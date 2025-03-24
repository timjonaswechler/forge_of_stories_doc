# GPlates: Splitting Comoving Plates- Worldbuilder’s Log 13

good morning interweb world Builders log
13. today we are going to learn how to
split apart coal moving plates and begin
modeling our second rifting vent so just
like the last time we had a rifting
event we need to cut apart the various
components here and assign them the
correct plate ID everything north of the
rift here should have a plated D of 300
in this case everything south of the
rift should have the plate ID of 200 so
let's do that so I'm going to just zoom
in a little bit I'm going to hit F on my
keyboard select feature and I'm going to
select this continent here I'm going to
cut it apart to make a North half and a
South half so I'm going to clone feature
it's a continent so-called in the
continents folder and then I'm going to
hit V on my keyboard to move some
vertices to match up with the rift we've
already done this no new information
here so time-lapse mode engaged
okay something like that hit F on the
keyboard to select that feature hit
controller command e to edit feature or
pop up here to the top right this fella
is not content PC this fella is
continent B now because it contains only
Craton B it begins its life at 900
million years ago at the point of this
second rifting event and it has a player
D of 300 so that's code I want to change
that all right done I'm going to repeat
this process again to cut out the bottom
half but this time I'm just going to
give it a player ID of 200 that's the
only difference again no new information
it's been covered before time-lapse mode
engaged
cool and then I'm going to hit F on my
keyboard again I'm going to select the
original continent that contained both
of the gratons and I'm going to edit
feature so Ctrl or command e or on the
top right here and then I'm going to
change its age so it began life at a
thousand million years ago correct but
it's going to cease to exist at this
moment of Riften at 900 million years
ago so I'm going to pop that in
and then we're good
and then as far as I remember from the
last time I labeled these fail riffs
correctly this should have a playerity
of 300 and it does this should be 200
because it's on the south it does and
this should have be 200 because it's on
the south perfect so next we need to cut
apart the oceans here and this island
arc now these are features where we care
about the dating on them so we're going
to employ a slightly different method so
let's start with the ocean over here so
I'm going to scroll over hit F on the
keyboard select this ocean here just
like before I'm going to clone it
its ocean cross circles and the ocean
crusts folder and then I'm going to hit
X on the keyboard and I'm going to
delete a bunch of points until we're
only left with the north side
Bingo it already has a played ID of 300
so I don't need to touch anything hit F
again on the keyboard and I'm going to
select the ocean slab again I'm going to
clone it again it goes in the ocean
cross folder hit OK hit X and I'm just
going to start deleting points until
we're left with just the southern
portion
okay I'm going to hit F here now here
this plate hoodie will need to be
changed to match with the green crate on
here with 200 or we need to change it to
200 so I'm going to go up to edit
feature I'm gonna go down to Plate ID
and I'm going to change this to 200.
ahead close and then I need to select
the original slab of ocean crust
but unlike last time where we changed
its end date we're just going to delete
it entirely and that way we preserve the
the dating on these features okay I'm
going to do the exact same thing for
this other half of Ultron crust exact
same procedure so time lapse mode
engaged
okay that's the ocean crossed on so
let's scroll back into the simulation
and let's see if there are any issues
foreign
something's a little funny here why is
that occurring oh I see I see okay so if
you notice here as the simulation is
progressing this content is already kind
of cut in half that shouldn't occur it's
not a big deal or anything bullsh let's
just make it all nice so I'm gonna
select that half here and I guarantee I
just didn't change the dates correctly
edit feature yeah there we go that
bottom half
here only starts becoming its own thing
at the moment of the second rifting so
that's at 900 million years ago I'm here
okay
that should be fine let's check that
cool much better now the island arc same
procedure as the ocean crust hit F on
your keyboard select the feature clonus
delete points so you're only left with
the northern half say
it already has a playerity of 300 so we
don't need to change anything there so
I'm going to hit F on my keyboard select
again the original feature clonus
and then this time I'm going to delete
everything to the north
okay hit F and we need to change its
plate ID so control or command e
and I'm going to change its plate ID to
200 because it's stuck to the 200
portion of the content select the
original feature and just delete it boom
all right and again a check always try
and check as you go it'll say if you're
committing an error and then only
realizing it way down the line
brill brill all right and then the final
Islands here notice it's pink so it's
gonna move with pink we do not want that
so I'm going to hit F on my keyboard and
I'm going to do a thing that I
recommended not doing before but
hopefully be okay okay control or
command e and I'm just going to change
its player D straight up
really hope this won't cause any
problems but let's give it a shot and
close
yes okay cool sometimes what will happen
is the feature will jump around the
globe thankfully it didn't do that here
fantastic so everything in the north is
pink everything in the South who's green
barring the subduction zone we need to
do a subduction zone and then we're
ready to Rift so this is actually
thankfully easy hit F choose a
subduction zone hit t for the what's it
called split feature tool yep and you
can only do this with lines and you
simply just at the point you want to
split you just click and G plates will
have created hit F on the keyboard one
copy to sell and one copy to the north
dead easy and the southern copy we are
going to change it's pretty to 200.
now and one final check
solid okay now we can start rifting so
the problem here is that this green
chunk it's been moving with pink so it's
just been following what pink has been
doing which means if we attempt to try
and over go forward the time step let's
go forward to 850 hit 5 on the keyboard
hit F to choose feature
hit p on the keyboard and then go up to
top right and highlight children you'll
see here that if we move this everything
in white is going to go with it so we
need to decouple the bottom Crayton from
the top one so they can both move
independently so to do that hit
controller command M to bring up manage
feature Collections and just save all
changes the important thing here is that
the rotation file is saved so we're
going to open that rotation file in text
edit
or whatever plain text editor you're
using so we want to decouple everything
with plate ID of 200 from 300 right so
what that means is take the last entry
in that place
which also happens to be the first entry
in this instance and remember G plates
reads the file backwards copy that
and paste it above it
then change the time here to the rifting
event so the rifting vent is going to
happen at 900 it's going to be completed
by 850. it's going to happen at 900 for
me so I'm going to put in 900 and we'll
make a little note here a little comment
and say that this line code
and
following C so this makes it so that's
going to stop following C and then we're
going to copy this again
and we're going to paste it above it
and this is going to be our
start
moving
independently line then change the plate
ID of this line the start moving
independently line change that to zero
zero zero so it's decoupled from 300.
now don't save anything leave everything
the way it is go back to G plates hit
Ctrl or command P to bring up this total
reconstruction polls the value here
needs to be the moment of rifting so I
actually need to scroll back in my
simulation a little bit sorry bear with
me
controller command P so the value here
like I said has to be at the moment of
rifting and this has to be zero then
click on equivalent rotations relative
to Anchored place and then find the
current location of the plate you want
to move independently so I want 200 to
move on its own currently it's at a
latitude of this a longitude of this and
an angle of this so go back to text edit
and fill in these values
in these columns here okay so the first
one here that is the latitude that
61.1665
this value here is the longitude that's
negative 18.3597
and this value here is the angle that's
33.5664
and then finally copy all of this and
put this above it and we'll turn this
into our usual drift correction
that means everything's kept the same
except we change our time to 1.0 or any
small non-zero number okay so we're
ready to save the rotation file let's
get rid of some of these lines
very good we hit save we'll go back into
G plates hit command or control M to
bring up manage feature Collections and
we are going to find our rotation file
and reboot it now hopefully absolutely
nothing should have changed save for the
fact that we can now move these two
independently so let's see if that works
this is always the moment of truth so
I'm going to move forward 50 million
years
I'm going to hit 5 of my keyboard to
bring up the poll manipulation tool I'm
going to hit f
to select the feature p highlight
children up here is selected and notice
notice everything in white here is
exactly what we want to move with this
half of the continent if I hit F again
and select the bottom half hit p
you'll notice everything here
is exactly what I want to move okay and
then just like before I hit o go to the
top right here and enable pole and we'll
move this fell around in combination
with the p menu and the all menu to
split these apart now I'm thinking again
because these are rifting apart this is
this fella is going to travel northward
and this trap fella is going to travel
Southward no new information so
time-lapse mode engaged
foreign
will be funky don't worry about it we're
going to need to repair them in a second
like last time controller command plus
shift and K brings up the kinematics
tool and I want to look I'm moving
Toyota D300 so I want to drop in okay
the 300 here and I'm looking for the
speed of display between 900 and 850
million years ago so beginning at 900
million years ago ending at 850 million
years ago and I want velocity and hit
update and we are traveling at one
centimeter per year that is a bit slow
because again we have mid-ocean ridge
ocean continent subduction zone
basically South America again so we're
looking at about three centimeters per
year so I'm just going to move him a
little bit further
2.9 centimeters per year that will do
and now I'm going to repeat this exact
same process but for the southern
continent
okay cool and don't forget about this
continent here it's also going to be
moving so I think this is just going to
keep heading west I guess we'll call it
so I'm going to place this Pole right up
on top we'll say and just have it make a
great circle like this nothing too fancy
yeah something like that let's have a
look at the simulation those fire No in
fact let's not do that let's put in
drift correction to make sure these
don't move everywhere so command or
control M and I'm going to save this
rotation file to import this new data
into the rotational file and then I'll
open up text edit
line breaks
and then delay his timestamp that's 850
million years I'm gonna copy this
I'm going to paste it into
drift correction in fact actually better
idea I'm just going to copy the
coordinates
and paste them into the coordinates of
drift correction boom copy the
coordinates
paste into drift correction
copy
paste
remove line breaks
save everything up
back in GPS command or control M and I'm
going to reload that rotation file and
then all the flow lines will get even
worse but that's fine because we're
going to need to reconstruct them so
let's just check if this movement is
decent
that looks pretty sweet to me and make
sure we go back to our correct time step
okay so now we need to fix these floor
lines I would recommend saving at this
point because things can go wrong a
controller command M and just save all
changes before you save and then file
save project now sometimes it's easy to
just kind of tweak the lines I guess but
in this case I'm just going to delete
them and wholesale remake them
so F on the keyboard
select the flow lines and simply delete
feature so let's start with the easy
ones let's set up flow lines between
continent C here and continent B so I'm
going to go back to when they were
attached that's 900 million years ago
I'm going to select my Rift
I'm going to copy points a digitize tool
hit M on the keyboard to turn that into
a bunch of points very important create
feature this is going to be a flow line
hit next left plate ID and right play
Hoodie so the Json player these are 300
for the pink
and 200 for the green and these floor
lines will begin at the moment of
rifting so that's 900 oh that's
incorrect at 900.
million years ago and they'll continue
into the distant future and name will be
flow lines 900. same thing as before
standard way of setting up flow lines
next
we're going to hit add so from 900
million years ago
to the end of the simulation in steps of
10 million years perfect hit insert
Ubuntu timestamps between 900 and the
end of simulation hit okay
next and then we'll save this in flow
lights and we'll go create let me check
if that worked
it's very nice so now we need to make
flow lines between this continent and
these two continents so this is a little
bit more complicated
again we'll go back to the moment of
rifting between these continents so
that's the very start of simulation in
this case a thousand million years ago
because I want one set of flow lines to
connect between blue and pink and the
other between blue and green what you
can do in fact what you should do is hit
F on the keyboard select the rift hit t
on the keyboard to bring up the split
feature tool and then just simply split
the rift in half now where does the
split occur
it's going to be where is this here yeah
so these this point here matches up at
this point so everything north of that
goes that way everything south of that
goes that way so that is the splitting
point so we'll go back to our moment of
rifting and we will split it
here so we should have two copies here
one Rift in the South and one Rift in
North perfect so we'll keep that
selected that Northern Rift I'm going to
copy points to digitize tool I'm going
to hit M on my keyboard get an error but
then go over to the top here digitize
new multi-point geometry hit create
feature flow line adjacent plate ID so
100 is adjacent and we're connecting up
to the pink one which is 300.
the beginning time for these floor lines
will be when this Rift opens that's a
thousand million years ago and we'll
call this flow lines at 1 000 million
years next now usually you'd have to add
a bunch of points here and in fact we do
but it's grayed out so what you need to
do is you to go down to this section
here scroll to the bottom and under gpml
times double click that and ensure that
all of these times are accurate in this
case they are not in this case they're
only going from 900 million years so we
do not want that we want to go from all
the way to start and then hit insert and
then do a quick check of this to see if
everything's fine yep thousand million
years ago all the way to the end done
then hit next and put it in flow lines
create again we'll play and we'll just
check to see if everything's gravy
boom look at that tastiness so back to
the start of simulation we'll select
that southern portion of the rift and
again if you have trouble selecting go
down to the bottom here and select Rift
copy geometry to digitize tool hit m
or come over to the left here digitize
new multi-point geometry create feature
exact same method here flow lines left
player D is 100 correct right plated e
is going to be 200. because we're tying
the blue and the green together
beginning time thousand yeah floor lines
one thousand perfect next
again I want to double check this so I'm
going to scroll down to gpml times
double click that and we should see a
thousand here correct
and a thousand there correct so we hit
okay hit next
save it in flow lines and go create
and now all our flow lines barring a
small exception we'll get to in a bit
should be decent
beautiful absolutely lovely now you see
this one trap here that's kind of poking
out a little bit don't worry about him
it's fine the important point is that
all of these are now connecting up
nicely so the next thing to do here is
to create some ocean crust again no new
information here it's the same way we've
been creating Ultra cross for the past
couple of videos so time-lapse mode
engaged
foreign
foreign
crossed in now you notice I've left this
bit blank here what we have here is
basically triple Junction we have a
mid-ocean ridge coming along here and
another mid-ocean ridge coming here
meeting at a t-shape here so the way in
which we do this is kind of like we have
to do kind of manually so for each of
the six surrounding plates here we want
to select a plate say this chap here we
want to hit I on the keyboard to insert
a point we want to insert a point
somewhere in the middle here then hit V
on the keyboard and we're going to just
pull this point out somewhere in the
middle of this triangle okay and then we
just repeat that for all the surrounding
plates
Bingo triple Junction Dawn so we will
need flow lines to compensate for the
motion that's going to occur in this
little triangular section so this is
really simple just hit M on the keyboard
to bring up that point tool I can never
remember these names digitized new
multi-point geometry and all you have to
do is just plonk down a point where all
the vertices meet then go create feature
flow lines and let's say we're going to
do connecting blue to Pink here Theta
D100 to play her D300 so 100
to 300 these will begin at 850 million
years at the current time step
continuing to this future and we're
going to call these flow lines
850. and we hit next again with floor
lines we have to add points so we hit
add from 850
insert yup 850 to zero great
hit OK next and we'll save it in
flowlines create and then you repeat the
exact same process again two more times
linking first blue to green and then
green to Pink all right time-lapse mode
engaged
foreign
thing we're going to do today is we're
going to add in new subduction zones
because we have this change in motion
and some Island arcs for those new
subduction zones so as we can see
through the simulation these are moving
um this way and then the rift happens
and now this chap is moving like hard
North and this trap is moving like I
guess hard South as well so that means
there's gonna have to be subduction zone
this abduction Zone here I'm imagining
it's going to have to widen to you know
get more of a northern motion and the
same thing here if this is heading south
hard South this subduction zone is going
to have to come across here to allow for
that motion so let us go to the moment
of rifting our second rifting event 900
million years ago
okay so I'm going to select my
subduction zone here the one I want to
extend out F on the keyboard select the
selection Zone I am going to clone it is
a subduction zone it goes in the
subduction zones folder hit okay
then I'm going to hit I on my keyboard
to insert points and I'm just going to
insert some points I'm going to bring
this looking Zone around like hearsay
the way I think about is that like the
Middleton Ridge might be continuing up
and the seductions all meets it here
somewhere
something like that hit F also hit X
router and I'm just going to delete
these points away from the old
subduction zone so I just get the newly
extended bit which is this bit then I'm
going to hit f
I'm going to edit feature control or
command e and we're going to call this
subduction zone at 900.
it began live at 900 Million Years it'll
go on to the distant future and player
the is 300 correct that should be fine
okay and so now we can just you know we
can select different parts of the
console and see the dates on that it's
really just one big thing but broken
apart for the sake of chronology okay
quick check
cool I'm going to do the exact same
process here this time I'm thinking I'm
just going to bring it around I'll
continue the path that's already going
on maybe swoop it around here and bring
it back to meet the coastline here and
I'll extend it out all the way to the
end of the plate to the mid-ocean ridge
and just to be clear I'm basing all this
on feeling and trying to explain the
motion of the plates you may look at the
setup and say to yourself no these
applicant zones would need to be placed
in a different place all right so I'm
going to repeat this process just like I
did up here
cool and so no new seduction zones are
needed here because nothing has really
changed it's just it's just going west
this is just doing its thing and
remember our rule of thumb 50 million
years after subduction zone opens expect
Island arcs so the subduction zones in
the North and South opened at 900
million years ago so at 850 million
years ago we'd expect some Island arcs
so again this is not new information
that was covered in a previous video so
I'm just going to time-lapse through
this
foreign
call moving plates how to deal with
Oceanic triple Junctions adding new
subduction zones adding New Island arcs
cool in the next video we are going to
learn how to split apart microcontinent
so I'm thinking maybe down here we could
re-engage this Rift and split this thing
apart or we could maybe engage this riff
that's probably the better idea because
this content's not really doing much and
spit him apart and maybe send him on a
collision course with this continent so
lots of fun to look forward to Oh and
before I go just a quick PSA I'm going
to be in the UK starting Monday for
about 10 days so the next video is going
to be slightly delayed I'm not going to
be able to work uh whilst away from my
computer normal service resumes
thereafter anyways thank you so much for
watching folks thanks again to World
building pasta whose methodology this is
and thanks to vangu Vanguard resident
artist have a great one and until next
time
it grows
foreign