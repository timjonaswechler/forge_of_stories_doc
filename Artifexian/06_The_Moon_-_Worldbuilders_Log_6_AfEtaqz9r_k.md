# The Moon - Worldbuilder’s Log 6

good morning interweb world builders log
six
after the marathon episode that was the
last video
we're going to do a slightly shorter
video today we're going to build a moon
but first as always we got to do some
follow-up big news the apparent size and
brightness tab has been completely
reworked the critical error is gone plus
there's like a whole bunch of really
cool new features
so go check it out link's in the
description there's still a few weird
edge case bugs in it but for most
applications
it's working 100 fine thank you daniel
bamberger for putting this together this
is literally none of my work it's all
him off air i made a change to our hablo
worlds rotation period in the last video
i set it at exactly 24 earth hours
so that time conversion wouldn't be an
issue but lots of people in comments
were like hey totally get where you're
coming from but how about variate just
ever so slightly you know what i think
you're right so i changed it to 22.8
earth hours which is about 96 as long as
the days on earth
so it's a little bit different but not
so different that it's going to cause
any sort of issues so thanks for
feedback folks that was cool and the
final point of follow-up is just a
clarification point on plant color now i
didn't mention this in the previous
video and it was remiss of me not to
mention it but just let me stress plants
can be basically any color you want them
to be the reason why green plants
dominate on earth is because look green
plants just happen to win out but if we
were to reroll life on earth there's a
really strong possibility that some
other pigment would become the dominant
color
it's basically just look so you can
choose whichever color you want that
said for me i really don't like that
because like all the options are no
options at least in my mind so i like to
limit myself and in general i limit
myself to two strategies so we got a
star here and let's say its peak output
is in the green wavelengths of light the
two strategies i like to limit myself to
are have plants be the same color as the
peak wavelengths of light or have them
be to complement to that color and a
refresher on color theory complementary
colors are colors that are separated by
180 degrees on the color wheel and the
rationale here is that the green plants
or the peak output color plants are
saying like oh that's a lot of radiation
coming in like i know i want to feed off
solar energy but you know that's a lot
let me block that by let me reflect
those peak wavelengths back and let me
just feed on everything else it's kind
of like the sunscreen strategy whereas
in the other strategy the rationalities
of the plants go hey that's a lot of
energy you're putting out there in the
green let me soak that in and let me
reflect back the other wavelengths of
light so in this strategy there'll be an
anti-green i.e the complement to green
and that's what panoptus five is doing
here it's going with the peak output
color the sunscreen strategy plus
modifications for atmospheric pressure
so like our sun is a g2 star i think
somewhere between g0 and g2 i can never
remember but its peak output is in the
green wavelengths of light there go
green plants but again just to stress
you can make your plants whatever color
you want all right and that i think
is follow-up done
let's go build the moon shall we so
before we start banging a load of
numbers into this moon spreadsheet we
should ask ourselves a couple of
questions firstly
do we need a moon
if so what type of moon
and also could we have multiple moons
do we need a moon answer yes
for one moons are just great
they're just really cool they help with
time keeping they illuminate the night
but most importantly of all they help
stabilize a planet's axial tilt so if a
habit of world has a
fairly massive major moon its axial tilt
won't vary a whole lot but if the
habitable world doesn't have a major
moon its axial tilt could vary wildly
and over really short periods of time
geologically speaking
which is just not great for habitability
now i have read stuff on the internet
that say that gas giants could perform a
similar stabilizing role
i'm not sure as to the veracity of such
claims and also i suspect that there's a
ton of variables involved there
so unless you really know what you're
doing your habit world is going to need
at least one major moon
one moon like moon so what are the types
of moon we can go for so broadly
speaking we can categorize moons into
two categories
major moons
and minor moons and the distinction here
is that major moons are round minor
moons are not
so major moons have enough mass for
their gravity to crush them into a round
shape they're quite massive bodies minor
moons tend to be quite low mass and so
they tend to be like irregular potato
shaped kind of objects
our moon is a major moon and the moons
of mars for example would be minor moons
and we can also categorize them by
composition you can have rocky moons and
you can have icy moons that's a gross
oversimplification of things but it just
helps in this context
in general rocky moons go in the inner
system
so star ward of the frost line and icy
moons go beyond the frost line in the
outer system
so given that habitable worlds tend to
be in the inner system your best bet is
to go with rocky major moons
and finally can a habitable world have
multiple moons
answer yes is my hubble world gonna have
multiple moons
no i'm really sorry at this point
there's three reasons why i don't want
multiple moons one it's complicated the
more bodies you add the more details you
need to know the more kind of
interactions occur it just all spirals
two this is a basic build so i'm going
to go with the basic option a habit
world with one rocky major moon
and three there's a general tendency
that the closer you get to a star
the less moons planets tend to have the
further out you get the more moons
planets tend to have
like mercury doesn't have any moons
venus doesn't have any moons earth has
one
mars has two jupiter has just loads
saturn has more than loads uh neptune
has uranus has loads neptune has loads
and pluto pluto has five
which is mad given how you know tiny it
is so therefore the most kind of
believable scenario for a habitable
world in the inner system in the
habitable zone is for it to have one
moon so i'm going to stick with that
okay so let's let's do i'm going to
explain the time first before we build
just because i think it's going to work
out handier as always there's a whole
section up here where you fill in
previously established data don't need
to talk about that because we've already
gone through it in the major moons
physical characteristics section it's
basically like a reduced planet section
from the previous spreadsheet
as always mass density radius and
gravity are like the most important
parameters to establish there's not many
constraints here with mass you want the
mass of your moon to be less than
the mass of your planet because if it
were somehow more massive than your
planet then your planet would be a moon
of your moon kind of doesn't make sense
density again we're going for a rocky
moon so we want to give it a density
indicative of that so again somewhere
between three and about the high seven
grams per centimeter cubed
closer to the three range i would say
the radius that'll play a role in
determining whether or not eclipses
total eclipses will occur on your planet
and gravity is gravity
doesn't really apply to me here but if
you were working with like a moon base
or you know you were doing an
interstellar setting and launching
rockets from the moon this would matter
same deal with escape velocity and the
albedo the albedo actually doesn't do
anything in this sheet but you can stick
it in here for the sake of posterity
then we have the orbital characteristics
this is kind of the meat and potatoes of
the sheet you need to establish your
moon semi-major axis how far it orbits
from the planet it must orbit in the
moon zone here
which whose inner limit is determined by
the roche limit so if the moon were to
orbit closer than this distance the
planet will tear the moon apart and the
outer limit here is given by the edge of
the planet's hill sphere that's the
region of space around the planet
where anything inside that region orbits
the planet for major moons you want to
be like i said beyond the inner image
but within half of the outer limit so
this value divided by two that's your
range eccentricity is how eccentric the
orbit is
just like in the last video the higher
the eccentricity the more the moon will
change size throughout the course of its
orbital period throughout the course of
the month but moons at least major moons
tend to have fairly low eccentricities
this is the periapsis how close the moon
gets to the planet this is the apoapsis
how far away the moon gets to the planet
this is the orbital inclination of your
moon with respect to the plane of the
planet so you take the center of the
star and you take the center of the
planet you draw a line between those two
that is the amount of inclination
respect to that plane the orbital
direction here would need to be prograde
major moons will almost certainly orbit
in the same direction as the planet
spins so the orbital inclination has to
be between 0 and less than 90 degrees
the orbital period is how long it takes
the boom to orbit your planet basically
how long a month is on your world
assuming you're counting months based on
the lunar cycle and for major moons if
you're doing everything correctly the
spreadsheet should spit out a rotational
period exactly equal to the orbital
period
this implies that your major moon is
tightly locked to your planet which
again almost always will be the case
that is just like our moon your moon
will present the same face to the planet
always and finally we have a tide
calculator so tight
tides are just like ridiculously
complicated to compute like
stupid complicated and as such this tide
calculator here is extremely simplistic
and it's only meant to give you like a
super vague approximation of what's
going on and the the idea here that
these ranges in meters
are a kind of rough attempt at
establishing what the tidal range is
only out in the deep open ocean
what the tides would be like at the
shores of your continents will vary
wildly depending on local geography so
for earth we're looking at spring tides
i'll explain those in a second of about
0.78 meters again that's only out in the
deep open ocean
varies wildly at the shore and we're
looking at neap tides of about 0.29
meters
i like to just keep those numbers in
mind so when i make my own moon i can
roughly gauge the sort of tidal force
that it is exerting relative to the moon
that's about
all this is useful for because again
tides are just they're just
so complicated it's not even funny so
what is a spring tide and what is a neap
tide so here we have a star here we have
the planet and here we have a moon when
the bodies are aligned like this all in
line either like this
or like this
you get spring tides the gravitational
pull of the combined sun and moon
amplify the tidal range
creating the highest heights when
they're in
these permutations neap tides will be
the weakest tides on your planet where
the tidal range is at its smallest and
this occurs when the sun the planet and
the moon form a 90 degree angle so
during we'll say first quarter
or during third quarter so we have
spring tide
neap tide
spring tide
neap tide
back to spring tide that's overly
simplistic but for our purposes it'll do
and then the spreadsheet does some
checks to see whether or not your planet
is tidally locked i.e does it present
the same face to either the moon or the
sun whichever makes more sense and we
check to see if the moon is tightly
locked and again if you're doing
everything correctly your major moon
should be tightly locked so that's the
moon spreadsheet fairly simple not too
much to compute so i'm going to go ahead
and put in the data from the previous
video
there we go that's the pertinent stellar
parameters and the pertinent havel world
parameters
now i'm actually going to skip the
physical characteristics for a second i
actually don't care that much about the
physical characteristics what i care a
lot about is the orbital characteristics
like i care about how long a month is
going to be on this world
so as it currently stands
at this semi-major axis at about just
shy of 400 000 kilometers from our habit
world we'd have an orbital period of
about 17 earth days which really isn't
great because remember a year on this
habitable world is about twice that
averts and we're looking at a shorter
month here
so we're going to have like what like 40
months in the year actually let me just
go figure that out hold on one second
i'm going to fill in the calendar sheet
for a sec
right yeah we'll be looking at about 42
months in a year
that is too much that is way too much
so i'm going to need to move our moon
outwards to increase its orbital period
let's go to um let's go to i don't know
450 000
and i'm also again i'm just glancing
here at the tide section to just see
whether or not i'm
somewhat similar to earth i don't really
care too much of the tides are stronger
or weaker i just care that they're there
and that they're of like a comparable
magnitude so anyway that's 450 000
kilometers for the semi-major axis of
our moon that brings us up to 21 earth
days 21.831
let's have a look at that
we're getting it down we're getting it
down to 33 months in the year we're
always going to have just like a lot of
months here there's not really much we
can do about it because our year is so
long but i just don't want to have to
name like 50 odd months like that's
crazy 33 is still a bit much uh let's
let me just reduce the moon's orbital
period or broader increase it and see
can we get
a slightly lower
number of months here
okay so if our moon's orbital period was
about 23.9
earth days which would equate to 25.16
local days remember the rotation period
of our planet is now not exactly equal
to earth we'd end up with about 30
months in the year that's pretty cool
and assuming we have four weeks per
month we end up with a six day week plus
some leftover that's kind of fun
um i kind of enjoy that
yeah let's see if we can get that
horrible period so back to moonsheet and
we'll just fiddle with the semi-major
axis till we get something decent
all right
23.961 let's see
point nine
six one
yeah we still got our 30 logo months
cool
all right
okay i think that's all right so our
tides now remember spring high tide and
low tide was plus or minus about not
0.78
for earth so we have
the magnitude of our tides is less
and the knee types are about the same so
what i might do to compensate is i might
actually pump up the mass of our moon
and because the more mass of the object
the more it'll be able to raise tides so
if i go to like 1.1 what do we have here
see we're increasing a little bit i'm
going to increase that even get that
let's say mid fives here i'll be happy
um
get a chunky moon i think i'm in danger
with the series of just making
everything big which i kind of want to
avoid because like
bigger is better is like a very common
trope
but it's kind of like you know if you're
going to have a high g world it's kind
of what you need to do
and go a little bit we'll go a little
bit more
and let's put in just
random decimal places to make it look
all fancy
uh
yeah
actually let's drop that a little bit
yeah that'll do i'm happy that title
range it's weaker so the tides in this
planet would be weaker because our moon
is further out but we still have
appreciable tides and that's gravy
i'm going to hold the density actually
i'm going to increase the density a
little bit just a little bit there we go
so
1.25 moon masses is what our moon is 3.5
grams per centimeter cubed we have 1.06
times the radius of our moon so it's
basically our moon and the gravity is
0.18 g so 18 that of earth cool i'm
fairly happy with that um what else do
we need to change here the eccentricity
let's take the eccentricity and let's
lower it
let's lower by go but let's do something
like that
so the moon will barely change size over
the course of its month and the
inclination again this doesn't actually
matter as long as it's between zero and
90 degrees again i'll i'll lower it
somewhat um we'll give us just a little
bit
and just to be sure our semi-major axis
is definitely beyond our inner system
and it's within half of this value
comfortably within half of that value so
we are gravy there so everything about
the sheet is gravy one last thing i want
to do is i want to check what the total
eclipse situation is on our path so we
need to pop over to the apparent size
and brightness tab i need to fill in
some data probably in the next video
we'll go through this sheet properly
and we'll go through the calendar sheet
properly in in another video but for now
i'm just going to do a little blitz
thing just to see what's going on
okay so stars mass is imported up here
our home world we're going to give it a
semi-major axis
6.9 i'll again i'll explain all this in
its own dedicated video but what we care
about now is the parent side so the
apparent size of our star is
0.663 times the sun that is our star
appears to be about two-thirds the size
of the sun as viewed from earth that's
important remember that figure let's
scroll down to the moon section here and
we'll fill in some data here so our
semi-major axis was
477 thousand
nine hundred kilometers and the radius
of our moon was 1.06
moon radii so what do we got our
apparent size is
0.85 times as big as our moon now the
cool thing about our system is that the
moon and the sun are basically the same
size when viewed from the surface of
earth so we can directly compare this
number
and this number so our sun 0.66 times
the size of the sun our moon 0.85 times
the size of our moon
which means that this moon is much much
bigger than the sun
but not much much bigger it's bigger
than the sun therefore total eclipses
are possible which is
fine a little bit sad
i was hoping i'd end up with a world
where we didn't have total eclipses but
here we are the numbers have led us this
way
sometimes just got to follow us now the
phase here this is at zero degrees this
basically means full moon again we'll
talk about this in more detail in the
next video but at full moon at a phase
of zero the brightness is 1.26 times as
bright as our moon is on earth so we
have
i'd say significantly brighter nights on
this planet and in fact we could
actually make that we could make that
more pronounced if i go up to the albedo
here if i just raise the albedo
i.e the more reflective it is
the brighter the knights will be so let
me do something like i don't know
well actually let me look at mercury
mercury is basically a glorified like
asteroid moon thing anyways like it's
barely a planet so what is it doing
uh mercury the planet cool let me look
at it look at it looks like a moon um
let me make this bigger for you guys oh
that's too big there we go um
it's
albedo
where is it albedo it's geometric albedo
that's important is
0.142
so the earth not the earth the moon is
0.113 mercury was
0.42 so they're really close anyway so
let's let's cut the difference and let's
say we make this moon
0.124
something like that so i'm envisaging if
you notice here mercury is
uh if you compare mercury with our moon
you'll see that our moon has a bunch of
like dark craters and stuff which i
presume contribute to its decreased
albedo whereas mercury at least in this
image appears to be not as heavily
crater marked with dark patches so and
its albedo is slightly higher so what
i'm envisioning here is a moon that
isn't so
pochmark it's basically in between
mercury and um our moon it's not as
pock-marked as our moon but it's not as
bare as mercury which i think i can i
can easily justify our knights will be
like you know crudely speaking 38
brighter than
night on earth i think that's really
cool i think that's really cool again
we'll talk about all of this
in a in another video in greater detail
but for now
i think
that is that
is that everything physical
characteristics we changed those orbital
characteristics we got our month down
really well
we were tied we still don't have a title
layout planet which is exactly what we
want and we have a title like moon which
is also what we want we worked on the
number of months and that came to a
satisfactory conclusion and we figured
out we have total eclipses and bright
nights yeah that's it
one moon done
i hope you enjoyed folks thank you all
so much for watching a massive shout out
again to vanga van gogh who's like the
artist on this series links in
description go check him out and again
massive shout out to daniel bamberger
for
offering to help with the apparent size
and brightness tabs all of you are the
best of people have a good one folks and
until next time
edgar out
so
you