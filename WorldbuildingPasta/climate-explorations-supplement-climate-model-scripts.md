# Climate Explorations Supplement: Climate Model Scripts

As promised, I’m going to do a quick overview of the python scripts I use to (for the most part) automate the process of running ExoPlaSim models for these climate explorations. Most of this is just to make it easier to run large batches of models; I don’t imagine that users running a single model will find much use with them, but I figured I’d make them available and explain their function for anyone who does want to do something similar.
Before we start, a couple notes:

  * I’m assuming here that you’ve already got ExoPlaSim installed and running and that you understand the basic workings of the model as explained in [the tutorial](https://worldbuildingpasta.blogspot.com/2021/11/an-apple-pie-from-scratch-part-vi.html).
  * I don’t expect any in-depth coding experience here, but I won’t be reviewing the basic concepts of coding or construction of python scripts here; you can look at the [official tutorials](https://docs.python.org/3/tutorial/) if you’re not familiar with them (you probably only need to get through the first 4 or 5 sections to follow what I’m doing here)
  * I’ve written all these scripts to function on an OpenSUSE partition, and they involve a fair bit of moving, editing, deleting, or overwriting of files; I know users who have installed OpenSUSE on a virtual machine occasionally encounter permissions issues with those sorts of functions, though without using a VM myself, I can’t be sure exactly what issues might arise or how to correct them.
This process uses a handful of scripts operating together, some of which are written in a somewhat nonlinear way to account for various special cases, so I may have to jump around a bit. But to start, here’s a fairly straightforward script; in this case, the one I use to model earth at 45° obliquity:
We’ll start from the top:
import exoplasim as exo  
import configparser  
import os These lines import the three packages we’ll be using in this script: exoplasim to run the model, configparser to read and write small configuration files, and os to work with file directories. The latter two are part of a default python install.
name='earth45ax'  
prev='earth30ax15ex'
name will be used for naming the files and folders used in the model; critically, it should be the same as the name for the script (without the “.py”). prev is the name for the previous model (in this case, the last step of the 30° obliquity model), the output of which will be used as the start of this model.
The next block identifies the year the model should start (lastyear) at and the restart file it should use (filename).
lastyear=0 First, it first sets lastyear to a default of 0, as appropriate for a new model.
if os.path.exists(name+'_crashed'):
Then it checks to see if there is a “crashed” folder associated with this model’s name, indicating that the model has been run before and crashed. In that case, it will aim to restart the model at a point 10 years before the crash (this is similar to the crashtolerant configuration option ExoPlaSim includes, but because this is performed once when the script starts, I can tweak parameters between each attempt to run again and limit the number of attempts to restart to avoid getting trapped in an infinite loop).
while True:  
if lastyear < 90:  
filename = name+'_crashed/MOST_REST.000' + str(lastyear+10)  
elif lastyear < 990:  
filename = name+'_crashed/MOST_REST.00' + str(lastyear+10)  
else:  
filename = name+'_crashed/MOST_REST.0' + str(lastyear+10)  
if os.path.exists(filename):  
lastyear += 1  
else:  
break This loop searches for the appropriate year. Starting with the initial lastyear of 0, it searches in the crash folder for a restart file 10 years after that year (requiring slightly different names for different orders of magnitude because of how the file names are formatted, though it’s assumed here that you’ll never run a model for more than 10,000 years). If it finds such a file, it increases lastyear by 1 and tries again; the first time it fails to find the appropriate restart file, it breaks the loop, leaving lastyear at that last value 10 years before the first missing year.
if lastyear == 0:  
filename = prev+'_out/'+prev+'/MOST_REST.00009'  
elif lastyear < 100:  
filename = name+'_crashed/MOST_REST.000' + str(lastyear)  
elif lastyear < 1000:  
filename = name+'_crashed/MOST_REST.00' + str(lastyear)  
else:  
filename = name+'_crashed/MOST_REST.0' + str(lastyear)
Next, it assigns a filepath to the appropriate restart file to filename (which was just used for convenience in the last block). If lastyear is still at 0, indicating that the model ran for less than 10 years before crashing, it refers to the output of the previous model (here, the last year of the 10-year run I do at the end of each model, as I’ll explain later). Otherwise, it refers to the restart file in the crash folder corresponding to lastyear.
else:  
filename = prev+'_out/'+prev+'/MOST_REST.00009'
And if no “crashed” folder exists, meaning the model is running for the first time, it also refers back to the output of that previous model. If this model is being run from scratch with no previous model, then I instead assign some placeholder value like “0” or “none” to filename; if exoplasim is told to use a restart file that it can’t find, it will just automatically start from scratch without one.
check = configparser.ConfigParser()  
check.read('times.ini')  
times = check['Time']  
step = times.getint('times')
cfg = configparser.ConfigParser()  
cfg.read('state.ini')  
rpt = cfg['State']  
level = rpt.getfloat('level')
We’ll discuss how configs are written and read later, for now all you need to know is that the script reads a couple of preexisting config files (“times.ini” and “state.ini”) to find two variables: step, which will be our model timestep, and level, which will control our CO2 and flux levels. If this model is not running from the output of a previous model, then instead of reading level from the config file, you should just set it to some reasonable initial value, e.g. level = 300e-6 if level > 10e-6:  
fluxlev = 1367  
clev = level  
else:  
fluxlev = 1357 \+ (level * 1000000)  
clev = 10e-6 level is then used to determine a CO2 level, clev, and a solar flux level, fluxlev. As I’ve mentioned before, I don’t want to use CO2 values below 10 ppm, so if level is above 10 ppm, it is used as the CO2 level and the flux is set to the default of 1367 W/m2, but if level is below that amount, then CO2 is left at 10 ppm and the flux is reduced instead; level essentially transitions from adjusting the CO2 level in units of bar to adjusting the flux level in units of MW/m2 relative to a baseline of 1357 W/m2 (10 W/m2 less than the default because the switchover happens at 10 ppm), such that a change of 1 ppm in CO2 before is now treated as a change of 1 W/m2 in flux here (which probably isn’t the actual equivalency, but should be close enough to allow a smooth transition).
I’ve also made some variants where CO2 is pinned to some set value (usually 300 ppm) and level only controls flux, allowing for it to be either decreased or increased from the default value as necessary.
model = exo.Model(workdir=name+"_run", modelname=name, ncpus=8, resolution="T42", layers=10, precision=8, outputtype='.nc', inityear=lastyear)
model.configure(timestep=step, runsteps=int(360*24*60/step), fixedorbit=True, landmap='earth64_surf_0172.sra', topomap='earth64_surf_0129.sra',  
pN2=0.78, pO2=0.21, pAr=0.01, pCO2=clev, ozone=True,  
eccentricity=0, year=360, rotationperiod=1, obliquity=45, flux=fluxlev,  
physicsfilter='gp|exp|sp', restartfile=filename,  
wetsoil=True, glaciers={'toggle': True, 'mindepth': 2.0, 'initialh': -1.0}, vegetation=2, initgrowth=0.5)
Here we create and configure the model itself. This should all be familiar from the ExoPlaSim tutorial, with just a few points worth noting:

  * workdir=name+”_run” and modelname=name use the established name of the model for naming folders and files, making other operations like finding restart files in the crash folder easier.
  * inityear=lastyear sets the lastyear value established earlier as the first year of this run, so the model will just pick up making new output files at the appropriate year if restarted from a crash.
  * timestep=step sets the timestep according to that step value read from the config file, and runsteps=int(360*24*60/step) adjusts the runsteps value to ensure that the model years are always equivalent to 360 days, for any timestep (I've made sure that none of the different timesteps used in this process could create issues with non-integer numbers of timesteps in each day or year).
  * pCO2=clev and flux=fluxlev set the CO2 and solar flux levels as appropriate given the earlier calculation from level.
  * restartfile=filename sets the earlier determined restart file.
model.runtobalance(baseline=20, maxyears=1000, minyears=20, crashifbroken=True, clean=True)
The model then straightforwardly runs to balance. Once it completes, it then writes a report on how the model ran:
report = configparser.ConfigParser()
First it creates a reference to the main ConfigParser function (I probably don’t need to do this anew each time I write or read a config, but when I was writing these scripts I figured it was better to keep these code blocks self-contained to make them easier to move around).
year = str(model.currentyear)  
tas = str(model.getbalance(key='tas'))  
co2 = str(level)
Then it extracts some information on the model’s current state; the current year, the global average 2-meter air temperature, and the level value (which I refer to here as co2, though as discussed it isn’t necessarily the actual CO2 value).
report['Report'] = {'name' : name,  
'outcome' : 'Success',  
'year' : year,  
'tas' : tas,  
'co2' : co2  
}
This information is formatted as a config file. The ConfigParser function writes out information as named variables organized into sections; here there’s just one section, ‘Report’, containing those variables we just found along with the model name and outcome (presumably successful if it’s run this far without crashing), but you can create multiple sections in this way all attached to that same report object, and they’d all be written together to the same file (this is how the koppenpasta.py script makes config and color list files).
model.finalize(name+'_out', allyears=False, clean=True, keeprestarts=True)
The model is then finalized and moved to an output folder; because I’m running a lot of these models, I save hard drive space by only saving the last year of the model and cleaning out the run folder, though I of course save the restart file to allow for the next model to be run off this one.
os.chdir('/home/user')  
with open('report.ini', 'w') as r:  
report.write(r)
I then switch the working directory back to my “home” folder (which will be named differently depending on your username) and write the report I prepared earlier to the text file “report.ini”, which is either created or overwritten if it already exists. I think the runtobalance function alters the working directory, hence the need to switch it back here. The resulting file should look something like so:
[Report]  
name = earth45ax  
outcome = Success  
year = 70  
tas = 294.1784691278832  
co2 = 0.0001725 We’ll discuss what that’s used for later.
Now, as I’ve mentioned before, though I initially want to see how the model balances out without interference, I also want to see how these models turn out with average temperatures of around 15 °C, for better comparisons with modern Earth (and in some cases I want to change the temperature to other values). As such I then take the output of this model run and feed it into another script with a bit more complex logic to try and achieve that average temperature:
Much of this is the same, but let’s look at all the additions:  
def statereport(run,level,adjust,ts,ts1,ts2,tol):  
rept=configparser.ConfigParser()  
rept['State'] = {'run' : run,  
'level' : level,  
'adjust' : adjust,  
'ts' : ts,  
'ts1' : ts1,  
'ts2' : ts2,  
'tol' : tol  
}  
with open('state.ini', 'w') as r:  
rept.write(r)
This defines a function which I’ll use a few times that, like writing the report, takes in some variables (which I’ll explain shortly) and writes them out to a text file, “state.ini” (which, you may recall, is where we retrieved our level value from in the last script), that will look something like so:
[State]  
run = 4  
level = 6.9e-05  
adjust = 3.45e-05  
ts = 291.8591408808789  
ts1 = 291.9569565854738  
ts2 = 292.51662414563674  
tol = 2.0 We’ll come back to that; moving on:
level = 300e-6  
adjust = level/5  
run = 0  
goal = 288.15  
tolerance = 4  
finalt = 1  
ts = 288.15  
ts1 = ts  
ts2 = ts Next it sets default values for a number of variables we’ll be using. Usually most of these are overwritten in the next couple sections, but they do need initial values for new model run for the first time, so I figured I’d just leave them in. Briefly:

  * level sets the CO2 or flux levels, as we’ve previously discussed.
  * adjust is the rate at which level is adjusted in the iterative temperature-adjusting function, which here is initially set relative to level.
  * run is the current number of iterations through that function, which should always start at 0.
  * goal is the desired final temperature (288.15 K here, or 15 °C), which will not be overwritten and so should always be set at the start here.
  * tolerance is the deviation from that goal that is tolerated by the function, though each time this is achieved it will be amended down until it reaches finalt.
  * finalt is the final tolerance required for the script to complete (1 K here), which again will not be overwritten and so should always be set here.
  * ts is the current average temperature of the model, which I’ve assumed to be 15 °C to start out.
  * ts1 is the temperature in the previous iteration, which I’ve set equal to ts just as a placeholder.
  * ts2 is the temperature 2 iterations ago, which again I’ve set to ts as a placeholder.
prev='earth45ax'
prior='earth30ax15ex'
name=prev+'15'
We then name the relevant models; prev is the initial run we are working off of, and the current model is named the same with “15” appended, as that’s how I’ve named all these temperature-adjusting scripts. But in case the previous model could not run to balance (typically because it got too hot), I also add a reference to the prior model that it was starting from, so that this model can run from that instead.
lastyear=0  
if os.path.exists(name+'_crashed'):  
while True:  
if lastyear < 90:  
filename = name+'_crashed/MOST_REST.000' + str(lastyear+10)  
elif lastyear < 990:  
filename = name+'_crashed/MOST_REST.00' + str(lastyear+10)  
else:  
filename = name+'_crashed/MOST_REST.0' + str(lastyear+10)  
if os.path.exists(filename):  
lastyear += 1  
else:  
break  
if lastyear == 0:  
if os.path.exists(prev+'_out'):  
filename = prev+'_out/'+prev+'_restart'  
else:  
filename = prior+'_out/'+prior+'/MOST_REST.00009'  
elif lastyear < 100:  
filename = name+'_crashed/MOST_REST.000' + str(lastyear)  
elif lastyear < 1000:  
filename = name+'_crashed/MOST_REST.00' + str(lastyear)  
else:  
filename = name+'_crashed/MOST_REST.0' + str(lastyear)
This is all much the same as for the first script, save that if the previous model didn’t complete, the script can start from the prior model instead. Then, given that the model crashed, it checks the “state.ini” file to determine the state of the model prior to the crash. Reading a config file works in a similar process to writing one:
cfg = configparser.ConfigParser()
First a name is defined to refer to the ConfigParser function cfg.read('state.ini')
Then that function is used to read the specific config file.
rpt = cfg['State']
Then a name can be attached to each section of variables in that file (just the one here).
run = rpt.getint('run')  
level = rpt.getfloat('level')  
adjust = rpt.getfloat('adjust')  
ts = rpt.getfloat('ts')  
ts1 = rpt.getfloat('ts1')  
ts2 = rpt.getfloat('ts2')  
tolerance = rpt.getfloat('tol')
We can then retrieve the individual variables within that section, using the names assigned to them when the report was written (compare to the statereport function above), though by default they’ll all be read from the file as strings, so configparser includes some functions to specifically read the variables as integers (appropriate for counting) or floats (appropriate for unit values).
If the model hasn’t crashed and is being run for the first time, then the approach is slightly different:
else:
if os.path.exists(prev+'_out'):
filename = prev+'_out/'+prev+'_restart'
else:
filename=prior+'_out/'+prior+'/MOST_REST.00009'
Again it finds the appropriate previous or prior model to start from.
cfg = configparser.ConfigParser()  
cfg.read('state.ini')  
rpt = cfg['State']  
level = rpt.getfloat('level')  
adjust = abs(level)/5 Then it reads the “state.ini” config file, but in this case only takes level from it; all other variables are left at their initial default, and adjust is set relative to level. 
Basically, “state.ini” is continuously updated as the script iterates, and if the model crashes, it takes all the variables from the last iteration and tries to pick up where it left off. But if the model is just starting, it just uses appropriate initial values, save for level which is preserved between models.
statereport('0',str(level),str(adjust),str(ts),str(ts1),str(ts2),str(tolerance))
These initial values are then immediately written to “state.ini”, such that if the model promptly crashes, it will use them when it starts again.
lines = ['start','\n']  
with open(name+'_report.txt','w') as f:  
f.writelines(lines)  
f.close()
The script then creates a new lines object, which is just a list of strings—to start out, just “start” and “\n”, which is not written out and instead forms a new line when written to file—and then creates a new text file named after the model to hold data about how the model runs; this is just for our reference and won’t be read by another script later, so we don’t need to use configparser to format it.
Retrieving the step variable, setting clev and fluxlev values based on level, and setting up the climate model are all the same. After that is the iterative temperature-adjusting function:
if os.path.exists(name+'_crashed'):  
balance=0  
model.run(years=5,crashifbroken=True,clean=True)
To start off, if the model is being restarted from a crash, it sets the balance value—which is used to track how close the model is to reaching a climate balance within tolerances—to 0 and initially runs for 5 years.
else:
model.run(years=2,crashifbroken=True,clean=True)
ts2 = ts1 ts1 = ts ts = model.getbalance(key='tas')
if abs(ts-goal) < finalt:
balance=5 else:
balance=0 model.run(years=3,crashifbroken=True,clean=True)
But if it’s being run for the first time, this little block is included to save time; it quickly runs the model for 2 years and then checks if the average temperature is already within the final tolerance (here, within 1 °C of 15 °C), then balance is set high to essentially tell the script to skip the whole iterative function and immediately conclude. Otherwise, balance is set to 0 and the model finished out an initial 5-year run.
Then (if not already at appropriate balance) the main iterative function starts,
while balance < 4:  
statereport(str(run),str(level),str(adjust),str(ts),str(ts1),str(ts2),str(tolerance))
At the start of each loop, it writes out the state at the start of the iteration to “state.ini”
ts2 = ts1  
ts1 = ts  
ts = model.getbalance(key='tas')  
run += 1  
year = model.currentyear The variables are then all updated; ts is set to the current average temperature, ts1 to ts’s former value, etc., run is iterated by 1, and year is set to the current model year.
lines=(['\n','\nrun ',str(run),'\nyear ',str(year),'\nlevel ',str(level),'\nadjust ',str(adjust),'\nts ',str(ts)])
This is all saved to the lines object, formatted such that it will appear as a neat block when written out to the file, like so:
run 1  
year 5  
level 0.0003  
adjust 5.9999999999999995e-05  
ts 293.02718480896345 run 2  
year 10  
level 0.00023999999999999998  
adjust 5.9999999999999995e-05  
ts 292.2692299133993
(The long lines of 9s or 0s are just harmless floating-point errors, don’t worry about them).
And then written to the report file:
with open(name+'_report.txt','a') as f:
f.writelines(lines)
f.close()
Because we are using append mode here (the ‘a’ in the function, as opposed to ‘w’ usually used), this text is added to the end of the file rather than overwriting it, so the file ends up as a continuous report of the state of the model at each iteration.
while True:
Within the iteration loop, we then start another loop to determine what adjustments should be made before the next run (while True: is a convenient way in python to make a loop that just runs until something in the loop tells it to stop). This is a slightly complex decision tree, so try to follow closely:
if ts < goal - tolerance:  
balance = 0 First off, we check if the model is colder than tolerated, in which case we first indicate the model is not balanced.
if ts - ts1 < tolerance/4:
If the model has not substantially warmed in the last run, than we need to try to raise level to warm it, but first:
if ts1 > goal:  
adjust /= 2 If the model was previously warmer than our goal but now got substantially colder, then it seems that we tried cooling the model in the last iteration but overshot the goal, and so adjust is halved to allow for finer adjustments.
elif ts < ts1 and ts1 < ts2:  
adjust *= 2 But otherwise if the model has been consistently cooling for the last two iterations, then it’s likely we’ve been trying to warm the model and failing, so adjust is doubled for more aggressive warming.
level += adjust If neither case is true, adjust is left as-is, and in any case, level is increased.
elif ts - ts1 > goal - ts:  
adjust /= 2  
level -= adjust On the other hand, if the model is warming very quickly, such that it appears likely to overshoot the goal in the next iteration, then we’ve likely been trying to warm the model and overdid it, so adjust is halved and level is reduced to slow the warming.
break If the model is warming between these limits, then level is unadjusted on the assumption that the model is warming towards our goal and just needs to be given more time. In any case, the loop is broken to proceed to the next step.
elif ts > goal + tolerance:  
balance = 0  
if ts1 - ts < tolerance/4:  
if ts1 < goal:  
adjust /= 2  
elif ts > ts1 and ts1 > ts2:  
adjust *= 2  
level -= adjust  
elif ts1 - ts > ts - goal:  
adjust /= 2  
level += adjust  
break If the model is colder than tolerated, than the logic is much the same, just with all the warming/cooling reversed.
else:  
if ts > ts1 + tolerance/4:  
balance = 0 If the model is within the tolerated temperature range, then it’s still not considered balanced if the temperature is changing too quickly, as it may just leave the tolerated temperature range in the near future. In this case, the model is warming too quickly, and so needs to be cooled.
if ts2 > ts1:  
adjust /= 2 If the model cooled in the last iteration and is now warming too quickly, then it appears that we’ve been trying to get it to settle at balance and overcorrected, so adjust is reduced.
level -= adjust  
break And regardless, level is reduced.
elif ts < ts1 - tolerance/4:
balance = 0 if ts2 < ts1:
adjust /= 2 level += adjust break And if the model is cooling too quickly, much the same deal.
else:  
if tolerance > finalt*1.01:  
balance = 0  
tolerance /= 2  
adjust /= 2 If the model is within the tolerated range and not changing too quickly, then tolerance is reduced (and adjust with it to allow for finer corrections), and then this whole loop-within-a-loop repeats to see if the model fits within the new, tighter tolerances. If it does, this repeats until reaching the final desired tolerance, finalt (multiplied by 1.01 here to account for floating-point errors).
else:  
balance += 1  
break And at long last, if the model is within that final tolerance, it is regarded as being at balance.
The script then modifies and runs the model based on all these adjustments:
if balance > 2:  
break First off, if the model has managed to remain at balance for several iterations, the function is complete and the loop ends.
if level > 10e-6:  
model.modify(pCO2=level, flux=1367)  
else:  
model.modify(pCO2=10e-6, flux=1357 + (level*1000000))
Otherwise, CO2 and flux levels are modified to match the new adjusted level, following the same logic as when first constructing the model.
if balance == 2:
model.runtobalance(baseline=20, maxyears=3000, minyears=20, crashifbroken=True, clean=True)
elif balance == 1:
model.run(years=10,crashifbroken=True,clean=True)
else:
model.run(years=5,crashifbroken=True,clean=True)
And finally, the model itself runs. If not at balance, it runs for 5 years; if it has just achieved balance, it runs for 10 years; and if, after that, it has retained that balance, it properly runs to balance (as defined by ExoPlaSim rather than my function). All of these runtimes are tweaked in models where the year length is significantly altered.
This iterative process has generally proved to be fairly reliable in achieving the desired temperature, though it can be a bit slow; even an adjustment by a few degrees can take 100 years of modelling to complete. It can also run into issues when dealing with unstable climates on the cusp of rapid melting or thawing, for example:

  * For my exploration of different average temperatures, I attempted to make the model balance at –20 °C, but this was evidently just not possible; below some threshold of CO2, it would freeze over completely and drop to –60 °C, and above the threshold it would warm to –18 °C. The model therefore got trapped endlessly adjusting CO2 up and down close to that threshold in response to rapid temperature shifts which never balanced. Ultimately I just stopped the model, picked a CO2 level just above the threshold, and let it balance there.
  * When running the 90° obliquity model, it initially balanced at a low temperature of around –20 °C, with a thick ice belt in the tropics. The model raised CO2 to get it to warm closer to 15 °C, but at around 0 °C the ice belt rapidly melted and average temperatures shot up to over 30 °C, at which point the summer temperatures at the poles were high enough to cause the model to crash before it could bring CO2 levels down again. I ultimately had to write a special function to raise CO2 levels just high enough to melt the ice belt and then immediately drop them to 300 ppm when the model passed 5 °C.
report=configparser.ConfigParser()
year = str(model.currentyear)
tas = str(model.getbalance(key='tas'))
co2 = str(level)
report['Report'] = {'name' : name,
'outcome' : 'Success',
'year' : year,
'tas' : tas,
'co2' : co2
}
model.finalize(name+'_out',allyears=False,clean=True,keeprestarts=True)
os.chdir('/home/user')
with open('report.ini', 'w') as r:
report.write(r)
statereport(str(run),str(level),str(adjust),str(ts),str(ts1),str(ts2),str(tolerance))
Once that whole process is complete, it then finalizes and writes out both the final report as with the previous script and the current state of the model for use with the next model. Note that, because all models use the same “state.ini” file, if you want one model to inherit the same level as another, it has to be run directly after it, or you’d have to manually edit the file or add some logic to record that level elsewhere and refer to it later.
Once that’s done, a third script runs the model one last time:
This looks much like the first script, but in this case the model runs for only 10 years and data from all years is retained, allowing them to be averaged together for producing more reliable climate data. Because it only runs a short time, there’s also no special case for restarting from a crash; if it crashes, the model just starts over.
Now that we’ve got these scripts set up, here’s the script I use to automate the running of *those* scripts:
To start:
import os  
import sys  
import shutil  
import configparser No need for exoplasim here, and I’m also using shutil to move some files around (also part of the default python install). I honestly don’t remember why I imported sys in this one, but I don’t want to break anything by removing it and it's a default package.
As is scripting convention, I’ve put my functions at the top of the script and the main commands at the bottom, so let’s just jump down to the latter at line 70:
hasrun = []  
while True:  
adjtime(30)
First off I create an empty list, hasrun, which I’ll use in a moment, and then start a loop; each run of the loop will run one model. The first thing we do each loop is call the adjtime function, at line 53:
def adjtime(time):  
timer=configparser.ConfigParser()  
timer['Time'] = {'times' : str(time)}  
with open('times.ini', 'w') as t:  
timer.write(t)
This just takes in a given timestep value and then saves it to the “times.ini” config, which is a pretty straightforward little file:
[Time]  
times = 30 As you may remember, each of the model scripts above reads that config when it starts and uses it to set its timestep, which allows us to easily adjust the timestep if the model is having trouble completing.
Back to the main loop:
with open("queue.txt", "r") as qlist:  
models = qlist.readlines()
The script opens the text file “queue.txt” and reads out each line. “queue.txt” is a simple text file I made containing a list of model names in the order they should be run, like so:
earth30ax  
earth30ax15  
earth30ax15ex  
earth45ax  
earth45ax15  
earth45ax15ex  
earth15ax  
earth15ax15  
earth15ax15ex  
earth5ax  
earth5ax15  
earth5ax15ex Having the list of models in an external file and making the script read that file again each loop means that I can add to or edit the queue of models to be run while the script is running.
Next:
finished = True  
for m in models:
I’ll explain finished in a moment; for now, the script looks through that file line by line.
if m.strip() == "wait":  
wait = input("WAITING......")  
break If it hits a line that reads as wait, the script will simply wait until told to continue (by pushing “enter”). This way I can put a pause between models if I want to do something before the next one in the queue runs. When the script continues, it starts a new loop and reads “queue.txt” again, so you can change the queue if you need to; note that you should also remove the wait line in “queue.txt” before continuing the script, or else it will see that line again and just immediately pause again without moving on in the queue (I could probably add some more complex logic to work around that, but it’s not really worth the effort).
elif m not in hasrun:  
finished = False  
print("running " + m)  
runscr(m.strip())  
hasrun.append(m)  
break Otherwise, it checks the model name against the list hasrun, which tracks the models that have already been run this session. If the model hasn’t been run, it changes finished to indicate that the script hasn’t concluded and prints a quick message on screen showing the model it’s running. It calls the runscr function we’ll look at in a moment with the model name (using strip() to remove any extraneous spaces or line breaks) and when that completes, adds the model to the list of models run and stops reading the list, effectively starting a new loop.
Note that this approach means that the script can’t run the same model multiple times in one session; if you want to try running a model again, you either have to give it a different name (changing the name of the script and the name variable within it as well) or stop this script (simply closing konsole will do it) and start it again (with “queue.txt” edited to remove any models you don’t want it to run again, as it won’t remember between sessions).
if finished:  
break If the script looks through the queue and finds no models it hasn’t already run, then it’s finished and the script concludes.
Now, the runscr function, starting at line 6:
def runscr(model):  
attempts=0  
runcom = 'python3 ' + model + '.py'  
outfold = model + '_out'  
while True:
It starts off by setting the number of attempts at running the model to 0, and then based off the model name, it constructs an appropriate command to run the model script and works out the name of the output folder produced when the model successfully completes. Then it starts a loop, with each run of the loop representing one attempt to run the model to completion.
if os.path.exists(model+'_crashed'):  
names = os.listdir(model+'_crashed/')  
for name in names:  
if os.path.exists(model+'_run/'+name):  
pass  
elif name.endswith(".nc"):  
print('moving '+name)  
try:  
shutil.copy(model+'_crashed/'+name,model+'_run/')  
except:  
pass First, some special logic in case the model has run once and crashed. See, when the model crashes, it takes everything from the “run” folder and moves it into the “crashed” folder. The way we’ve written our model scripts, when they run they’ll pick up 10 years before the crash and put the outputs from there onwards in the “run” folder. The problem is that the runtobalance function requires that the .nc data files for every year from 0 onwards be in the “run” folder to run correctly. As such, the script looks through the “crashed” directory for every .nc file and, if it doesn’t already exist in the “run” folder, copies it over. I do this with the nifty try/except function here, which attempts to copy the file over, and if it encounters an error, rather than crashing the whole script, it just executes whatever’s under the except command (which in this case just tells the script to move on).
if os.path.exists(model+'_run/state.ini'):  
try:  
shutil.move(model+'_run/state.ini','state.ini')  
except:  
pass We also check if the “state.ini” file has been written into the “run” folder rather than “home” for some reason (I think this might happen as a side-effect of the runtobalance function), and if so moves it out to the "home" directory, which is where the model will look for it when it restarts.
if os.path.exists(model+'.py'):  
os.system(runcom)
The script then checks that the appropriate script exists and, if so, runs it through a konsole command (this is not usually the recommended approach to operating functions in one script from another, you should generally import the script functions as packages, but it serves our purposes here and allows us to write new scripts and add them to the queue while this process is running).
else:  
print('no script')  
failreport(model)  
break If it doesn’t exist, it reports this on konsole, creates a failure report (which I’ll explain later), and stops the loop to cease attempts to run it.
if os.path.exists(outfold):  
os.system('python3 maps.py')  
try:  
shutil.rmtree(model+'_crashed')  
except:  
print('no folder')  
break If the model does run, the script then checks if it completed and produced an output folder; if so, it then runs the external script “maps.py” (which we’ll look at shortly), attempts to delete the “crashed” folder, if it exists, to save hard drive space, and breaks the loop.
elif attempts > 20:  
failreport(model)  
break  
elif attempts > 15:  
adjtime(10)  
elif attempts > 10:  
adjtime(15)  
elif attempts > 5:  
adjtime(20)  
attempts += 1 If the model crashed, then the loop continues, and every 5 attempts to run the loop, the timestep is reduced (to 20, 15, and then 10 minutes). If, after 20 attempts, the model still fails to complete, then the script gives up and reports a failure.
os.system('python3 report.py')  
return In any case, the script runs the script “report.py” and concludes.
So let’s look at these external functions and scripts, starting with the failreport function in this script, at line 59:
def failreport(model):  
report=configparser.ConfigParser()  
report['Report'] = {'name' : model,  
'outcome' : 'Fail',  
'year' : '0',  
'tas' : '0',  
'co2' : '0'  
}  
with open('report.ini', 'w') as r:  
report.write(r)
This is just like the report-writing functions in our model scripts, but here it reports a failure and fills the variables with placeholders.
Next, the “maps.py” script that runs if the model successfully completes, which takes the final output of each model and creates some convenient averaged data files and climate maps from them:
From the start:
import koppenpasta as kp  
import eps_avg as ea  
from PIL import Image  
import os  
import configparser It imports the koppenpasta and eps_avg scripts I’ve made previously (and won’t show here; they’re detailed in my [previous tutorial](https://worldbuildingpasta.blogspot.com/2021/11/an-apple-pie-from-scratch-part-vi.html#thekoppenzonescript) and in the [koppenpasta repository](https://github.com/hersfeldtn/koppenpasta)), as well as the Image function from Python Image Library, and of course the os and configparser libraries as we’ve seen before.
As before, the function (just the one here) is on top and the main commands below them, at line 30:
if __name__ == "__main__":
This means this only runs if the script is called directly, not if it’s imported as a library (as I use the mappy function here in some other scripts as well).
cfg = configparser.ConfigParser()  
cfg.read('report.ini')  
rpt = cfg['Report']  
model = rpt.get('name')
The script reads the report from the latest model and finds the model name.
mappy(model)
And then runs the main function:
def mappy(model):  
if os.path.exists(model+'_out/'+model):  
path = model+'_out/'+model  
else:  
path = model+'_out'
That function first finds the appropriate path to the output files, which are formatted a bit differently by ExoPlaSim depending if there’s a single-year output (allyears=False in the finalize function) or multiple years.
outnorm = path+'/'+model  
outint = path+'/'+model+'_interp'  
kp.MakeMap(path, outnorm)  
kp.MakeMap(path, outint, interp=8, dum_ice=1, use_topo=1, topo_path='earthscale.png', maxel=6300, minel=0, gravity=9.81, blend_topo=1, sealev=0)
It then creates two climate maps with the koppenpasta script, one using the default settings and one interpolated to 512x1024 resolution, using an Earth topography map for temperature adjustment, and then saves both maps to that model’s output folder with different names. If you wanted to use different topography maps for different models, there are a couple ways you could approach that, but I think the simplest would be to give the models using different topography distinctive names and then add logic here to check the model name, e.g.:
if model in (‘earth’):
topo = ‘earthscale.png’
min = 0 max = 6300 grav = 9.81 elif model in (‘kashyyyk’):
topo = ‘kashyyykmap.png’
min = -200 max = 4600 grav = 8.82
(and then use those variables in the kp.MakeMap command).
with Image.open('kop key.png') as key:  
with Image.open(outnorm+'.png') as norm:  
im = Image.new("RGB", (1024,740))  
im.paste(norm.resize((1024,512), resample=Image.NEAREST))  
im.paste(key, (0,512))  
im.save(outnorm+'.png')  
with Image.open(outint+'.png') as interp:  
im = Image.new("RGB", (1024,740))  
im.paste(interp)  
im.paste(key, (0,512))  
im.save(outint+'.png')
Next, the script opens an image of a map key I have waiting in my "home" folder:
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhdljr-FpIGODY2gsTp1d0nG7EIWj-NMsLEMDo2tiCkb75W7TSdBaN3YH_5TZlqYaV6ChJDF_HQz_p48dhL3MNw-Ha94LEuuX2P-iS7AiPRZERon_etRu0uWuX8HnS699i9HKXwqUNc6ZCh7fVVN-UrpzMLIrCUD0ONs-OPJIfIlle-YKyEgRoByRV1TA/w640-h142/kop%20key.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhdljr-FpIGODY2gsTp1d0nG7EIWj-NMsLEMDo2tiCkb75W7TSdBaN3YH_5TZlqYaV6ChJDF_HQz_p48dhL3MNw-Ha94LEuuX2P-iS7AiPRZERon_etRu0uWuX8HnS699i9HKXwqUNc6ZCh7fVVN-UrpzMLIrCUD0ONs-OPJIfIlle-YKyEgRoByRV1TA/s1024/kop%20key.png)
And then opens each of the climate maps in turn and pastes the map and key together (resizing the uninterpolated map up to 512x1024 resolution) into a new image, which it saves over the existing map images. These are the climate maps you see in the other posts in this series.
ea.main(path, outnorm+'_av', 1, 0, 1, 1)  
return It then uses the eps_avg script to create averaged Netcdf files as well (including an annual average file, rotating the longitudes for better viewing with Panoply, and converting the precipitation units to mm/month) and the script concludes.
Note that this script makes the maps and averaged data files using all the .nc files in the model outputs. In these cases where I’m either only preserving the last year of the model or running a short model of a climate already at balance, that’s fine, but if you preserve all the years of a model run, the map and climate files produced here will average that all together and so not represent the final state of the model.
Finally, let’s look at the “report.py” script, which sends an email to me at the end of every model showing the outcome and even with one of the climate maps attached:
From the top:
import configparser  
import smtplib, ssl  
import os  
from email.mime.application import MIMEApplication  
from email.mime.multipart import MIMEMultipart  
from email.mime.text import MIMEText  
from email.utils import COMMASPACE, formatdate It imports our usual configparser and a bunch of specialized functions for handling emails.
cfg = configparser.ConfigParser()  
cfg.read('report.ini')  
rpt = cfg['Report']  
name = rpt.get('name')  
out = rpt.get('outcome')  
year = rpt.getint('year')  
tas = rpt.getfloat('tas')  
co2 = rpt.getfloat('co2')
It then reads off the report made by the last model.
sender = "sender@email.com"
receiver = "receiver@email.com"
It then designates a sender and receiver email. I would suggest making a new email account specifically to send these emails to avoid any possible security risk to your existing accounts.
message = """
Hello sir, we have done more calculations for you Report:
""" + 'Name \n ' + str(name) + '\n\nOutcome \n ' + str(out) + '\n\nYear \n ' + str(year) + '\n\ntas \n ' + str(tas) + '\n\nCO2 \n ' + str(co2)
Here we make the main body of the report, which is just a generic message with the report data attached as a formatted list, which will look something like this when emailed:  
Hello sir, we have done more calculations for you  
Report:  
Name   
earth45ax  
Outcome   
Success  
Year   
70  
tas   
294.1784691278832  
CO2   
0.0001725 Moving on:  
msg = MIMEMultipart()
msg['From'] = sender msg['To'] = receiver msg['Date'] = formatdate(localtime=True)
msg['Subject'] = "Model Report"
msg.attach(MIMEText(message))
This constructs an email object with the appropriate information and a subject, and attaches the message to it.
if out == "Success":  
try:  
if os.path.exists(name+'_out/'+name):  
path = name+'_out/'+name+'/'+name+'.png'  
else:  
path = name+'_out/'+name+'.png'  
with open(path, "rb") as fil:  
part = MIMEApplication(  
fil.read(),  
Name=name+'.png'  
)  
part['Content-Disposition'] = 'attachment; filename="%s"' % name+'.png'  
msg.attach(part)  
except:  
pass If the report indicates the model succeeded, then the script looks for one of the climate maps we made previously (the uninterpolated one) and attempts to add it as an attachment to the email.
port = 465  
password = 'password'
context = ssl.create_default_context()
with smtplib.SMTP_SSL("smtp.gmail.com", port, context=context) as server:  
server.login(sender,password)  
server.sendmail(sender,receiver,msg.as_string())
Here we send the email itself. How you approach this may vary depending on the email you use. With gmail, you should use the port 465 and then run through [this process](https://support.google.com/accounts/answer/185833) to get an appropriate password; in short, turn on 2-step verification, log into the gmail account on the device you’re running models on, and then get a password that will work only for that device. Even then, leaving the password in code like this is generally *not recommended* if there’s a chance anyone else might access this code or the device, but in my case I’m the only one who touches the code or this laptop, so I figure it’s fine; again, use a disposable email for this.
And that about wraps it up. So, to summarize the whole process:

  * queue.py reads the list of models from queue.txt and runs them each in turn
  * Each model consists of 3 scripts:
    * An initial run to balance with the main parameter altered.
    * A model with an iterative function to alter CO2 or solar flux levels to achieve a desired average temperature of 15 °C.
    * A final, short run of 10 years as a sample for producing the output data and maps.
  * As these models run, they read and write some simple text files:
    * times.ini, which allows queue.py to determine the timestep of the models.
    * state.ini, which tracks the current state of the model between model runs and crashes.
    * report.ini, which records the final state of the model when it completes (or records that it failed to complete).
    * [model]_report.txt, named for each model, which records the process of the iterative temperature-adjusting function.
  * If a model crashes, queue.py moves the .nc files back into the run directory and the model restarts 10 years before the crash.
    * If it crashes again, queue.py reduces the timestep every 5 attempts and then gives up and reports a failure after 20 attempts.
  * If a model completes successfully, maps.py creates climate maps and averaged data files from the outputs, and attaches keys to the maps.
  * At the end, report.py sends me an email with the reported result and, if the model was successful, a climate map as an attachment.
I hope that all helps and isn’t too tediously detailed. As you might have guess by my choice of example, the climate models for different obliquities are coming along nicely and should make for an interesting exploration. I’m also *finally* making some progress on a reliable methodology for creating terrain for the next post in the main series, so, exciting times ahead.
