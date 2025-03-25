# Fixes and Tweaks - Worldbuilder’s Log 4

good morning interweb world Brothers log
4 so today we are supposed to start work
on our habitable planet but I'd like to
take just another quick detour and just
polish up some of the stuff we were
doing in the previous episodes namely
I'd like to rework the Stellar
neighborhood based on your guys'
feedback and also rework the planetary
system a little bit again based on your
guys' feedback in fact I already tried
to record this episode do we those two
items of reworking and working on the
habitable planet and it just went on for
like an hour and a half and it was just
way too long so let's do the touchup
first and then we'll move on to the
habitable planet in the next video but
first as always follow up so the
spreadsheet has been updated lots of
little minor updates here and there the
big one though is the introduction of
random seed functionality in the star
system generator so if we pop on over to
the Galaxy Tab and head down to the star
system coordinate generator we see
random seed so in the last episode what
was happening is the spreadsheet was
using a random number function that was
Dynamic that is that every time you
edited any of the sheets it would update
the random number and everything would
change so shout out to Patron and
Discord user caloo who came up with a
cool way of implementing a seed and that
is you just stick in a number between 1
and 2 billion the spreadsheet takes that
number and uses it to Generate random
numbers the difference from last time is
that this is static so so I can edit the
sheet and nothing will change which I
think is a huge Plus in terms of
functionality so mass of thanks calloop
also lots of people got in touch to say
that distribution issues I was having in
the previous video were not based on the
way that Google Sheets handles random
numbers it was in fact a math error on
my part so I fixed up the math and
hopefully this will result in a stellar
neighborhood that has a more uniform
distribution I've done a little bit of
testing and it looked like that so far
so all in all star system coordinate
generator is much much better now so
thank you to everyone who emailed in and
helped out with that also lots of people
left comments to say that my worries
about star systems being too close
together are kind of unfounded star
systems can be really close together it
turns out without the gravitational
interactions between the two systems
leading to instability so again I was
worried that I would brought two star
systems very close to one another
planets would start getting knocked out
of orbit asteroids would go mental be
chaos and according to forward census
here gisa 710 in about a million years
or so is going to come within about
10,000 Au of us which is like really
close and apparently that's not going to
lead to any issues and they go on to say
that a small M dwarf could be 0.77 light
years from a star system without any
issues and that was highlighted by
others as well in comments so great so
with all that in the bag the random seed
the updates to the distribution and the
new info on star system spacing let's go
and reroll the star system coordinate
generator and remap it to get something
that hopefully looks a little bit better
now I was messing around with the seed
off air and I found one that I really
like it's
14 28 61
97 so I hit return and we generate a
whole bunch of systems so just like
before I'm going to go over to Geo bra
now head on over to the 3D
calculator input the radius of my
stellar
neighborhood which is 12 light
years head back to the sheet copy these
coordinates put them in gebra and
hopefully like I said better results so
time lapse engaged
so this guy is our closest St system so
like last time I was going to make it a
green color to make sure it sticks
out and all here is our most distant
fell so let's make him red
all right there are the Boos so that
looks a lot more even of a distribution
than last time so that's
cool very very much enjoy that
and just like last time I'm going to
copy all the systems barring the home
system barring
araxia and zero out their Zed axis so I
get to see where the system is in the
plane which again is just going to help
with the art later so not mandatory at
all just a little aid for me
okay one stad neighborhood
done yeah and everything looks to be in
order all the points in the plane are
matching up cool all right right right
so that is the Stellar neighborhood done
next up we got our planetary system so I
was thinking a lot about what the
astronomers were saying about two
asteroid belts being unstable the idea
being that you a gastr controlling two
asteroid belts like one inwards and one
outwards that's not great it's going to
be one gas giant controlling one belt so
there's a bunch of options we could do
here like for example we could have an
asteroid belt and then beyond that a gas
giant and let's say that gas giant
controls that asteroid belt and then
beyond that again we could
have a gas giant controlling a Kyper
belt that would be one option for what's
happening in our outer system we could
also do something like gas giant
controlling an asteroid belt Beyond this
and then we have
our outer gas giant controlling the
Kyper belt so those would like our one
asteroid belt options if we really
wanted to I guess we could probably do
something based on what the astronomers
were saying something like asteroid belt
gas giant that gas giant controlling the
asteroid belt and then just do another
set of that so then have another
asteroid belt with another gas giant
controlling that and then have our final
gas giant controlling the Kyper belt and
any combination thereof so again we
could have say asteroid
belt gas giant or at least a in theory
I'm sure the astronomers will let me
know if this is a whole bunch of
nonsense so asteroid belt gas giant gas
giant controlled an inner asteroid belt
then immediately another gas giant
controlling an outer asteroid belt then
another gas giant controlling a Kyper
belt now part of the goal was to try and
keep like have a fairly minimal system
so I think really these two asteroid
belts even if we could make them work
and they're um and they would be stable
I think it's just awful lot of clutter
and goes against my gold so I think
we're going to resort to the one
asteroid belt system and just because
this is a basic build I'm going to do
the most basic thing the most solar
system like and it's up to you to expand
upon that and do something more wild so
I'm going to go for that arid belt gas
giant then another gas giant then the
Kyper bu like like a minimal solar
system I was also messing around with
this off air and I found a really
interesting combination of the spacing
factor and the first orbit that I
actually like a lot better and that was
uh 1.09 as the spacing factor and
.6 as the first orbit so again this gets
me like a really tight system which I I
kind of like so we could have a rocky
planet here like a Mercury type Jazz
then we have our habitable world then we
could have another rocky planet say
here's our major gas giant cuz remember
major gas giants goes go just beyond the
frost line and so inwards of that as per
this chap here we'll get an asteroid
belt and then we have our next gas giant
we'll call it like a minor gas giant SL
maybe ice
giant depending on whether or not it's
it is uh like Saturn or like Uranus and
Neptune and then beyond that we got a
Kyper belt so we have a really tight end
system like the system extends only air
quotes out to 18 AU
which I enjoy and it means that I'm
skipping less orbits I kind of like that
so let's do that let's take our
outermost gas giant it's semi- major
axis 18.04 let's drop it into this boil
over here and we got a Kyper belt going
from 23 to 28 Au so again a really tight
little system now at the risk of losing
everyone with the mats I'd actually like
to just take a second to do some more
mats just because like we're giving all
this treatment to the Kyper belt by
figuring out where it begins and where
it ends or at least the major component
of it and with the asteroid belt we're
just like doing none of that we're just
saying it's here so let's let's do that
let's work it out and let's um figure
out exactly where it begins and where it
ends so if we check our asteroid
belt we see that it runs the main belt
anyways runs from the 2:1 mean motion
resonance point out to here which is the
four to one mean motion reson point with
Jupiter that is at the outer limit
objects orbit twice for every one orbit
of Jupiter and in the inner limit
objects orbit four times for every one
orbit of Jupiter now again keeping
things on the smaller end the scale I
might go maybe 2 to one to 3: one have a
smaller tighter asteroid belt so let's
do that and the way we work this out is
we're going to use Kepler's thirdd Law
so Kepler's Third Law is or at least one
formulation of it is the orbital period
so how long it takes your planet to
complete one orbit is equal to the
square root of its semi- major axis
cubed divided by the mass of the star
using this formulation the semi- major
axis is in AU and the mass of star is in
solar masses so our gas giant that's
controlling this asteroid belt is here
we know it's semi- major axis so let's
figure out its
period so that's going to be equal to
the square root
of the semi major axis cubed so this guy
cubed divided by the mass of the
star and that will give you an answer in
Earth
years now we want belt want the outer
limit to be at the
two is to one point the two is to one
mean motion resonance point with that
gas giant and then the belt
inner limit we want that to
be at the three is to one mean motion
resent point so to figure out the period
of each of those points it's dead easy
so we have outer
period so if one orbit is 25 years
something that completes two orbits in
that same space of time is going to have
half the year length so we simply just
take the period of the Giant and divide
it by this limit here and that gives us
12
years and then the inner
period same thing again you take the
period of the gas giant so for every one
gas giant period an object at the inner
limit of our asteroid belt completes
three orbits so we simply divide that by
three and now that we know some periods
we just convert them back into semi-
major axes to get the distance from the
beginning of our AST belt to the end of
our asteroid belt
so inner we'll call it
Au and
outer Au and to convert back we just
need to do a little bit of mats on this
to rearrange everything to get in terms
of a so that would be mass the mass of
the
star multiply by the inner period
squared and all of that raised to the 3
power
and again all of that is it's just a
rejiggering of this equation to get in
terms of
a and that means our inner limit is at
4.48 AU and let's round
that to two Sig figes and all we do is
repeat the same process for the outer
limit so again we get the mass of the
star we multiply it by the outer
period squared and the whole
Chang raised to the third power
and again we'll
round and hey Presto we got it so our
asteroid belt goes from 4.48 Au out to
5.87 Au and assuming we've done
everything correctly nine times out of
10 the orbit listed here will fall
within this Zone and if we wanted to we
could increase the size of the belt so
we could say hey maybe it's exactly like
our belt so the inner limit isine
by the fors to one mean motion resonance
point and that would increase the size
of the asteroid belt but I'm just going
to keep it to something a little bit
shorter so that is that the first of the
warts and all redo type videos of this
series it only took four episodes we got
one updated Stellar neighborhood looking
a lot nicer art will be
incoming and we got one updated
planetary system with a little bit more
detail I think looking a lot nicer art
will also be incoming and next time
we're going to move on to our habitable
World cannot wait hope you enjoyed and
until next time Ed gr out