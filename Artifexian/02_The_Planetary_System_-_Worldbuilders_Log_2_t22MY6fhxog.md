# The Planetary System - Worldbuilder’s Log 2

good morning interweb world builders log
2. in the last video we built a main
sequence star in this video we're going
to wrap a planetary system around the
star
but before we do that let's talk some
follow-up
so if you recall i was humming and
hanging about the color of the star and
i got a really interesting comment from
ellis e
who has an astrophysics degree and
professional experience so they know way
more than i do ella says if you want to
know what a 3500k star looks like look
at a 3500k incandescent filament light
bulb not only is it the exact color but
it's the same brightness too
so a star of x kelvin will look exactly
like a bulb of x kelvin
class next up i mentioned i was going to
do a little reference dock for this
project i have started work on that it
looks like this um just as a placeholder
name i'm going to call the setting
artifexia that will change once we do
conlang we'll have a native term for the
world
i got some table of contents beautiful
you got a chapter marker this is very
big actually hold on let me bring us
down and then we have page one which is
the sun so this is what we did last
episode compiled into a neat format
all the red text here is stuff that's
either yet to be determined or will need
a native term down the road so if you're
interested in checking out this dock
head on over to patreon links are in the
description and there will be a card at
the end of the video final point of
follow-up is on the spreadsheet itself
lots of great positive comments which
made me feel all warm and fuzzy inside
so thank you all so much i'm glad you're
getting something out of the spreadsheet
again links in description for anyone
who wants to download it now a couple of
folks weren't able to download the
spreadsheet they followed the link but
they were met with an error message as
far as i can tell people are getting
that error message because their google
drive storage is full so the spreadsheet
is attempting to download itself into
your drive but if there's no space it'll
throw an error message so try freeing up
a bit of space and then hopefully be
able to get your hands on the sheet
certainly that fixed some of the issues
one of the patrons were having so it
might work for you keep me posted and
i'll fix things as best i can also a
couple you spotted some errors thank you
very much in the spreadsheet so i've
updated them and this is a new version
1.01 so again you may want to go and
make a new copy for yourself
all right i think that is all of the
follow-up let's get on to building a
planetary system
so as always before we build let's do a
little bit of explanation given that one
of the goals of this series is to do
everything really simplistically
we are going to aim to build a classical
planetary system and that basically is a
planetary system like the one we are
currently embedded in so you got
yourself a star
and a planetary system that is divided
into two
broad areas
an inner system and an outer system
more on that later in a classical
planetary system the inner system is
full of little rocky planets
and the outer system has your gas giants
and on top of that the orbits of these
various planets tend to be
logarithmically spaced
so for example this guy here is twice as
far out as this guy
and then this guy is twice as far out as
this guy again
etc etc
it need not be exactly twice but that's
the general kind of trend
so that is what a classical planetary
system looks like this is not the only
type of planetary system you got like
hot jupiter systems where a gas giant
forms in the outer reaches of a
planetary system and then migrates
inwards into a really tight in orbit
hence the name hot jupiter you got
systems where you have a whole bunch of
rocky worlds packed like impossibly
close to one another you got systems
with like giant gaps in the middle you
got systems with multiple asteroid belts
systems where all the bodies are on
really weird eccentric orbits there's a
whole bunch of variety out there but
again
trying to keep things simple we'll stick
with a solar system like planetary
system so all of these stats here these
should be familiar to viewers of the
last episode we already worked those out
last time we just need to input them
here again here's our first new
parameter the frost line so the frost
line is this demarcation point here
between the inner and outer system it's
the point at which volatile compounds
like water or methane ammonia carbon
dioxide that sort of thing can exist as
isis where it's cold enough for those
substances to be ices and the importance
here is that gas giants go beyond the
frost line rocky plants go starward of
the frost line now there's a couple of
complications here one there's no such
thing as a frost line like every single
volatile compound will have a different
frost line like the point of which it's
cold enough for water to become ice is
not the same point where it's cold
enough for carbon dioxide to become ice
for example so really there's like
many frost lines but here's where we're
world building and not sciencing so
we'll just simplify things and we'll say
there's one kind of general frost line
and it occurs here
further i've never found a formula for
the frost line in the literature the
formula i'm using here comes from gerp
space which is a table top role playing
manual it's worth picking yourself up a
copy it's great and in general like
draws upon established science really
well so i have no real reason to doubt
this but just heads up this isn't coming
from like literature this is coming from
a tabletop rpg manual next up we have
this section the stable orbit generator
and the way this works is the
spreadsheet uses a thing called bode's
law to generate a whole bunch of orbits
for your system and the way that bold's
law works is that it asks you to input
the orbit of your first planet in a u
and it asks you to set a sort of spacing
factor so the smaller this number the
more tightly packed orbits will be the
larger this number the more widely
spaced they'd be now it's worth noting
that bold's law despite being called law
isn't actually all that great at
predicting where planets would be
like in our system it works really well
for the inner planets but it starts to
fall apart something serious for the
outer planets so much so that people
have tried to reformulate the law but if
you look at the craziness here
i can't even begin to scrutinize this so
to keep things simple the conceit of the
spreadsheet is that in this universe
bold's law just holds because there's no
reason why it wouldn't or rather there's
no reason that it couldn't for a given
planetary system so keep things nice and
simple just bold's law holds for all
orbits now a couple of points here for
the first orbit make sure it's beyond
this point this is the point of no
return in terms of planets if planets
orbit inside this point they'll be torn
apart by your star in fact i would
suggest having your first orbit be
orders of magnitude removed from this
inner limit just to make sure you're
absolutely safe any green orbits are
orbits that fall in the habitable zone
so you can place habitable planets there
any gray orbits are orbits that fall
beyond the frost line so that's where
your gas giants will go specifically the
first orbit beyond the frost line will
likely be home to your system's largest
gas giant your jupiter analog and the
first orbit immediately before the frost
line will likely be home to an asteroid
belt the idea being that the gravity of
the very very large gas giant will
disrupt any planet that might
potentially want to form in an adjacent
orbit tear it apart and make an asteroid
belt out of it
now you'll note that there's an inner
limit here but i have no outer limit
listed that's because if you're going to
do it correctly determining the outer
limit of a planetary system is
really
really difficult it involves computing
what's known as the hill sphere of your
star which is like a bubble of space
around the star whereby if any object
were inside said bubble it would be
gravitationally bound to the star a
that's really difficult to compute and b
as far as i can tell such a bubble will
be
so large
as to be kind of meaningless so i've not
included any outer limit and i'm going
to leave it up to your discretion to
populate your orbits with an amount of
planets that you think is appropriate
i would say maybe 10 11 12 maximum
anything else on that oh yeah yeah these
are just orbits notes
so once you've generated a big list of
them you can decide at will to populate
them with planets or not so you could
say like oh there's a planet here but no
planet here there's a planet there
planet there
the asteroid belt here
gas giant here no planet no planet gas
giant and you can justify this by
invoking collisions for example like
maybe there was a planet here but
something collided with it broke it
apart all the debris got scattered or
maybe in the protoplanetary stage there
just wasn't enough stuff knocking around
that area to form a substantial body all
that sort of jazz so basically you have
free reign to pick and choose from your
list of stable orbits where you want
your bodies to go once you've done that
you can locate your outermost gas giant
so your last orbit here and if you input
it here
the spreadsheet will generate a debris
disk outward of that orbit basically
your system's kuiper belt and the way
this works is that once the spreadsheet
knows where that last gas giant is
it can find an orbit
beyond that gas giant
whereby if an object were to orbit
here it would orbit exactly two times
for every three orbits of your gas giant
we would say that the object here is
in two is to three mean motion resonance
with the gas joint
the spreadsheet will also find another
orbit beyond that
again whereby if an object were to orbit
here it would orbit one time
for every two orbits of your outermost
gas giant
i.e it would be in one is two
mean motion resonance with your gas
giant
now these two resonance orbits or
resonance lines or points or whatever
are really stable and they'll act as a
sort of corral like your gas giant will
corral a bunch of debris in between
these two lines forming
you guessed it
your system's
kuiper belt
now the spreadsheet doesn't get into it
because it's not really that important
but we'd expect there to be some sort of
like significant dwarf planet in and
around the two three mean motion
resonance point and another one around
the one is two mean motion resonance
line plus like a whole bunch extra but
like chances are there's not gonna be a
whole bunch of narrative action going on
in your system's kuiper belt so i think
it's just fine to say there exists a
debris disk it lies between here and
here and it's home to a bunch of small
dwarf planets
notably
this chap
something like that okay if i'm not
mistaken
that is the spreadsheet explained so
what i'm gonna do now is i'm gonna pop
in my star's mask that we created last
time everything will populate and we'll
see if the frost line moves out from
where it was larger star or more massive
star frost line moves out and now what
i'm going to do is i'm going to fiddle
with the first orbit and with spacing
factor until i get a spread of orbits i
like so time lapse i will see you
momentarily
okay something like that could work
so i think what i might do is i might
say that i might leave this orbit blank
um this orbit here i might say that's
home to like
a mercury type analog
um
i'll skip that orbit here's a habitable
world
again probably skip that orbit
major gas giant goes on this orbit we'll
say
and i also said i want a two to four
planet so i've got three now so
one more
will be nice
uh so let's put a minor gas giant here
and just to bring in a little bit of
interest yeah let's say that we have an
asteroid
belt here
and another one
here
and the justification here is that we're
sandwiched in between two gas giants
lots of gravity going on there so maybe
it tore apart some minor objects to form
these things now i think jupiter is at
about five au i think and i think the
asteroid belt is about 2.8 au in our
system so it's worth noting the distance
from my major gas giant to my asteroid
belt here is way more than that so i
think what i'll do to compensate just to
be safe i'll make this gas joint like
major like a lot more massive than um
than jupiter and again hopefully that
will kind of in my head justifies there
being a second asteroid asteroid belt as
well we just have an exceedingly large
gas giant here that just wrecked stuff
all around us so yeah i think that's
good
yeah so
47.57 au from my last gas giant this
fella here so let me drop that in
47
point
a u gives me a debris disc from 62 to 75
au and we'd expect there to be some sort
of dwarf planet here so i'll make a note
of that and stick it in the reference
dock all right
that's that done now
this is kind of getting a little bit
ahead of ourselves but i'd like to check
this whilst our habit world is indeed
inside the habitable zone which goes
from 1.4 au to 2au so 1.69 is definitely
in the habitable zone that just means
that it's warm enough for liquid water
to be on the surface of this planet this
planet may still be exceedingly hot or
exceedingly cold by earth standards and
what i'd like to do is i'd like to have
it be
within a degree or two of modern day
earth
such that i can draw on the various cope
and climate zones of modern day earth
etc because you know if if climate
change is taught as anything very subtle
changes to temperature can completely
wreak havoc on the planet so i want to
make sure
this can be made to be this planet can
be made to be
about 15 degrees celsius which is
the average temperature of earth so to
do that again i'm going to get a little
bit ahead of myself here i'm going to go
to the planet tab and i'm going to
import my star's mass
again so everything populates and drop
down here to physical characteristics
these cells here in fact these cells
plus this cell play a role in
determining the temperature of the
planet and so what was my where the
orbit
1.69 au so it orbits at
1.69 au
all right so it's negative three degrees
celsius on average again that is warm
enough for there to be liquid water
somewhere on the planet
but like it's going to be a cold cold
cold place
let's see if we can twiddle with stuff
to get this in and around 15 degrees so
the albedo here albedo is a measure of
how reflective or absorptive
a planet is the scale here goes from
zero to one zero is a perfect absorber
one is a perfect reflector so the earth
is 0.29 here so it absorbs
most of the
energy that hits it but some of it is
reflected back and the greenhouse effect
here is how much does the atmosphere
contribute towards heating of the planet
if you put in zero there you have no
atmosphere so there's no greenhouse
effect one is a greenhouse effect
equivalent to modern day earth and i
think it's 200 is it yeah 200 would be
the equivalent of the greenhouse effect
on venus so go don't go anywhere near
200 basically and so i'm gonna by and
large i'm gonna mess with these two uh
to change the temperature and i may
move this uh habitable world around a
little bit to do so as well i'd like to
keep the albedo earth-like as well
because the albedo is determined by the
amount of water on the planet and like
the spread of biomes so like so like how
much of the surface area is taken up but
ice caps for example would play a role
in albedo again i'd like to draw on
modern day climate zones so i i'd like
to keep this in and around here
so really i think it's these two
parameters that are main
they're the main source of changing this
temperature so again time lapse give me
a few minutes and i'll try and get this
fella
somewhere more conducive
so uh that was easy all i had to do was
nearly double the greenhouse effect and
we're basically in a modern earth range
again i'm willing to go plus or minus
one degree modern earth is 15 degrees 14
degrees suits me perfectly now that is
not to say that the greenhouse effect is
necessarily twice as strong as it is on
modern day earth i don't actually
understand the scale very well it comes
from
it comes from this
planet temperature calculator from uh
the university of indiana and i had a
look through the source code of this
page
and pulled the mats from this section
again not entirely sure what the scale
is here but it seems to get decent
results anyways in summation earth-like
albedo greenhouse effect is stronger
semi-major axis is at 1.69 au i am happy
with that and we'll explore more of this
page at a later date right well that's
that one planetary system done i am
going to head off now and start work on
the reference dock
again patreon links inscription if you
want to get your hands on it i hope you
all enjoyed and until next time
edgar out
you