# Hurried Thoughts: Time Dilation Loop

So, you may have noticed by now that my regular habit is to do very long, intensely researched posts that have been steadily creeping up towards textbook length. It's a bit of imposing, but I usually figure it's the best way to present what are usually very complex and interrelated subject matters. On occasion though, I do have thoughts or make interesting discoveries about simpler subjects that either don't fit in with one of the larger posts I've been working on or would fit only in a post I won't be putting up for a long time. Rather than just sit on these, I figured it might be nice to occasionally throw up a quick post just quickly running over a single idea without worrying too much about polish or context.
For this first one, a thought experiment: say you're impatient to get to the future. Maybe you want to see what the technology will be like, maybe you're waiting for a return letter from your pen pal in Fomalhaut, maybe you're just impatient for the next season of *Prehistoric Planet* , who knows. Say you don't have any way to hibernate or freeze yourself, but you do have some very high-performance spacecraft on hand. So you'll figure you'll move yourself at high velocity, causing time dilation between yourself and home such that you can appear to be moving more quickly forward in time. But you don't want to get far from home, so you can't just fling yourself out into space in a straight line. You could pick some distant point and repeatedly head there and back, but then you'll spend a large portion of the trip at lower velocity as you decelerate at the end of each trip and accelerate at the start of the next one.
The best way to maximize your velocity while minimizing your displacement is to move in a circle; reaching your desired velocity and then constantly accelerating towards the center of the circle. This is basically what happens in an orbit, but in this case you're not necessarily orbiting another object, just an arbitrary point in space.  
But you're going to be feeling that acceleration, and presumably there's only so much you can handle, even if you're trying to minimize the amount of time you're spending on this journey. Thus, if you're aiming for a specific velocity, to achieve a specific rate of time dilation, and you can only handle a certain maximum acceleration, that necessarily implies a particular radius to this circle. How big will that be?
In classical mechanics, the radius of the circle is simply linked to an object's centripetal acceleration (towards the center of the circle) and tangential velocity:



*
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhrMM31lxU5iILwbge__naRgnAYji0uCQZoiUPlw2EXHu0Y-pjNzfrMIRgz_Plvi7JYaNWWctZOTuPDfHal16497yd0M8lcYBkMMbWLWwIs9IzNmAP8Vlkt71IcfmVbqDCkPzMTyszB9rd6-4Ak1QnoOXfrKgEMJ9ujBYpqHmz9M5VKycHTNp-GyLuaBw/s1600/Screenshot_22.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhrMM31lxU5iILwbge__naRgnAYji0uCQZoiUPlw2EXHu0Y-pjNzfrMIRgz_Plvi7JYaNWWctZOTuPDfHal16497yd0M8lcYBkMMbWLWwIs9IzNmAP8Vlkt71IcfmVbqDCkPzMTyszB9rd6-4Ak1QnoOXfrKgEMJ9ujBYpqHmz9M5VKycHTNp-GyLuaBw/s99/Screenshot_22.png)

*



*r* = circle radius  

*v* = tangential velocity

*a* = centripetal acceleration *  
*
But as per usual, special relativity complicates matters. As the tangential velocity approaches the speed of light, the spaceship's momentum increases in such a way that it requires greater acceleration to keep within a given circular path. [Going by this guy's numbers](https://crowlspace.com/?p=3016) (which match up with what I've seen elsewhere), the formula becomes this:
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhNtRJVZRD_U06R7LZtcEZpFHcneY3Dh4lgNhkHHPQt1zj1HvhpIuHdnFLRBVPhwgI0RfcqKypLUT_vpX0TB8LXzr9mTd0r_8DdVMqyz3ZwZZmiL8AoUOzyeEFIkFy3WgA5A1OoR887XSiipdPQ40mq1K9OQbwH0B2WJK2OhxJGl1HmOhgsdEEXIQ3Sxw/s16000/Screenshot_23.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhNtRJVZRD_U06R7LZtcEZpFHcneY3Dh4lgNhkHHPQt1zj1HvhpIuHdnFLRBVPhwgI0RfcqKypLUT_vpX0TB8LXzr9mTd0r_8DdVMqyz3ZwZZmiL8AoUOzyeEFIkFy3WgA5A1OoR887XSiipdPQ40mq1K9OQbwH0B2WJK2OhxJGl1HmOhgsdEEXIQ3Sxw/s457/Screenshot_23.png)

  

*c* = speed of light   
γ = gamma factor  
Conveniently enough, the gamma factor here is equivalent to the ratio of how quickly time appears to pass outside the spaceship relative to inside; for a gamma of 10, 10 years will pass at home for every 1 year in the spaceship. Thus, if we assume that the center of the spaceship's circle is static relative to home, such that, despite constant acceleration, the spaceship is maintaining constant relative velocity compared to home, we can take this formula to describe the circle's radius from the desired time dilation and maximum acceleration; we don't even have to bother calculating what the tangential velocity ends up being.
Thus, for a range of given accelerations and time dilation gamma factors, here are the radii of the resulting circle ("E+" here is short for "*10^" because I copied this table out of Excel):  
  
Orbit Radius (light-years) |  *  
*** |  |  |  |  |   
---|---|---|---|---|---|---  
|  Acceleration (g) |  |  |  |  |  |   
Gamma |  0.01 |  0.1 |  0.33 |  1 |  3 |  10 |  100 |  1000  
1.1 |  20.3361 |  2.03361 |  0.61625 |  0.20336 |  0.06779 |  0.02034 |  0.00203 |  0.0002  
2 |  290.516 |  29.0516 |  8.80352 |  2.90516 |  0.96839 |  0.29052 |  0.02905 |  0.00291  
5 |  2324.13 |  232.413 |  70.4282 |  23.2413 |  7.7471 |  2.32413 |  0.23241 |  0.02324  
10 |  9587.04 |  958.704 |  290.516 |  95.8704 |  31.9568 |  9.58704 |  0.9587 |  0.09587  
100 |  968291 |  96829.1 |  29342.1 |  9682.91 |  3227.64 |  968.291 |  96.8291 |  9.68291  
1000 |  9.7E+07 |  9683864 |  2934504 |  968386 |  322795 |  96838.6 |  9683.86 |  968.386  
10000 |  9.7E+09 |  9.7E+08 |  2.9E+08 |  9.7E+07 |  3.2E+07 |  9683874 |  968387 |  96838.7  
100000 |  9.7E+11 |  9.7E+10 |  2.9E+10 |  9.7E+09 |  3.2E+09 |  9.7E+08 |  9.7E+07 |  9683874  
1000000 |  9.7E+13 |  9.7E+12 |  2.9E+12 |  9.7E+11 |  3.2E+11 |  9.7E+10 |  9.7E+09 |  9.7E+08  
Not exactly encouraging, is it? For a modest gamma factor of 10 (requiring a velocity of 99.5% *c*), keeping your circle under a light-year wide requires a continuous acceleration of over 192 g. More reasonable acceleration and more useful time dilation implies quite the trip; past a gamma of a couple hundred you need to start worrying about keeping yourself in the galaxy. You might as well just go visit your friend in Fomalhaut directly.
And if you do decide to go on such a trip, you'll take quite a while for each circuit (worked out here by just finding the circumference of each circle and dividing by the velocity as determined by tanh(acosh(γ)) ):

Orbit Period, external perspective (years) |  |  |  |   
---|---|---|---|---  
|  Acceleration (g) |  |  |  |  |  |   
Gamma |  0.01 |  0.1 |  0.33 |  1 |  3 |  10 |  100 |  1000  
1.1 |  306.712 |  30.6712 |  9.29432 |  3.06712 |  1.02237 |  0.30671 |  0.03067 |  0.00307  
2 |  2107.75 |  210.775 |  63.8713 |  21.0775 |  7.02584 |  2.10775 |  0.21078 |  0.02108  
5 |  14904.1 |  1490.41 |  451.638 |  149.041 |  49.6802 |  14.9041 |  1.49041 |  0.14904  
10 |  60540.6 |  6054.06 |  1834.56 |  605.406 |  201.802 |  60.5406 |  6.05406 |  0.60541  
100 |  6084253 |  608425 |  184371 |  60842.5 |  20280.8 |  6084.25 |  608.425 |  60.8425  
1000 |  6.1E+08 |  6.1E+07 |  1.8E+07 |  6084554 |  2028185 |  608455 |  60845.5 |  6084.55  
10000 |  6.1E+10 |  6.1E+09 |  1.8E+09 |  6.1E+08 |  2E+08 |  6.1E+07 |  6084557 |  608456  
100000 |  6.1E+12 |  6.1E+11 |  1.8E+11 |  6.1E+10 |  2E+10 |  6.1E+09 |  6.1E+08 |  6.1E+07  
1000000 |  6.1E+14 |  6.1E+13 |  1.8E+13 |  6.1E+12 |  2E+12 |  6.1E+11 |  6.1E+10 |  6.1E+09  
But of course it'll be shorter in the spaceship, as that is rather the point here:  
  
Orbit Period, internal perspective (years) |  |  |  |   
---|---|---|---|---  
|  Acceleration (g) |  |  |  |  |  |   
Gamma |  0.01 |  0.1 |  0.33 |  1 |  3 |  10 |  100 |  1000  
1.1 |  278.829 |  27.8829 |  8.44938 |  2.78829 |  0.92943 |  0.27883 |  0.02788 |  0.00279  
2 |  1053.88 |  105.388 |  31.9356 |  10.5388 |  3.51292 |  1.05388 |  0.10539 |  0.01054  
5 |  2980.81 |  298.081 |  90.3276 |  29.8081 |  9.93604 |  2.98081 |  0.29808 |  0.02981  
10 |  6054.06 |  605.406 |  183.456 |  60.5406 |  20.1802 |  6.05406 |  0.60541 |  0.06054  
100 |  60842.5 |  6084.25 |  1843.71 |  608.425 |  202.808 |  60.8425 |  6.08425 |  0.60843  
1000 |  608455 |  60845.5 |  18438 |  6084.55 |  2028.18 |  608.455 |  60.8455 |  6.08455  
10000 |  6084557 |  608456 |  184381 |  60845.6 |  20281.9 |  6084.56 |  608.456 |  60.8456  
100000 |  6.1E+07 |  6084557 |  1843805 |  608456 |  202819 |  60845.6 |  6084.56 |  608.456  
1000000 |  6.1E+08 |  6.1E+07 |  1.8E+07 |  6084557 |  2028186 |  608456 |  60845.6 |  6084.56  
Still, if you want to keep acceleration under 1 g and get back home within your natural lifetime, you're probably not going to be getting more than a few centuries into the future; and that's before accounting for the time just to get up to speed. If you're an immortal who can take a trip of centuries and withstand over 10 g, you might manage millennia.  
And, of course, acceleration doesn't come free. Rocket scientists often measure a spacecraft's performance in terms of its achievable change in velocity, or delta-v. Accelerating continuously at 1 g for a full year requires almost 310,000 km/s of delta-v, which is near the limit of what could be achieved with the most powerful speculative designs for antimatter-fueled rockets. Measured in terms of delta-v expended per year passing at home, the trips with the highest gamma and lowest g are most efficient in this respect:

Delta-v per External Year (km/s) |  |  |  |  |   
---|---|---|---|---|---  
|  Acceleration (g) |  |  |  |  |  |   
Gamma |  0.01 |  0.1 |  0.33 |  1 |  3 |  10 |  100 |  1000  
1.1 |  2814.29 |  28142.9 |  92871.5 |  281429 |  844286 |  2814287 |  2.8E+07 |  2.8E+08  
2 |  1547.86 |  15478.6 |  51079.3 |  154786 |  464357 |  1547858 |  1.5E+07 |  1.5E+08  
5 |  619.143 |  6191.43 |  20431.7 |  61914.3 |  185743 |  619143 |  6191432 |  6.2E+07  
10 |  309.572 |  3095.72 |  10215.9 |  30957.2 |  92871.5 |  309572 |  3095716 |  3.1E+07  
100 |  30.9572 |  309.572 |  1021.59 |  3095.72 |  9287.15 |  30957.2 |  309572 |  3095716  
1000 |  3.09572 |  30.9572 |  102.159 |  309.572 |  928.715 |  3095.72 |  30957.2 |  309572  
10000 |  0.30957 |  3.09572 |  10.2159 |  30.9572 |  92.8715 |  309.572 |  3095.72 |  30957.2  
100000 |  0.03096 |  0.30957 |  1.02159 |  3.09572 |  9.28715 |  30.9572 |  309.572 |  3095.72  
1000000 |  0.0031 |  0.03096 |  0.10216 |  0.30957 |  0.92871 |  3.09572 |  30.9572 |  309.572  
But these are also the longest circuits; as it turns out, the total delta-v required for each circuit with a given gamma factor does not vary with acceleration; but even in the most moderate cases it well exceeds what any vessel bound by the rocket equation could realistically achieve:
|  Delta-v per  
---|---  
Gamma |  circuit (km/s)  
1.1 |  863176.736  
2 |  3262501.4  
5 |  9227747.46  
10 |  18741643.7  
100 |  188351188  
1000 |  1883605121  
10000 |  1.8836E+10  
100000 |  1.8836E+11  
1000000 |  1.8836E+12  
And, again, you have to get up to this speed first. A while back I added in some calculations for time dilation under acceleration to the [worldbuilding spreadsheet](https://www.dropbox.com/s/xvdee364tlua9re/worldbuilding%20spreadsheet.xlsx?dl=0) (in the "Unit Converters + Relativity" tab, yes I buried it a bit) for a linear case of travelling between two static locations, and much the same math can be used here:
|  |  For 1 g Acceleration |  |  For 10 g Acceleration |  |  For 100 g Acceleration**  
---|---|---|---|---|---|---  
|  Speed |  Acceleration time (years) |  delta-v |  Acceleration time (years) |  delta-v |  Acceleration time (years) |  delta-v  
Gamma |  (out of *c*) |  (internal) |  (external) |  (km/s) |  (internal) |  (external) |  (km/s) |  (internal) |  (external) |  (km/s)  
1.1 |  0.416598 |  0.4295445 |  0.4437694 |  132978.4 |  0.0429545 |  0.0443769 |  132978.4 |  0.0042954 |  0.0044377 |  132978.4  
2 |  0.866025 |  1.2753213 |  1.6772908 |  394814 |  0.1275321 |  0.1677291 |  394814 |  0.0127532 |  0.0167729 |  394814  
5 |  0.979796 |  2.2199548 |  4.7440947 |  687253.7 |  0.2219955 |  0.4744095 |  687253.7 |  0.0221995 |  0.0474409 |  687253.7  
10 |  0.994987 |  2.8985899 |  9.6353019 |  897345.6 |  0.289859 |  0.9635302 |  897345.6 |  0.0289859 |  0.096353 |  897345.6  
100 |  0.99995 |  5.130783 |  96.833585 |  1588388 |  0.5130783 |  9.6833585 |  1588388 |  0.0513078 |  0.9683359 |  1588388  
1000 |  1 - 5E-07 |  7.3605942 |  968.38379 |  2278693 |  0.7360594 |  96.838379 |  2278693 |  0.0736059 |  9.6838379 |  2278693  
10000 |  1 - 5E-09 |  9.5903816 |  9683.8428 |  2968991 |  0.9590382 |  968.38428 |  2968991 |  0.0959038 |  96.838428 |  2968991  
100000 |  1 - 5E-11 |  11.820168 |  96838.316 |  3659288 |  1.1820168 |  9683.8316 |  3659288 |  0.1182017 |  968.38316 |  3659288  
1000000 |  1 - 5E-13 |  14.05002 |  968448.75 |  4349606 |  1.405002 |  96844.875 |  4349606 |  0.1405002 |  9684.4875 |  4349606  
And, of course, you have to do the same in reverse at the end of the trip to return home.  
So, if you want to take any of these trips, you're probably going to have to break a few of the known laws of physics to make it practical, and in general this is by no means an easy way to skip forward into the future. Oh well.
A better option may be to find a large black hole and drop into low orbit of that instead; no need to keep accelerating to hold yourself in place while time-dilating, though you still could to get that little extra bit of velocity for more dilation. Either way, you may still have to pay a hefty cost in delta-v and travel time to get into and out of that orbit. But, in keeping with the spirit of this new series, I won't dig into the math for gravitational time dilation today. That's all for now.  
### [Buy me a cup of tea (on Patreon)](https://www.patreon.com/worldbuildingpasta

)
