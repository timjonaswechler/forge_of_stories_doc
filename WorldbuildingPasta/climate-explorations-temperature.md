# Climate Explorations: Temperature

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEghyCKK2w2pIfg4uHLrAHZKFIBnfinAkNEC5n0O79eRAjOfIALhLfdfZGEfBw58DfKSYNGqlaoh8G4X9OlE2BnX4PFAgEjb2oBadat7VMVNwhEKJqG7pOs8joAnRKuwrKYMq4HI9Bgd4hWTmJvv_exATrIghzWDa-IIiD9JWG5Dln_aMMMmAHEfYMUyrQ/s16000/pretty.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEghyCKK2w2pIfg4uHLrAHZKFIBnfinAkNEC5n0O79eRAjOfIALhLfdfZGEfBw58DfKSYNGqlaoh8G4X9OlE2BnX4PFAgEjb2oBadat7VMVNwhEKJqG7pOs8joAnRKuwrKYMq4HI9Bgd4hWTmJvv_exATrIghzWDa-IIiD9JWG5Dln_aMMMmAHEfYMUyrQ/s1024/pretty.png)  
---  
"True color" approximation for Earth modeled at an average of -10 °C.  
This is the first in a series of shorter posts I’ll be doing where I take the ExoPlaSim climate model (which I described [here](https://worldbuildingpasta.blogspot.com/2021/11/an-apple-pie-from-scratch-part-vi.html)) and use it to explore a broad number of interesting climate scenarios using the same standard topography. Eventually I hope to explore most of the climate forcings I discussed in [Part VIa](https://worldbuildingpasta.blogspot.com/2020/03/an-apple-pie-from-scratch-part-via.html). In this case, I'll be looking at models of climates at a range of different average temperatures, from those teetering at the edge of a snowball (and a quick look at the snowball climate itself) to those approaching a moist greenhouse.
First off, here’s my standard methodology: I’ve started by running a model at T42 resolution (64 by 128 cells) with parameters matching pre-industrial Earth, though simplified in a few places to work as a cleaner starting point:

  * flux = 1367
  * startemp = 5780
  * year = 360
  * eccentricity = 0.0
  * rotationperiod = 1.0
  * obliquity = 23.5
  * fixedorbit = True 
  * pN2 = 0.78
  * pO2 = 0.21
  * pAr = 0.01
  * ozone = True
  * wetsoil = True
  * vegetation = 2
  * initgrowth = 0.5
  * glaciers = {'toggle': True, 'mindepth': 2, 'initialh': -1}
  * physicsfilter = 'gp|exp|sp'   
Here’s the heightmap I used for topography—note that, for largely practical reasons, I won’t be adjusting sea level or the topography of glacial regions (Antarctica and Greenland) to account for ice melt or formation:
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjOa4mtUDfVQx-RLVP2MmhxVtmMzRTCesfrsQdhhg57ssB57PTqAYR2mG5Y4DMoYMPeW4ZspKIDmmNpOnKgfGG-25848-tgtt0FKg5yTV9Bb7WDHqBBCE4W88xDkMFe_5acrvBgmAkqEufZ655SiNc2-JYlwfIBvX4nG4cyNq6odR-b4UGAi2k-fSIwFA/s16000/earthscale.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjOa4mtUDfVQx-RLVP2MmhxVtmMzRTCesfrsQdhhg57ssB57PTqAYR2mG5Y4DMoYMPeW4ZspKIDmmNpOnKgfGG-25848-tgtt0FKg5yTV9Bb7WDHqBBCE4W88xDkMFe_5acrvBgmAkqEufZ655SiNc2-JYlwfIBvX4nG4cyNq6odR-b4UGAi2k-fSIwFA/s1024/earthscale.png)
At this resolution, the maximum elevation is roughly 6300 meters (I’ve also clipped the lowest land elevation to be at least 25 meters, which ensures a proper land/sea distinction with the 8-bit colors used here).
I’ll be using this model as my baseline for most of these simulations; spinning it up again, altering the parameters I want to experiment with, and then running again to balance. The results may not be quite as accurate as if I ran each model anew, but this approach saves a lot of simulation time. There are some cases where multiple models fall into a logical sequence and so I’ve run them in order (e.g. in this post, the baseline model was used as the starting point for the 10 °C model, and then the final year of the 10 °C model was used as the start for the 5 °C model, and so on). There will also be some cases (e.g. 90° obliquity) where the climate state is so distinct from modern Earth that I have spun up a new model from scratch. 
For the most part (this post being an obvious exception) I want to explore worlds with a similar overall range of temperatures to modern Earth, but many of the parameters we’ll explore have some impact on global average temperatures. As such, I’ll first run them to balance with just the experimental parameter changed, but then I’ll alter other parameters to attempt to bring the global average surface temperature back into the range of 14 to 16 °C. I’ll achieve this mostly by altering the CO2 level, but if it drops as low as 10 ppm CO2 (roughly the minimum CO2 level required for carbon-fixing photosynthesis) then I’ll leave it there and start decreasing flux of sunlight instead if further cooling is required (year length will not be altered to simulate a wider orbit; chalk it up to variances in stellar luminosity). Where multiple models are run in sequence, I’ll just retain these changes from one model to the next (e.g. if I have to lower CO2 levels for the 30° obliquity model, I’ll keep that CO2 level when starting the 45° model).
For each model, I’ll indicate the previous model used as the starting point, the final average temperature (based on the 2-meter air temperature data, as that’s close to 15 °C for our baseline model), and the CO2 level (and, where appropriate, sunlight flux) used to achieve balance.
Once a model has finally run to balance at an acceptable temperature, I’ll run it an extra 10 years to give use a good data sample for producing Koppen climate maps. I’ll do at least 2 for every model: One at the model resolution (upscaled to 512 by 1024 pixels just so it displays properly) and one interpolated up to 512 by 1024 resolution, using “dummy” sea ice and adjusting temperature by the topography in the above heightmap. I may also add other maps made in [Panoply](https://www.giss.nasa.gov/tools/panoply/) of various climate conditions (also averaged over 10 years using the eps_avg.py script I recently added to the [koppenpasta repository](https://github.com/hersfeldtn/koppenpasta)) where appropriate.
The code to achieve all this is a bit complex, so I've put together [a separate post](https://worldbuildingpasta.blogspot.com/2022/07/climate-explorations-supplement-climate.html) reviewing it for those who want to do something similar.
So let’s get started.

  * [Baseline (15 °C)](https://worldbuildingpasta.blogspot.com/2022/05/climate-explorations-temperature.html#baseline)
  * [Hot Worlds](https://worldbuildingpasta.blogspot.com/2022/05/climate-explorations-temperature.html#hotworlds)
    * [20 °C](https://worldbuildingpasta.blogspot.com/2022/05/climate-explorations-temperature.html#20c)
    * [25 °C](https://worldbuildingpasta.blogspot.com/2022/05/climate-explorations-temperature.html#25c)
    * [30 °C](https://worldbuildingpasta.blogspot.com/2022/05/climate-explorations-temperature.html#30c)
    * [40 °C](https://worldbuildingpasta.blogspot.com/2022/05/climate-explorations-temperature.html#40c)
    * [50 °C](https://worldbuildingpasta.blogspot.com/2022/05/climate-explorations-temperature.html#50c)
    * [60 °C](https://worldbuildingpasta.blogspot.com/2022/05/climate-explorations-temperature.html#60c)
  * [Cold Worlds](https://worldbuildingpasta.blogspot.com/2022/05/climate-explorations-temperature.html#coldworlds)
    * [10 °C](https://worldbuildingpasta.blogspot.com/2022/05/climate-explorations-temperature.html#10c)
    * [5 °C](https://worldbuildingpasta.blogspot.com/2022/05/climate-explorations-temperature.html#5c)
    * [0 °C](https://worldbuildingpasta.blogspot.com/2022/05/climate-explorations-temperature.html#0c)
    * [-10 °C](https://worldbuildingpasta.blogspot.com/2022/05/climate-explorations-temperature.html#n10c)
    * [-18 °C](https://worldbuildingpasta.blogspot.com/2022/05/climate-explorations-temperature.html#n18c)
    * [-60 ](https://worldbuildingpasta.blogspot.com/2022/05/climate-explorations-temperature.html#n60c)[°C ](https://worldbuildingpasta.blogspot.com/2022/05/climate-explorations-temperature.html#n60c)
## Baseline (15 °C

)



[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhheduo7OXsaQBd8KTCBja3nkjdVYyeDMJG7jmxxK3jUYVwpZe25M2YHY5dcTIytTGmY3lISgIcjBdrAfYwfZ0rRoitvUNw2kxqTmnAii_LJ661F5eDduIeS-ue4TYTvQg6rKGTnJlxYY0c4jR66jYKiMFX1l3HLCdBSRULNPcWhTs1jtoE7wBtlAdQdQ/s16000/earthbaseex.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhheduo7OXsaQBd8KTCBja3nkjdVYyeDMJG7jmxxK3jUYVwpZe25M2YHY5dcTIytTGmY3lISgIcjBdrAfYwfZ0rRoitvUNw2kxqTmnAii_LJ661F5eDduIeS-ue4TYTvQg6rKGTnJlxYY0c4jR66jYKiMFX1l3HLCdBSRULNPcWhTs1jtoE7wBtlAdQdQ/s1024/earthbaseex.png)
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiTNoQm_YtGyFVByVwu1lW9-S4MuZKPngYmrbuTOdZVfnv-sqzt3Xwffu3R_bi2ACR_hu5HngC7IVd9ppzjUv267wCkkJ28v_-xKVfd1vSCe3OlbHPnbkMGHpusk-zCQie2Hu3mXcHjr1tmlH3ildTQbacO_5tlLMJBaMC5xrjPH1bwMoWaHiiH3BgRGg/s16000/earthbaseex_interp.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiTNoQm_YtGyFVByVwu1lW9-S4MuZKPngYmrbuTOdZVfnv-sqzt3Xwffu3R_bi2ACR_hu5HngC7IVd9ppzjUv267wCkkJ28v_-xKVfd1vSCe3OlbHPnbkMGHpusk-zCQie2Hu3mXcHjr1tmlH3ildTQbacO_5tlLMJBaMC5xrjPH1bwMoWaHiiH3BgRGg/s1024/earthbaseex_interp.png)

Prior Model: None.

CO 2 Level: 300 ppm

Average Temperature : 15.5 °C This is ExoPlaSim’s best attempt to model modern Earth. There are, of course, a few differences with Earth’s actual climate:
[![](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d5/K%C3%B6ppen-Geiger_Climate_Classification_Map.png/1280px-K%C3%B6ppen-Geiger_Climate_Classification_Map.png)](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d5/K%C3%B6ppen-Geiger_Climate_Classification_Map.png/1280px-K%C3%B6ppen-Geiger_Climate_Classification_Map.png)  
---  
[Beck et al. 2018](https://www.nature.com/articles/sdata2018214)  
I already went over some of these issues in the ExoPlaSim tutorial, but in short: the ice caps are too small (though they might be larger had I started with a colder model and warmed it to this point, emulating Earth’s recent warming from an ice age), a lack of deep ocean currents leaves some areas like northern Europe too cold, the East Asian monsoon is too weak, mountains aren’t quite cold enough, and a few areas are a tad too arid. Bear all that in mind when interpreting the rest of the models in this series.
Let’s look at the key elements of climate a bit more closely:
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiLMYV0dLpF9WnhB8SMznUS3gLBfJAR-FJu1nUOQQAr2ci7nmygrpnV1Pmh_50bVlxhKfmaJb4b_nU6dNtI1Iws8Dh710q-lgmAiG_P71FQ4GqDVlopkZX8k_g3pHHXOp7lkFgeLHXYNYx97ULmYIChdf8C9Zge0Pl-oiemr-gpTBL-Qo3t06LULCMbTA/s16000/base_tas.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiLMYV0dLpF9WnhB8SMznUS3gLBfJAR-FJu1nUOQQAr2ci7nmygrpnV1Pmh_50bVlxhKfmaJb4b_nU6dNtI1Iws8Dh710q-lgmAiG_P71FQ4GqDVlopkZX8k_g3pHHXOp7lkFgeLHXYNYx97ULmYIChdf8C9Zge0Pl-oiemr-gpTBL-Qo3t06LULCMbTA/s1048/base_tas.png)  
---  
Average on top, January bottom left, July bottom right, all on the same scale. Contours on the maps correspond to the major "ticks" on the scale.  
Temperature generally remains in the range of -40 to 40 °C, with some deserts reaching over 55 °C at midday in summer and Antarctica plunging to under -80 °C in winter.
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhRDpD2cJDJak8syLHyVggTO8lu_NkanvD7R5yTGPPIzfsOR8zadu_QfMW2BqZO9KjfxpOOERZMNBfJS3Bbp5OoVVCWFPVccAgW_GewI0w3Uhm4PSHRVkXCOBesYy3iTU5fMwttNhYA7Le8igTycmvnCTjsf0D0Zeeq48GZG_8qs3M1rIEfLYQE25mKNQ/s16000/tas_error.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhRDpD2cJDJak8syLHyVggTO8lu_NkanvD7R5yTGPPIzfsOR8zadu_QfMW2BqZO9KjfxpOOERZMNBfJS3Bbp5OoVVCWFPVccAgW_GewI0w3Uhm4PSHRVkXCOBesYy3iTU5fMwttNhYA7Le8igTycmvnCTjsf0D0Zeeq48GZG_8qs3M1rIEfLYQE25mKNQ/s1040/tas_error.png)
Compared to real climate data from Earth ([from here](https://climateknowledgeportal.worldbank.org/download-data)) this is generally the right range of temperatures, but there are some systemic errors, attributable mostly to the lack of deep ocean currents: tropical landmasses tend to be 5-10 °C too warm, west-facing coastlines at high latitudes are similarly too cold. Highlands are generally modeled too hot but that's mostly down to the low resolution, and polar landmasses that should be glaciated are of course too warm.  
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiDrkHwU9eBQM3YKDEmupMwZbbf7ZdixeFkA1E02yvOJf5W1YqCy2ECe0H8BJNckassSHU61smPpygxZpOYklVD446ACxnMVOyY1NprOlFIfOqNokgu6kxeUup2RELwOctxk9d4DeRQSp_K4mjN5biuTXZpMS0d3a_S-t34mPsGs7PUPqIUXP2jK8cXHw/s16000/base_pr.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiDrkHwU9eBQM3YKDEmupMwZbbf7ZdixeFkA1E02yvOJf5W1YqCy2ECe0H8BJNckassSHU61smPpygxZpOYklVD446ACxnMVOyY1NprOlFIfOqNokgu6kxeUup2RELwOctxk9d4DeRQSp_K4mjN5biuTXZpMS0d3a_S-t34mPsGs7PUPqIUXP2jK8cXHw/s1048/base_pr.png)
Annual mean precipitation averages around 110 cm/year, reaching up to over 500 cm/year in equatorial rainforests and down to under 5 mm/year in the central Sahara. 
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiolQf52QLOFHIAYClspV9VpmXsuGaDn6Z3A08RUnsqBDJeLMwR4yqxnWHF0I1Whdj8OFrvwRgphQuJI-UYtMnuVgqkLbpqDzkQE0RODZItML-uy2m5Pcc-BWfSH6AeCskq8RMA3RfsHASKu842_Vj-1cmgqBwBoVqPFAF36_-DePRHqvwzqbanR7fbRA/s16000/pr_error.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiolQf52QLOFHIAYClspV9VpmXsuGaDn6Z3A08RUnsqBDJeLMwR4yqxnWHF0I1Whdj8OFrvwRgphQuJI-UYtMnuVgqkLbpqDzkQE0RODZItML-uy2m5Pcc-BWfSH6AeCskq8RMA3RfsHASKu842_Vj-1cmgqBwBoVqPFAF36_-DePRHqvwzqbanR7fbRA/s1040/pr_error.png)
Compared to Earth, this is about 10 cm/year too wet on average. The average position of the ITCZ is a bit south of where it should be in reality, with monsoon effects being generally too weak. Continent interiors are generally a tad too dry at low latitudes and a tad too wet at high latitudes. Combined with the discussed temperature errors, this makes the tropics a bit too arid overall.  
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjLcQDXHi4WkkpXODAyYAsfLQI3ruutNiAAhbRgCFO6KG_HDYiI_kxa1_40rznrjfGgj2ravZNo09g7WmIoQ_2Q6V0Duor18v6KT3OxhYy5CQg7eqPf1E5Qg4iNW-LxqE7wmU8CUaa9nDgMO8VjIW1RVceO3_6B-Or7UOsW_Z1L8o1eLi4avEi1g1qfwQ/s16000/base_w.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjLcQDXHi4WkkpXODAyYAsfLQI3ruutNiAAhbRgCFO6KG_HDYiI_kxa1_40rznrjfGgj2ravZNo09g7WmIoQ_2Q6V0Duor18v6KT3OxhYy5CQg7eqPf1E5Qg4iNW-LxqE7wmU8CUaa9nDgMO8VjIW1RVceO3_6B-Or7UOsW_Z1L8o1eLi4avEi1g1qfwQ/s1048/base_w.png)
Wind speed averaged about 6 m/s globally, up to 14 m/s in the Southern Ocean in winter.
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiuUjfu5vn5o9aKunnuXxVaTBDiu0A3jmN87KTiZtOqZvdbJemweMXeo_rk-l0XwKiCENT090N6-e5Cf_4KlYx0-3zi8HXwUVJ3nzLPEGxmFzbUcqNNiKaZLSUuzcefvshFGx1W_YZ6ax12CuQ5bgaWZlP_D4P4TgsH0KeuPjKcARz_SCGnFx4wPjSJ-A/s16000/base_veg.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiuUjfu5vn5o9aKunnuXxVaTBDiu0A3jmN87KTiZtOqZvdbJemweMXeo_rk-l0XwKiCENT090N6-e5Cf_4KlYx0-3zi8HXwUVJ3nzLPEGxmFzbUcqNNiKaZLSUuzcefvshFGx1W_YZ6ax12CuQ5bgaWZlP_D4P4TgsH0KeuPjKcARz_SCGnFx4wPjSJ-A/s1024/base_veg.png)
ExoPlaSim’s rather simple vegetation model does a decent enough job of reflecting the overall distribution of major forests, save for the oddities in east Africa.
# Hot World

s
## 20 °

C



[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiMtwCo53_RTV-SgRIdsb-Lud-bmA_5VMTMoAb9dBHmr0V13eRFapERDK5AXdJxQewFWPCtYtHT9dzshpon1stP1b9_1QHbDBO9Op2al8yZbG46E5-yAQ0CTBQvJ9aGySzAdbKWBurm9zkLvjopuOTJrfgJXy49sc1j41VIC8GOru2M5682fABK3xkRYw/s16000/earth20cex.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiMtwCo53_RTV-SgRIdsb-Lud-bmA_5VMTMoAb9dBHmr0V13eRFapERDK5AXdJxQewFWPCtYtHT9dzshpon1stP1b9_1QHbDBO9Op2al8yZbG46E5-yAQ0CTBQvJ9aGySzAdbKWBurm9zkLvjopuOTJrfgJXy49sc1j41VIC8GOru2M5682fABK3xkRYw/s1024/earth20cex.png)
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEizlCNUYDg8aR44rivfdzyISp7SSn7YsXUhVQRIwFEPiw2C8NHdEMrMDrfmHltrTwhIKO9qbl7fpHQp5Rb0s15k2VFyFdWJxid_MTQ5gH9pG9x9nobzUnUluqi0voYo-LtIo5UNwS3VpwuMyStJOQiXiMXf_B1IxFim2OwoSu6ixlZEorA3tpHQiUhGuw/s16000/earth20cex_interp.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEizlCNUYDg8aR44rivfdzyISp7SSn7YsXUhVQRIwFEPiw2C8NHdEMrMDrfmHltrTwhIKO9qbl7fpHQp5Rb0s15k2VFyFdWJxid_MTQ5gH9pG9x9nobzUnUluqi0voYo-LtIo5UNwS3VpwuMyStJOQiXiMXf_B1IxFim2OwoSu6ixlZEorA3tpHQiUhGuw/s1024/earth20cex_interp.png)

Prior Model : Baseline.

CO 2 Level: 550 ppm

Average Temperature : 19.8 °C This is a cool greenhouse state, last reached in the late Eocene around 40 million years ago, and roughly the average climate for the last half-billion years. Earth may return to something like this after a couple centuries of continued climate change.
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgm8pIyyG3eHjtVZJi7N49erMX_o12g2VefwDZEk86mMkHAN_J_lerqif7RJ_Ju6VeXyfv6fFBplLyrbWgXnoYH1DGHf9gyL1gOwdLwstynZ8bs2H1P0H_uMKmz73YfKcMkyapTIJKMRy7YtxvMAQItN34LOBI9wkLWbGp15VJdHDipSVWV0q21R3djkg/s16000/20c_tas.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgm8pIyyG3eHjtVZJi7N49erMX_o12g2VefwDZEk86mMkHAN_J_lerqif7RJ_Ju6VeXyfv6fFBplLyrbWgXnoYH1DGHf9gyL1gOwdLwstynZ8bs2H1P0H_uMKmz73YfKcMkyapTIJKMRy7YtxvMAQItN34LOBI9wkLWbGp15VJdHDipSVWV0q21R3djkg/s1048/20c_tas.png)
For the most part, the changes are subtle; The major climate bands have all shifted poleward, with continental climates extending into the polar landmasses, Greenland and Antarctica. There are no more permanent sea ice shelves save for a few coastal patches. The southern ice cap survives here largely because the model has been warmed from a cooler state (and I haven't lowered the elevation from the surface of the current ice cap); an initially warmer world cooled to this temperature may lack ice caps or feature far smaller ones. 
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgejgTZm-UtzKM6OqRIR1CiIr2cv9x1F-pR0T0Vsyb_0HTqB18dYVenVn_d2G0Q7HP-JkpvfPnGG9JA7mlyF4RORNgg0jruasWmAdoLt42nCo54HW83xdJE187tkYyWbPdxb9xYzlptVevoU_etYV3j_726khcITERKE9NBVJp_pEYvEadqSlFpOE9WUQ/s16000/20c_tas_rel.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgejgTZm-UtzKM6OqRIR1CiIr2cv9x1F-pR0T0Vsyb_0HTqB18dYVenVn_d2G0Q7HP-JkpvfPnGG9JA7mlyF4RORNgg0jruasWmAdoLt42nCo54HW83xdJE187tkYyWbPdxb9xYzlptVevoU_etYV3j_726khcITERKE9NBVJp_pEYvEadqSlFpOE9WUQ/s1024/20c_tas_rel.png)
Relative warming from the baseline is mostly concentrated towards the poles, up to 11 °C in some areas, while the tropics have only warmed by a few degrees—though the Sahara can now reach over 60 °C at midday in summer.
## 25 °

C



[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjmD11Kcbhl0vwSulJhjD56ZSuOVK-EjFEXNnnrX4l1CiVXo-1_MwPVdjC2kj25M-NEOeVcZjpqO04I8Ej3UhnZ-nV2bAscd709TyoNpatExUfgu6AKb3X1wqN0b5scSONxdc5IZnsV9q6SSaq51LYfBxBW_w3-SU0o0O_xl7NVYwZobPyXlEw0dLSL9g/s16000/earth25cex.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjmD11Kcbhl0vwSulJhjD56ZSuOVK-EjFEXNnnrX4l1CiVXo-1_MwPVdjC2kj25M-NEOeVcZjpqO04I8Ej3UhnZ-nV2bAscd709TyoNpatExUfgu6AKb3X1wqN0b5scSONxdc5IZnsV9q6SSaq51LYfBxBW_w3-SU0o0O_xl7NVYwZobPyXlEw0dLSL9g/s1024/earth25cex.png)
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj6a6WPE2lqf7HG0wDWwl2iZ7z9XAE0HzYZuwCASMQLLlMeoHO1lGdPV7bPrOnK8WW5jS3_taf2e9uV6ycBejTdHLk13_PJOSovfufG6wKELhTuDP8G5Jd2xX2PfhRl1iowVq5OoEqFsEW8qYADD65AtxDp0iQ3j4MJ2UB-iQ6q3FetNGX2PdssgYs19w/s16000/earth25cex_interp.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj6a6WPE2lqf7HG0wDWwl2iZ7z9XAE0HzYZuwCASMQLLlMeoHO1lGdPV7bPrOnK8WW5jS3_taf2e9uV6ycBejTdHLk13_PJOSovfufG6wKELhTuDP8G5Jd2xX2PfhRl1iowVq5OoEqFsEW8qYADD65AtxDp0iQ3j4MJ2UB-iQ6q3FetNGX2PdssgYs19w/s1024/earth25cex_interp.png)

Prior Model : 20 °C

CO 2 Level: 1060 ppm

Average Temperature : 24.6 °C This is a warm greenhouse state, last achieved during the Paleocene-Eocene Thermal Maximum, 56 million years ago.
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh23HMVRc2VcRX_eyWPPpQK6TK37MH8yXLt_0SF2eXqe8CpDsXNUx7PMxaDehupJ_jIXSVB454LZKz49FwypKn_zmTzQL2PWKKdWDWSKI7tWD5aAusuVlrlGxuzI2KuKuOMY0o6rkzpHg9wOyS78kUv1BNsPeQMTTZAsUWR8m8aDBNX8GaesL13nBgkjw/s16000/25c_tas.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh23HMVRc2VcRX_eyWPPpQK6TK37MH8yXLt_0SF2eXqe8CpDsXNUx7PMxaDehupJ_jIXSVB454LZKz49FwypKn_zmTzQL2PWKKdWDWSKI7tWD5aAusuVlrlGxuzI2KuKuOMY0o6rkzpHg9wOyS78kUv1BNsPeQMTTZAsUWR8m8aDBNX8GaesL13nBgkjw/s1048/25c_tas.png)
This is a more substantially different climate: the ice caps have disappeared completely and the polar landmasses are now vast boreal forests, with some temperate coastal regions.
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjna1LBHMGTmxKNt4QsQrnVXrsyFZrHAy6R8XyEWy_ETB-RGUn73qzhOzKcQ-aswLRzW-syi0Da-rm_X8NNg6cHf-e3eqFXHFOQkyd9HnbYzXib1MbatVg-5zaqWRM7lltQ35U2-ZKFiBmTMXVaHeUCqrhHRNJf-tvZgcNum5gfSdjlcm0fLyuwy9Unwg/s16000/25c_veg.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjna1LBHMGTmxKNt4QsQrnVXrsyFZrHAy6R8XyEWy_ETB-RGUn73qzhOzKcQ-aswLRzW-syi0Da-rm_X8NNg6cHf-e3eqFXHFOQkyd9HnbYzXib1MbatVg-5zaqWRM7lltQ35U2-ZKFiBmTMXVaHeUCqrhHRNJf-tvZgcNum5gfSdjlcm0fLyuwy9Unwg/s1024/25c_veg.png)
On the other continents winter snow and frost are largely restricted to the deep interiors. Sea ice is rare.
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjiezi7gwLwXh1QwbF1FydXVq5d7GVMmbmvb7kzl0XUghtLVnaLJNGyCeUIGWiTMivEYBVz5QblVDcO7fWSpAH-niu_Z-CtOVt1Ls12iM-ThzcGR-lNpADgryohaiYp01vzMiKA3CKZvNcYyHcQX5gWx8Gy7lVUthqf4pGspCfrsQlacfuSgef9ZMH-hA/s16000/25c_pr.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjiezi7gwLwXh1QwbF1FydXVq5d7GVMmbmvb7kzl0XUghtLVnaLJNGyCeUIGWiTMivEYBVz5QblVDcO7fWSpAH-niu_Z-CtOVt1Ls12iM-ThzcGR-lNpADgryohaiYp01vzMiKA3CKZvNcYyHcQX5gWx8Gy7lVUthqf4pGspCfrsQlacfuSgef9ZMH-hA/s1048/25c_pr.png)
This warmer climate is also wetter, with moderately smaller deserts compared to baseline and global average precipitation increased by around 25 cm/year.
## 30 °

C



[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhw2sDBOfClxAh8F33jjIdwF3uHc93XPs19hKf1-vq85qms5ZcwGymK2cL0glPl0NgWH7nOluJKpaIcDefqy5Of4x2OxTmc0isMsVSYW8c2gYrYpTqJRywbWBmZB1qRj3E3PbDJtHRN_pjF4WYI79fg4AkSwIVVX4dPpd-DuLSkoWp7HHgWK18RCN7pWQ/s16000/earth30cex.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhw2sDBOfClxAh8F33jjIdwF3uHc93XPs19hKf1-vq85qms5ZcwGymK2cL0glPl0NgWH7nOluJKpaIcDefqy5Of4x2OxTmc0isMsVSYW8c2gYrYpTqJRywbWBmZB1qRj3E3PbDJtHRN_pjF4WYI79fg4AkSwIVVX4dPpd-DuLSkoWp7HHgWK18RCN7pWQ/s1024/earth30cex.png)
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj1hc7RR74h0XvzuktimeynbyS9PcEgLqQKHttKWRoGegNaPRV6bEVFAds0mYGkzx77C7C3m7WmKbY2oSxcUg1dHUCU1BYXJT14nq2X5Bx0WEEWzYeKxFNNLm-rx_6gf6kmJjhR4HZ2SesvWazJ85WXd5Prls15_584yUJz8mG0Hz43DwPyhyJwH7hbwg/s16000/earth30cex_interp.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj1hc7RR74h0XvzuktimeynbyS9PcEgLqQKHttKWRoGegNaPRV6bEVFAds0mYGkzx77C7C3m7WmKbY2oSxcUg1dHUCU1BYXJT14nq2X5Bx0WEEWzYeKxFNNLm-rx_6gf6kmJjhR4HZ2SesvWazJ85WXd5Prls15_584yUJz8mG0Hz43DwPyhyJwH7hbwg/s1024/earth30cex_interp.png)

Prior Model : 25 °C

CO 2 Level: 1980 ppm

Average Temperature : 29.6 °C This represents an extreme hothouse state; within the last half-billion years, such temperatures may have been achieved only briefly at the end of the Permian, 251 million years ago.
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEikeiHArLbTIwzP12zGYzodOzkogj3jr88kdeX30dUkPX5Dkbif16ENRZrnlBArVCn3Nbk2UwBjpxA9oGilTOPvlAuyaV0ondC19RTM2BOrGNRCuFHuSuOJHQygKzeJ_y_CY2cUR0mffRljJJitOTz8iMXlTPeIayLY0B2XKWKfCsjVCifooj8skzUjcQ/s16000/30c_tas.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEikeiHArLbTIwzP12zGYzodOzkogj3jr88kdeX30dUkPX5Dkbif16ENRZrnlBArVCn3Nbk2UwBjpxA9oGilTOPvlAuyaV0ondC19RTM2BOrGNRCuFHuSuOJHQygKzeJ_y_CY2cUR0mffRljJJitOTz8iMXlTPeIayLY0B2XKWKfCsjVCifooj8skzUjcQ/s1048/30c_tas.png)
Much the same trends we’ve been seeing continue here: temperate regions have expanded over much of the high latitudes, and vast rainforests dominate the tropics. Much of the tropics rarely drop below 30 °C, and the deserts can reach over 70 °C in summer.
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj8844ZrvCVObuW9yStckBb154M93fOeZWeFwK5SF2OidjWb_WzNagahyTzKDXsDYrJYZ5dM4pr-S_DUjtzHc_uJDPNwBTbMa-IFcnNLhfT4B9H2XB1pAPE75TzVS4aOQ_Kt3VKOXb-k5oXp8Ggz3FeXShxfxicS8YsmYpGU75T7ApF5fNvb4hxhI6a_w/s16000/30c_pr_rel.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj8844ZrvCVObuW9yStckBb154M93fOeZWeFwK5SF2OidjWb_WzNagahyTzKDXsDYrJYZ5dM4pr-S_DUjtzHc_uJDPNwBTbMa-IFcnNLhfT4B9H2XB1pAPE75TzVS4aOQ_Kt3VKOXb-k5oXp8Ggz3FeXShxfxicS8YsmYpGU75T7ApF5fNvb4hxhI6a_w/s1024/30c_pr_rel.png)
The overall climate is, again, wetter (by 40 cm/year on average), but there’s also a notable poleward shift in the desert belts, corresponding to a slight widening of the Hadley cell.
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhg21AQCP7hnghfovweSttk85Sf8YHQbJHqNmIXq2h-ipHwZfRudRCL1-cLFxV3WeUBtDwLUZMH573b37TbCSFiitLN4rJGO3fSfwusMiL4H6qGusapASuLrhT1akjf08Ttdy7P7RwTeJtvUIX7hKLs2-0zU3Tl5Kg1W1aWTXq0FNazNfWgFq01GA8O-A/s16000/30c_w_av.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhg21AQCP7hnghfovweSttk85Sf8YHQbJHqNmIXq2h-ipHwZfRudRCL1-cLFxV3WeUBtDwLUZMH573b37TbCSFiitLN4rJGO3fSfwusMiL4H6qGusapASuLrhT1akjf08Ttdy7P7RwTeJtvUIX7hKLs2-0zU3Tl5Kg1W1aWTXq0FNazNfWgFq01GA8O-A/s1024/30c_w_av.png)
## 40 °

C



[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj9hrcbyitk8C47DfQe7vWY3cJdG29rm654uuigVw81oMGilsGir00gXPN1hKCeJqiQB70pUHs4v9xl4R5k23jtfcK0tLputrKdUyN35XTAlmb8irSHb5UBd3bbybH4pS3ko9gQ4AeXJOfhiB-rmU4YjmfFJQTOtMPwo7KkkUyhrRs768lKxO4fPK6YUg/s16000/earth40cex.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj9hrcbyitk8C47DfQe7vWY3cJdG29rm654uuigVw81oMGilsGir00gXPN1hKCeJqiQB70pUHs4v9xl4R5k23jtfcK0tLputrKdUyN35XTAlmb8irSHb5UBd3bbybH4pS3ko9gQ4AeXJOfhiB-rmU4YjmfFJQTOtMPwo7KkkUyhrRs768lKxO4fPK6YUg/s1024/earth40cex.png)
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjoYKZcqQt1hAo-WJPfc-MGbntRi-IvLvy7oXCT0YHZMAm91uqWCx4ggJhfN0c3AhoO_eQO4aU302Vkq6T6Y2iTe25PDpVVN2Bbid6waJJD5ADTd_GKH2R4FB47_YCxc46hCCh9Vwagd4vYgtL93tPpXhgJ85MxfAQxiV-frUg0BsTI_LKImTLhIUhOQA/s16000/earth40cex_interp.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjoYKZcqQt1hAo-WJPfc-MGbntRi-IvLvy7oXCT0YHZMAm91uqWCx4ggJhfN0c3AhoO_eQO4aU302Vkq6T6Y2iTe25PDpVVN2Bbid6waJJD5ADTd_GKH2R4FB47_YCxc46hCCh9Vwagd4vYgtL93tPpXhgJ85MxfAQxiV-frUg0BsTI_LKImTLhIUhOQA/s1024/earth40cex_interp.png)

Prior Model : 30 °C

CO 2 Level: 0.022 bar

Average Temperature : 39.5 °C Earth has likely never gotten this hot within at least the last billion years at least, and in general it’s likely that carbon-silicate cycling would prevent such a temperature being achieved under any normal circumstances. But a planet experiencing extreme volcanism, on its way to a moist greenhouse, or experiencing some other kind of strong climate forcings might conceivably have a climate this warm.
Note that, at this point we shouldn't put too much trust in the stated CO2 level; ExoPlaSim is probably underestimating greenhouse heating when they get this high. Fortunately that shouldn't affect the rest of the modeled climate too much.  
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjicRgaXMpiNnF9q9dz_vGVtIsTISRKzHj43dEMt7cdexx6rlfQXeV44wfZazcHJcLfkNhH4cYyc6xfJ-57Lv6twvDPUIiQidEx5RyHLo9NyH2TSEodHxuDM9DDGn7X_rDlqaNvYYyatcT1lmJJIaqIUFXTyaI70-2Xyg7-MYYzNzLK9NRg-mSzQjUHCg/s16000/40c_tas.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjicRgaXMpiNnF9q9dz_vGVtIsTISRKzHj43dEMt7cdexx6rlfQXeV44wfZazcHJcLfkNhH4cYyc6xfJ-57Lv6twvDPUIiQidEx5RyHLo9NyH2TSEodHxuDM9DDGn7X_rDlqaNvYYyatcT1lmJJIaqIUFXTyaI70-2Xyg7-MYYzNzLK9NRg-mSzQjUHCg/s1048/40c_tas.png)
This world is perhaps beginning to resemble the sci-fi “jungle planet” trope; tropical and subtropical rainforests dominate most of the continents. Still, some of the deserts have expanded as they continue to shift poleward.
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgyPtG9OH373RbiOwgQRxXMjVbYfj9f1g8w8xgHK6Aje7msPjMcZm93Hb8xR97Nnsu30Ou8ns0m3K4IdrIPpqfY76NYG7YjTv_-TJHfjXEgHURaFYpg0s9DSOHMsfP-XzDb5tkP-XTAFJF7L1a8YoEFK_2sfQfmbDZLz8hP_GCAz0mvBMkSuWoCGE0yTQ/s16000/40c_pr.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgyPtG9OH373RbiOwgQRxXMjVbYfj9f1g8w8xgHK6Aje7msPjMcZm93Hb8xR97Nnsu30Ou8ns0m3K4IdrIPpqfY76NYG7YjTv_-TJHfjXEgHURaFYpg0s9DSOHMsfP-XzDb5tkP-XTAFJF7L1a8YoEFK_2sfQfmbDZLz8hP_GCAz0mvBMkSuWoCGE0yTQ/s1048/40c_pr.png)
## 50 °

C



[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg26qS1RbZzD1gW0se5EvP-jfvUA9FZHJUaOTOllJCC8C_PJeGex40gO-dOVWkccrR33FdRkAwmurBMHw0-SwLWRVUa9IM94ZVkbXk29_zjDGZjttnuZPSbzSdlbehoPEmsmROgiM4T6o1kIJMoDPShWBcFNhKCmGxH4VQMJWPOZqb5Nj8Fn989EaPUYw/s16000/earth50cex.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg26qS1RbZzD1gW0se5EvP-jfvUA9FZHJUaOTOllJCC8C_PJeGex40gO-dOVWkccrR33FdRkAwmurBMHw0-SwLWRVUa9IM94ZVkbXk29_zjDGZjttnuZPSbzSdlbehoPEmsmROgiM4T6o1kIJMoDPShWBcFNhKCmGxH4VQMJWPOZqb5Nj8Fn989EaPUYw/s1024/earth50cex.png)
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgHSs4q534SdTLry9llGvNgEDv7wIpG9bPQSbUeYeBTqq7DYcWM4M6V68IhRyGSa4PAKXmX7cWG7So3rEgSFFuXjpZhYSN_baXE3tjSLFZrblSbBKgPMxQddIJJD7VXpQIin6Whsajd7kzqJ_YwyzxIkuAmtFQhIUK0xHjYVZdSKu6yANA9cmMgzWQabQ/s16000/earth50cex_interp.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgHSs4q534SdTLry9llGvNgEDv7wIpG9bPQSbUeYeBTqq7DYcWM4M6V68IhRyGSa4PAKXmX7cWG7So3rEgSFFuXjpZhYSN_baXE3tjSLFZrblSbBKgPMxQddIJJD7VXpQIin6Whsajd7kzqJ_YwyzxIkuAmtFQhIUK0xHjYVZdSKu6yANA9cmMgzWQabQ/s1024/earth50cex_interp.png)

Prior Model : 40 °

CO 2 Level: 0.18 bar

Average Temperature : 49.6 °C We are perhaps pushing the model past the point of reason here; there is now almost as much CO2 as oxygen in the atmosphere. Tropical rainforests dominate, but vast deserts now occupy the interiors of some continents.
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi1fK45b9f3Z3uZZUzRsO8vbaHsky_40hOb61NCgPGKUU3hfo5o1qWSUEybThxSMSlcTwKjxTxSiv7lCMJ5z6QFobvjYWYHdoM-uRC_KB-1inJTDeOyTccy1N6pbCCl0c6EflozFGtvEUvgbbhgApOI2fXmnqEUW1JbYKVP-mZ_jaPBe3kb1kGG25Kr4A/s16000/50c_tas.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi1fK45b9f3Z3uZZUzRsO8vbaHsky_40hOb61NCgPGKUU3hfo5o1qWSUEybThxSMSlcTwKjxTxSiv7lCMJ5z6QFobvjYWYHdoM-uRC_KB-1inJTDeOyTccy1N6pbCCl0c6EflozFGtvEUvgbbhgApOI2fXmnqEUW1JbYKVP-mZ_jaPBe3kb1kGG25Kr4A/s1048/50c_tas.png)  
---  
Note that I shifted the color scale.  
Snow does still fall in Antarctica in winter, though it never accumulates.
## 60 °

C



[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhOd5WKvwIsw2hhknoea-ZekgK0LZCxYh2G33md0ja2fofvIrq4gXgqm4vZXARwbl1W9kW7HNyk4c3n_smhCl_05nOR3oF-Gct9qkPvFoM2fMScTbIJMPhQzgG8zCu3Sv3JFpXj1ERn8Td74SBKklWfvyFmJgKlrFUCxohnpDzsanhjszxKhoz7tvZJ4w/s16000/earth60cex.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhOd5WKvwIsw2hhknoea-ZekgK0LZCxYh2G33md0ja2fofvIrq4gXgqm4vZXARwbl1W9kW7HNyk4c3n_smhCl_05nOR3oF-Gct9qkPvFoM2fMScTbIJMPhQzgG8zCu3Sv3JFpXj1ERn8Td74SBKklWfvyFmJgKlrFUCxohnpDzsanhjszxKhoz7tvZJ4w/s1024/earth60cex.png)


[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg2ywH9v8nQS6tck2MtbGgIdnY4-TU4aeX4ez06Yw5fHFipM-sQPUiYxUO4Pgw_MfuZ2RADHsuPdC_VSNH2YuTp_CLhUWOcILqQSdMqQZux8XV5vtUhoAZWlt6-u8PlGMCt8VBs_w2AbJ_Qi-As2jKPQRBSChTWhbEiBrAFfU2USeljBd0RtOxxOKzg1w/s16000/earth60cex_interp.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg2ywH9v8nQS6tck2MtbGgIdnY4-TU4aeX4ez06Yw5fHFipM-sQPUiYxUO4Pgw_MfuZ2RADHsuPdC_VSNH2YuTp_CLhUWOcILqQSdMqQZux8XV5vtUhoAZWlt6-u8PlGMCt8VBs_w2AbJ_Qi-As2jKPQRBSChTWhbEiBrAFfU2USeljBd0RtOxxOKzg1w/s1024/earth60cex_interp.png)

Prior Model : 50 °C

CO 2 Level: 0.65 bar

Average Temperature : 59.6 °C This is close to the maximum temperature that could be achieved before a moist greenhouse state occurs and the planet loses most of its water to space. Even Antarctica rarely drops below 20 °C in winter, and some deserts can surpass 100 °C in summer.
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj4uRwxPUsQwoBfiklmm0l3xgeevERIhK6CCRnMQF3jzRJui3u05Ja2bfHs0MwwFt1WN_CkB_XxyBDOj1YinOAK_BIhEGNjxXDm7JCpHLAG5VkV_bv4ZAxUYBW79v7mu-HxeV0usI73yhuapYYxQHwqvKm-unSEQVlzGiTcERh9UE_friRz1ueNGVfZfg/s16000/60c_tas.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj4uRwxPUsQwoBfiklmm0l3xgeevERIhK6CCRnMQF3jzRJui3u05Ja2bfHs0MwwFt1WN_CkB_XxyBDOj1YinOAK_BIhEGNjxXDm7JCpHLAG5VkV_bv4ZAxUYBW79v7mu-HxeV0usI73yhuapYYxQHwqvKm-unSEQVlzGiTcERh9UE_friRz1ueNGVfZfg/s1048/60c_tas.png)
Both the Koppen zones and ExoPlaSim’s vegetation model predict vast, thick forests, but frankly I’m not sure how reliable either model is at such extremes; plant life on Earth likely couldn’t tolerate such high temperatures, but alien life may of course find ways to adapt.
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhP8ZigOdfUKZ06UY8DZdGjh3te6I-Si50BLKXUz9nSjfWFv7__vc4RZEPuWx_9dOw9Lwl2Av_LC-7983BoxeJ07iS9Lvoxedhykc_3kfWEVx_3OeCxbhFX_rlqkRy86lLL_qA2FGBjiapqlrQeTuendpWLkg0GZBViRjUOMSTzAGyoBlk2eIBXz0tCQg/s16000/60c_pr.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhP8ZigOdfUKZ06UY8DZdGjh3te6I-Si50BLKXUz9nSjfWFv7__vc4RZEPuWx_9dOw9Lwl2Av_LC-7983BoxeJ07iS9Lvoxedhykc_3kfWEVx_3OeCxbhFX_rlqkRy86lLL_qA2FGBjiapqlrQeTuendpWLkg0GZBViRjUOMSTzAGyoBlk2eIBXz0tCQg/s1048/60c_pr.png)
The trend with precipitation continues, with a global average of around 200 cm/year and some areas averaging over 20 m/year. Even the driest regions exceed 8 cm/year, but the extreme heat and evaporation maintains vast deserts.
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjgzNQst2T0tvyJxXjLLViSXlWhiTB4Ul_bhxQOJBWgVA679hVMKi97n9Eam3L-HGExx_vBNQwCDIIIlBJwFaIzBdHr3AealnD9wMSkJ6JIgDYHkcIfI_-IfAJ5kYZlUmJ9PXn2OZtb7uDFeRYE9ZKU3jlNedPu1HhmMU4jsGZvzVLZzjmfo8o-LK5VtQ/s16000/60c_w.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjgzNQst2T0tvyJxXjLLViSXlWhiTB4Ul_bhxQOJBWgVA679hVMKi97n9Eam3L-HGExx_vBNQwCDIIIlBJwFaIzBdHr3AealnD9wMSkJ6JIgDYHkcIfI_-IfAJ5kYZlUmJ9PXn2OZtb7uDFeRYE9ZKU3jlNedPu1HhmMU4jsGZvzVLZzjmfo8o-LK5VtQ/s1048/60c_w.png)
The Hadley cells have continued to subtly expand, and extratropical winds have become much more sedate, averaging below 1 m/s in many areas.
# Cold World

s
## 10 °

C



[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgl4Y38CVngCqxTDCgdbUyHw1yRKqIZx3LG7IIia0CJgmDZ21dLH8bwvElvzYqocnrhtlWv1VDkgW43jnrvCiZmO09zMk73pY-YFVbvgeutBSD-pyGVjvDJ7DP8Rk5uOSpuDcyv7yduH2D0jaLzNefxGzOZzWnJhZLWjthAMPGU1Jxh-uEgWXjUNhP9yA/s16000/earth10cex.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgl4Y38CVngCqxTDCgdbUyHw1yRKqIZx3LG7IIia0CJgmDZ21dLH8bwvElvzYqocnrhtlWv1VDkgW43jnrvCiZmO09zMk73pY-YFVbvgeutBSD-pyGVjvDJ7DP8Rk5uOSpuDcyv7yduH2D0jaLzNefxGzOZzWnJhZLWjthAMPGU1Jxh-uEgWXjUNhP9yA/s1024/earth10cex.png)
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg9G8rAkDDN2pJqwfdaMHIIpixMRK5hf0ffQy2vqmo6W-kLz73lmNhX6mJ0kgQBsJeU8URSXma4CwpvIw_sRQ1ktZ3l51PQE59EiAMF28LagTLICSGLwb05JF6evk1Dy4pJJVexj8gtGGMkB6amWRT6-mIjhaoLvqGkqKGyQ56Y2RJeILonSGXdGUUvAg/s16000/earth10cex_interp.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg9G8rAkDDN2pJqwfdaMHIIpixMRK5hf0ffQy2vqmo6W-kLz73lmNhX6mJ0kgQBsJeU8URSXma4CwpvIw_sRQ1ktZ3l51PQE59EiAMF28LagTLICSGLwb05JF6evk1Dy4pJJVexj8gtGGMkB6amWRT6-mIjhaoLvqGkqKGyQ56Y2RJeILonSGXdGUUvAg/s1024/earth10cex_interp.png)  
---  
In all these cooler models the interpolated maps had some erroneous patches of ice-free water near the poles (in waterways too small to appear in the model) which I've removed in an image editor.  
  
  
Prior Model : Baseline

CO 2 Level: 195 ppm

Average Temperature : 10.3 °C This is about the temperature during the Last Glacial Maximum, 20,000 years ago. As you can see, the modeled extent of the ice caps is still far short of their actual extent during the ice ages.
[![](https://upload.wikimedia.org/wikipedia/commons/4/42/Northern_icesheet_hg.png)](https://upload.wikimedia.org/wikipedia/commons/4/42/Northern_icesheet_hg.png)  
---  
[Hannes Grobe, Wikimedia](https://commons.wikimedia.org/wiki/File:Northern_icesheet_hg.png)  
In this and the following models, we can expect that any actual such climate would likely have glaciers over much of the areas marked as tundra here, perhaps even beyond.
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhpxFMVZSgh_cpDX5nUvL_iwR2uu9K-66WimGGcToz2g5ytrZmy8Oq327HRhkb8K1Be4Zwav6sysYHXXLdJ5vEHe4DB_sQb2iPpAyRyZOJ-MCeoXBbPtGDjdp8Y7_MWW50S4ue2GZJmUHmx6woa7Gfc5J-BjllwJuP1PJU6bymAwldUl6_1nOJdMSKugA/s16000/10c_tas.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhpxFMVZSgh_cpDX5nUvL_iwR2uu9K-66WimGGcToz2g5ytrZmy8Oq327HRhkb8K1Be4Zwav6sysYHXXLdJ5vEHe4DB_sQb2iPpAyRyZOJ-MCeoXBbPtGDjdp8Y7_MWW50S4ue2GZJmUHmx6woa7Gfc5J-BjllwJuP1PJU6bymAwldUl6_1nOJdMSKugA/s1048/10c_tas.png)
Still, we can draw some conclusions from the general trends. Much as with warming, cooling here is concentrated towards the poles, equatorial temperatures barely affected. Thus, vast temperate regions in Europe and North America have disappeared, while the tropical band has only slightly shrunk.
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh3NetLnznPBgeTLyoPFMgMjo1Q-L3KiGSHL5NnBOZElEAucPysVMkAH6YwvWeHMFMBv6OGdXM4rYP6isG5vQCUnQloE-ZSQ7J4SdqjYPKt_ecSC5Lmm4EU8mHoce9AoPN9KX-36UCuulleghzzxLszFmBEvgebGv0aR-Qv_Jh7V3m-SxiJywYQDBdIjw/s16000/10c_tas_rel.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh3NetLnznPBgeTLyoPFMgMjo1Q-L3KiGSHL5NnBOZElEAucPysVMkAH6YwvWeHMFMBv6OGdXM4rYP6isG5vQCUnQloE-ZSQ7J4SdqjYPKt_ecSC5Lmm4EU8mHoce9AoPN9KX-36UCuulleghzzxLszFmBEvgebGv0aR-Qv_Jh7V3m-SxiJywYQDBdIjw/s1024/10c_tas_rel.png)
Many of the temperate areas that do remain are also notably drier.
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgfiI6CkLc228MdQBGJ2ff6OehnyWglcrRDm3dLtLPARcYc7UDQS4nAwaekYi5KvV4QBKjSirzstuOb6VZqUg4sITZ6vxHVtdc-ZW7h9ZwxusuUK7UzGBkancULYxC_U7461GHa8Kp-vCGm4hY8y1imRkBiPnx7napY51FWC7Tr0sTo0NbjZjfQNSnvzg/s16000/10c_pr_rel.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgfiI6CkLc228MdQBGJ2ff6OehnyWglcrRDm3dLtLPARcYc7UDQS4nAwaekYi5KvV4QBKjSirzstuOb6VZqUg4sITZ6vxHVtdc-ZW7h9ZwxusuUK7UzGBkancULYxC_U7461GHa8Kp-vCGm4hY8y1imRkBiPnx7napY51FWC7Tr0sTo0NbjZjfQNSnvzg/s1024/10c_pr_rel.png)
## 5 °

C



[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhlTzp6uJTi1tw9kbMWR3gHZyFTvTYVzxZCAppEwMldzg1lxQ4bDq9T4XTG3YI2MFCpPbSRtdFPqGkLpfQwq8ZE_ut_4tDLkrU0Lo8wrHolXEyNEgzaF6msDvPnviQBl3mIZ_zxWUed94y8XdW4OA-XcYnTsBtXjPPNSsr_w6H0OEes2Sqok1uu1eYtxA/s16000/earth5cex.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhlTzp6uJTi1tw9kbMWR3gHZyFTvTYVzxZCAppEwMldzg1lxQ4bDq9T4XTG3YI2MFCpPbSRtdFPqGkLpfQwq8ZE_ut_4tDLkrU0Lo8wrHolXEyNEgzaF6msDvPnviQBl3mIZ_zxWUed94y8XdW4OA-XcYnTsBtXjPPNSsr_w6H0OEes2Sqok1uu1eYtxA/s1024/earth5cex.png)
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh7s3hUwXUkskeF2XDmV2JX_iJWuCSrSDtyBfZmOKKgnIytrubADRNfclQ3QLyGiCDyrbMpLSfiLOo01e4DrAxCsojMGcEUQL8Gblp7zxOIubL2M7MX5fqAPTvlSBdSFHS-KSjDSxm0aqO_rjarkDbja6b2auoRLvMHKi-aSIC5wNY51wwUvzJKNIwhcg/s16000/earth5cex_interp.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh7s3hUwXUkskeF2XDmV2JX_iJWuCSrSDtyBfZmOKKgnIytrubADRNfclQ3QLyGiCDyrbMpLSfiLOo01e4DrAxCsojMGcEUQL8Gblp7zxOIubL2M7MX5fqAPTvlSBdSFHS-KSjDSxm0aqO_rjarkDbja6b2auoRLvMHKi-aSIC5wNY51wwUvzJKNIwhcg/s1024/earth5cex_interp.png)

Prior Model : 10 °C

CO 2 Level: 130 ppm

Average Temperature : 5.3 °C Temperatures this low have likely not been achieved since the Cryogenian, 635 million years ago.
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEge9DmKueGvAXcXLd7HpKwYlXkyRoSjs4TAL3ykzC3FesYjyJA65eDR_ddvXlr4KtssXAYKXgYin4WOu-NNGTlEw_wvEGNWShudeFDRJtIJhWGbO-zmVZ2Wc0fkmca0Rl7TKNsrF7nzSvD4pGzgF5whoKFEZ_8lsu4nzbYAVBGxoTRMKuzfWompIFv38w/s16000/5c_tas.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEge9DmKueGvAXcXLd7HpKwYlXkyRoSjs4TAL3ykzC3FesYjyJA65eDR_ddvXlr4KtssXAYKXgYin4WOu-NNGTlEw_wvEGNWShudeFDRJtIJhWGbO-zmVZ2Wc0fkmca0Rl7TKNsrF7nzSvD4pGzgF5whoKFEZ_8lsu4nzbYAVBGxoTRMKuzfWompIFv38w/s1048/5c_tas.png)
The shrinking of the tropical band is a bit more substantial here, and much of the high-latitude landmasses are nigh uninhabitable (and would likely be covered in much larger glaciers). The Black Sea and Adriatic freeze over in winter. In the growing ice caps, temperatures can plunge to below -100 °C in winter.
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhbD0fEg5zmE05dOwQ8Ai8-B-VF4KE-8-CU7T1LJg4P71CWpww6GT9mTLHR03DD1Qm7GBz-jjxihs_5jLsFQEOEL0m2CFGIopNVxk9swzb8aAxAZSisWWVbg6rJY-drltthPt_CxUkZypgMsQ2FEZf3jZZSa7CqPIbGv-r9glfEtMYTtcgH7qUJUIYTEA/s16000/5c_pr.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhbD0fEg5zmE05dOwQ8Ai8-B-VF4KE-8-CU7T1LJg4P71CWpww6GT9mTLHR03DD1Qm7GBz-jjxihs_5jLsFQEOEL0m2CFGIopNVxk9swzb8aAxAZSisWWVbg6rJY-drltthPt_CxUkZypgMsQ2FEZf3jZZSa7CqPIbGv-r9glfEtMYTtcgH7qUJUIYTEA/s1048/5c_pr.png)
The deserts are also clearly shifting equatorward, matching their poleward shift in the warmer models. Global average precipitation is about 20 cm/year lower than baseline. Rainforests have almost disappeared from central Africa for lack of consistent rain, replaced by savanna.
## 0 °

C



[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj-KqnV4d51kNozFvHbbAXj-F8KAoj7quhJTjc4B6WnGvbdfvi4z4htYot0sWO6XCDwTZe3nsj-DaLqTg9T5Uex-50_NJHkDmtqAAt4-_isNIB45woZwv5cYqkKaRmmv3muoHK7EtvXZV1eLPhKdTVbckPBsL_RiYluuXsgRpPJXTvVpo3RiCVwqRyLhA/s16000/earth0cex.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj-KqnV4d51kNozFvHbbAXj-F8KAoj7quhJTjc4B6WnGvbdfvi4z4htYot0sWO6XCDwTZe3nsj-DaLqTg9T5Uex-50_NJHkDmtqAAt4-_isNIB45woZwv5cYqkKaRmmv3muoHK7EtvXZV1eLPhKdTVbckPBsL_RiYluuXsgRpPJXTvVpo3RiCVwqRyLhA/s1024/earth0cex.png)
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEil3E6_m_1eOYQees_yQAG_VOCsdedpKoBoR9GniW5f-7p8MsbuIsfuIUj6g3Rt5hBcfVhBrLywGoS92ljPTuZmEyKw8Q2m_uP0HcIQGmK__nVYJWHg37gGn_4D9yhvtLDDwdy_5jXrIR9POX0IgToqro6PoMwdFSNM3x6mhGTWcxfqSpdZPLUitEHdiw/s16000/earth0cex_interp.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEil3E6_m_1eOYQees_yQAG_VOCsdedpKoBoR9GniW5f-7p8MsbuIsfuIUj6g3Rt5hBcfVhBrLywGoS92ljPTuZmEyKw8Q2m_uP0HcIQGmK__nVYJWHg37gGn_4D9yhvtLDDwdy_5jXrIR9POX0IgToqro6PoMwdFSNM3x6mhGTWcxfqSpdZPLUitEHdiw/s1024/earth0cex_interp.png)



Prior Model : 5 °C

CO 2 Level: 81 ppm

Average Temperature : 0.3 °C This is perhaps lower than we would usually expect planets stabilized by the carbon-silicate cycle to reach under normal circumstances, but it might be realistic for a planet on its way to a snowball or with very low rates of volcanism.
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiJyr0FvlpCMjzFeSuOmCJG1GiLwLdLgWrsvvt17OYLCaVup2qU8JXuUxwv2Vl-oKkb0n2fOQ1t96OI1PyntLM5O90YgxLs7Gw1K7FBL1M34rg3DKfJ3CoCQPb87BoMzhKeH3r4ork2fGqprxx8Hlq5zwqWKj6XHWES1qTOK-B8JrEBWbehewmRjb887w/s16000/0c_tas.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiJyr0FvlpCMjzFeSuOmCJG1GiLwLdLgWrsvvt17OYLCaVup2qU8JXuUxwv2Vl-oKkb0n2fOQ1t96OI1PyntLM5O90YgxLs7Gw1K7FBL1M34rg3DKfJ3CoCQPb87BoMzhKeH3r4ork2fGqprxx8Hlq5zwqWKj6XHWES1qTOK-B8JrEBWbehewmRjb887w/s1048/0c_tas.png)
The tropical zones have shrunk further, and large semi-arid and mediterranean regions have appeared around their edges. It’s worth stressing, though, that even in such a globally cold climate, there are still large rainforests in the tropics, and the desert regions can still reach up to 40 °C at midday in summer. It is a cooler, drier world, but still one with a broad range of local climates.
## -10 °

C



[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjtVKQQd56r6zn0I4OUhTMSk53ioPRnEPIbCvnzLg4aUHoavp8bV-uyxkA3OGNo2GTlPvg9QP_H8OZuqcliOVnmNJpKUfUTaACwZoaEg1lJ0ZPXFwwgzSNbfiiJZnW6twZTAFmNP9QY_BJFxk6MrZjsJ8sDmBwm0gsjnecZMvdeK6m8xHVGOZdzHUBEgQ/s16000/earthn10cex.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjtVKQQd56r6zn0I4OUhTMSk53ioPRnEPIbCvnzLg4aUHoavp8bV-uyxkA3OGNo2GTlPvg9QP_H8OZuqcliOVnmNJpKUfUTaACwZoaEg1lJ0ZPXFwwgzSNbfiiJZnW6twZTAFmNP9QY_BJFxk6MrZjsJ8sDmBwm0gsjnecZMvdeK6m8xHVGOZdzHUBEgQ/s1024/earthn10cex.png)
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgHQCag-LXkl4p86mVgAlRROjQmNj_CxgrhWARhWkAC-H4J1g3K7-wkavT9Vg9ziQetwt8FvEscT2Jv6LNlNF9ZdoPAkRY6H8IURV2mkH45nuH3vCGWGnOSeKI7QNyDv68jkowezO1DrCgyjRnzzZr5UBNTV4BKUcbnUglBi_lwaJ-aTqlxfBEcm-c-1g/s16000/earthn10cex_interp.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgHQCag-LXkl4p86mVgAlRROjQmNj_CxgrhWARhWkAC-H4J1g3K7-wkavT9Vg9ziQetwt8FvEscT2Jv6LNlNF9ZdoPAkRY6H8IURV2mkH45nuH3vCGWGnOSeKI7QNyDv68jkowezO1DrCgyjRnzzZr5UBNTV4BKUcbnUglBi_lwaJ-aTqlxfBEcm-c-1g/s1024/earthn10cex_interp.png)

Prior Model : 0 °C

CO 2 Level: 49 ppm

Average Temperature : -10.2 °C It seems that ExoPlaSim’s glacial model is finally starting to catch up with the declining temperatures: everywhere outside the former tropics is overrun by ice. Note how stark the transition from ice cap and sea ice to the more temperate climates is: with the more direct sunlight at lower latitudes, the strong contrast in albedo creates a steep temperature gradient.
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi5FVVxYQUafLBlGZkVxxmyZjmnEvO0Kiz48rtbaK_qjJ5dLivNTLwtM0r4ucfbvakYuhYWUNwS3LFlTHKeXCcMRqkWNKXuZqynIdNgrnOBxe8XOFHgtcWM6rwqGYUSiue96IqkkGR4DLfctQ9MVFgx7mDyssG_LSraIxmMibSe3XgdYhqYw3hUXMJKhQ/s16000/n10c_tas.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi5FVVxYQUafLBlGZkVxxmyZjmnEvO0Kiz48rtbaK_qjJ5dLivNTLwtM0r4ucfbvakYuhYWUNwS3LFlTHKeXCcMRqkWNKXuZqynIdNgrnOBxe8XOFHgtcWM6rwqGYUSiue96IqkkGR4DLfctQ9MVFgx7mDyssG_LSraIxmMibSe3XgdYhqYw3hUXMJKhQ/s1048/n10c_tas.png)
Meanwhile, tropical climates have near-totally disappeared. Daytime temperatures at the equator can still sometimes reach 30 °C, but the average remains below 20 °C year-round. 
## -18 °

C



[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjBg6wOo4UgsrOXILm9K0Opj_CAnWDmUkiB4juPKoca01UD3V33FQczRuHuumtCMz9T_CDgN7JU7ypGllxdFBgE_csUmdRrX9KEWFyaKXvsRgAKyIk2OYoKQS5HjpH76UQJCzO7slLpjuauqrqnDfQ8N0ukGfhtTHfCSbk6kPXLrniZkLQg-eqpXd0dPA/s16000/earthn20c40ppm.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjBg6wOo4UgsrOXILm9K0Opj_CAnWDmUkiB4juPKoca01UD3V33FQczRuHuumtCMz9T_CDgN7JU7ypGllxdFBgE_csUmdRrX9KEWFyaKXvsRgAKyIk2OYoKQS5HjpH76UQJCzO7slLpjuauqrqnDfQ8N0ukGfhtTHfCSbk6kPXLrniZkLQg-eqpXd0dPA/s1024/earthn20c40ppm.png)
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEig3D5pOi9LwJEwwrKUuPaRkfHvV_K6rPhkOV0gRHOhCy_eqlMLM_Diw2VFD_nHnl6wV5PvfPMjloZGpcPHlKSWPrC8wJwJIy_CRixB5a1PmRQzd_cyo2mTt8XCClfozP6RCaQkTxS8-dZcRIaP1P-IZt2HZvoT7pBx7ubGvX5MJdS_BRaO95cP4Z_o8w/s16000/earthn20c40ppm_interp.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEig3D5pOi9LwJEwwrKUuPaRkfHvV_K6rPhkOV0gRHOhCy_eqlMLM_Diw2VFD_nHnl6wV5PvfPMjloZGpcPHlKSWPrC8wJwJIy_CRixB5a1PmRQzd_cyo2mTt8XCClfozP6RCaQkTxS8-dZcRIaP1P-IZt2HZvoT7pBx7ubGvX5MJdS_BRaO95cP4Z_o8w/s1024/earthn20c40ppm_interp.png)

Prior Model : -10 °C

CO 2 Level: 40 ppm

Average Temperature : -18.0 °C This is about the minimum stable climate possible without plunging into a complete snowball. Indeed, I’m not even sure that this climate would be realistically stable: a drop by just a couple ppm in CO2 levels will precipitate a snowball state, and Milankovitch cycles could probably have a similar impact.
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgLf5lStAQdmQW4YiTA4lu0JBL3kdg4j33s3xgkGxXnjGl_Y8grr7s6skznahKrnpMQxNQkZ4V4GtJll3t6Cr6UrtAMcd8q_nSrbxqjyW-qYDyFjNuBPsKfml2d8_AaKUaQ4gbxQEGtygtgqr2ZiEK-ykEVxEEIODe5AAFN9hqRicvSYcnM9WLor557Rg/s16000/n18c_tas.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgLf5lStAQdmQW4YiTA4lu0JBL3kdg4j33s3xgkGxXnjGl_Y8grr7s6skznahKrnpMQxNQkZ4V4GtJll3t6Cr6UrtAMcd8q_nSrbxqjyW-qYDyFjNuBPsKfml2d8_AaKUaQ4gbxQEGtygtgqr2ZiEK-ykEVxEEIODe5AAFN9hqRicvSYcnM9WLor557Rg/s1048/n18c_tas.png)
This is a properly cold world with no warm climates. The warmest parts of the tropics are a mere 16 °C on average. Days can still reach 30 °C in summer in some areas, but nights then often plunge to below 10 °C. The ice caps, meanwhile, can plunge to below -140 °C in winter, and some areas rarely exceed -40 °C.
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjpFEQo4t11_CBAODr9UMj_kGYxCRrnvPSXVkwAsx2KVCHrR4-vyNy0MjxNyyWQ_jRgojIO0FnZipEIHau41eyNMebrkGIxEuSbgGMJRd_eJmQKiezVGK2gGfxU6e2b5zLvbWocYyb53-fZ8bnXASfbKixiutK3-U7_Qtzti243-02kHX-WnuqKP_zhIA/s16000/n18c_pr.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjpFEQo4t11_CBAODr9UMj_kGYxCRrnvPSXVkwAsx2KVCHrR4-vyNy0MjxNyyWQ_jRgojIO0FnZipEIHau41eyNMebrkGIxEuSbgGMJRd_eJmQKiezVGK2gGfxU6e2b5zLvbWocYyb53-fZ8bnXASfbKixiutK3-U7_Qtzti243-02kHX-WnuqKP_zhIA/s1048/n18c_pr.png)
And, of course, it’s drier as well: Global precipitation averages 50 cm/year, and a fairly thin and immobile ITCZ leaves much of the tropics parched for part of the year.
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiJl8wEVCrlBtHj_rbFwl-i_789QnsaN5_LMwrlXm8jQUNbdCoLSdcDL_k9yp5ZAM-xLvRcnk_JqR2UK0okzbjjsqO2_kedJYAwxJbG0lGuNxXsmcnY-6sMVjAOoTaIL5qUTSngRc1WIDtvZJ-rUXKT2wp1CT6Ko8GIE5Yz_xupjAjt4PV1AjyhUqX5Ug/s16000/n18c_w.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiJl8wEVCrlBtHj_rbFwl-i_789QnsaN5_LMwrlXm8jQUNbdCoLSdcDL_k9yp5ZAM-xLvRcnk_JqR2UK0okzbjjsqO2_kedJYAwxJbG0lGuNxXsmcnY-6sMVjAOoTaIL5qUTSngRc1WIDtvZJ-rUXKT2wp1CT6Ko8GIE5Yz_xupjAjt4PV1AjyhUqX5Ug/s1048/n18c_w.png)
Life clings to a narrow equatorial strip: Even moderate highlands in the tropics are chilly tundra, and in the lowlands only scattered forests survive between plains of grass and shrub.
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjXx8PL7dWdcxmTaoB1rhzS5sYXQvJfyCGbfoRUTam3hFL-4fyRuFNaC6IdgcNgoLJy1imtrpghldAjYxlLKdPyLuWLVdEkPdq5mqvlDurNWpmLJSmYc3KYO0hl9su5ksJktOShJacd61BjPHIQywHfn8x7SqE5SNlcytOUHbGQa7OaDtyDhmGPram8Xg/s16000/n18c_veg.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjXx8PL7dWdcxmTaoB1rhzS5sYXQvJfyCGbfoRUTam3hFL-4fyRuFNaC6IdgcNgoLJy1imtrpghldAjYxlLKdPyLuWLVdEkPdq5mqvlDurNWpmLJSmYc3KYO0hl9su5ksJktOShJacd61BjPHIQywHfn8x7SqE5SNlcytOUHbGQa7OaDtyDhmGPram8Xg/s1024/n18c_veg.png)
## -60 °

C


[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjWE4-pUVrE7k_GVAhr2iq8FpCNsEWHRKMcWE6PY_qQCGT3R35GrxleV_mfFcTf1OC6wwkd8ON3vK1vSHyBBk2f4bmBK2e6BHDrpbCwY4RRR30_m0DDG2dN9oGv_SBnUBQ3C5V2W2MpcJR7sLmXsDjSy26mzcRRXG7D7y7f0fMs8gZ8nZpO1LqAjSD1Gg/s16000/earthn20c35ppm.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjWE4-pUVrE7k_GVAhr2iq8FpCNsEWHRKMcWE6PY_qQCGT3R35GrxleV_mfFcTf1OC6wwkd8ON3vK1vSHyBBk2f4bmBK2e6BHDrpbCwY4RRR30_m0DDG2dN9oGv_SBnUBQ3C5V2W2MpcJR7sLmXsDjSy26mzcRRXG7D7y7f0fMs8gZ8nZpO1LqAjSD1Gg/s1024/earthn20c35ppm.png)  
---  
What did you expect, really?  
  
  
Prior Model : -18 °C

CO 2 Level: 35 ppm

Average Temperature : -59.6 °C The snowball. As you can see, it only took a slight drop in CO2 to cause the tropics to completely freeze over, at which point the temperature precipitously dropped to these lows within just decades. Whether or not this is actually a reasonable scenario for snowball onset or the Earth ever got quite this cold in the Cryogenian is beyond the purview of this model, but climate models do generally agree that there is a critical threshold latitude well away from the equator that glaciers cannot reach without precipitating a total freezing over of the tropics.
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgnvQVwIjI_9TNngHMDi9lq9KvrE2XlrNhs5_k8I_-K8P0AwyiPPacGSwQ6R11VqWDy_m9qdQqBYGuFjdqpQ7Y-dD1BqkcY7Iqlj_YHN-7MT3cRWhUmc3ADR8dF8N5_8g0EfxiZY_K9aXfLdjIbzZS4wB_XvKhYVESCG9-yKyjKVKEDa7sjKA7RaoMyAg/s16000/n60c_tas_av.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgnvQVwIjI_9TNngHMDi9lq9KvrE2XlrNhs5_k8I_-K8P0AwyiPPacGSwQ6R11VqWDy_m9qdQqBYGuFjdqpQ7Y-dD1BqkcY7Iqlj_YHN-7MT3cRWhUmc3ADR8dF8N5_8g0EfxiZY_K9aXfLdjIbzZS4wB_XvKhYVESCG9-yKyjKVKEDa7sjKA7RaoMyAg/s1024/n60c_tas_av.png)
Temperatures generally stay below -30 °C in summer, and can plunge to below -160 °C in polar winters. 
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEizefMz0RnzXKELG0Ikk3NLur_68FHAjgW3cpkGwDpxbRC-saNW4pnoKZ0GGnwBtJ_fzJ8eGMO-gz4rFUAnWZvmr-dVSvgKVkuu-dQ9ub-2CaXCs_6OAJoqflgKZImQQWL8bGAbh4rMSl0A7N5O2w7HdbFWiJxHunI-zHb741ZoNCMlw_V6Vor0EnLayg/s16000/n60c_pr_av.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEizefMz0RnzXKELG0Ikk3NLur_68FHAjgW3cpkGwDpxbRC-saNW4pnoKZ0GGnwBtJ_fzJ8eGMO-gz4rFUAnWZvmr-dVSvgKVkuu-dQ9ub-2CaXCs_6OAJoqflgKZImQQWL8bGAbh4rMSl0A7N5O2w7HdbFWiJxHunI-zHb741ZoNCMlw_V6Vor0EnLayg/s1024/n60c_pr_av.png)
Global snowfall averages just 6 mm/year.
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiUrfXZWjGYz7GhfJMJ6RwP_H3ZrjAXrulI0kpvg2ozud4N1JvFRv7vNrbpkEMmnrcKkPdisySkvdxi7fn_7JFoa1X-PpGPsgqmp6JlNTQ7EzsGmSyrua3C1rbdDiHeZOscizZ8x6B_XNS5Ak9pt-VWnGOvC9gLjyFO1oDm6o_nFU9MrlWC7irhH-Luwg/s16000/n60c_w.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiUrfXZWjGYz7GhfJMJ6RwP_H3ZrjAXrulI0kpvg2ozud4N1JvFRv7vNrbpkEMmnrcKkPdisySkvdxi7fn_7JFoa1X-PpGPsgqmp6JlNTQ7EzsGmSyrua3C1rbdDiHeZOscizZ8x6B_XNS5Ak9pt-VWnGOvC9gLjyFO1oDm6o_nFU9MrlWC7irhH-Luwg/s1238/n60c_w.png)
Thanks to the homogeneity and low thermal inertia of the surface, the ITCZ can move fairly far with the seasons such that there is essentially one Hadley cell that switches direction with the seasons. Extratropical winds are fairly sedate.
I did some experimentation with recovery from this snowball as well: even up to CO2 levels as high as 0.8 bar, temperatures remained below freezing year-round; at around 1 bar, the ice melts away within decades and temperatures shoot up past 60 °C. I won’t explore this process in detail here, as there are a number of feedbacks not accounted for here (buildup of dust on the ice lowering its albedo and so triggering melting sooner, immediate draw-down of CO2 once melting begins) that would make any actual such transition far gentler, but it does conform to research suggesting that recovery from a snowball should usually result in total loss of the ice caps.

* * *
That completes our tour of Earth at different temperatures. Models are already running for our next climate exploration, regarding Earth with a range of different obliquities.
### [Buy me a cup of tea (on Patreon)](https://www.patreon.com/worldbuildingpasta

)
### [Next Exploration: Obliquity ](https://worldbuildingpasta.blogspot.com/2022/08/climate-explorations-obliquity.html) 

 
