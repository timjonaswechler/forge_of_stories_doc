# GPlates: Subduction Zones & Island Arcs - Worldbuilder’s Log 12

good morning interweb world Builders log
12. today we are going to finish up the
first 100 million years of our
simulation here by adding in subduction
zones Island arcs and setting up a new
rifting event but first there's one
thing I forgot to do in the previous
video and that is put in an additional
drift correction so if you notice if I
scroll the simulation forward all of my
consonants come back together again so
let's fix that up so I'm going to go to
my project
find the rotation file open it in a text
edit document
make it bigger make the text bigger you
know the drill and then some line breaks
just so I can see what's going on
so what we can see here is at 950
million years say take id1 was at this
set of coordinates and that's what we
put up in our drift correction but we
move the simulation forward another 15
billion years and never paste it in the
new set of coordinates so let's do that
now so I'm going to copy those
and then paste them over these in the
drift correction liner code and the same
thing for 300 here 900 million years
that's our latest time stamp I'm going
to copy it and I'm going to paste it
into the drift correction now a couple
of people in comments pointed out that
you should just be able to paste this
drift correction into the 0 million year
time Mark and everything is fine you
think that would work but it doesn't it
actually caused the whole thing to break
down the line and I'm unsure why that
occurs exactly but I think it's to do
with the fact that g plates expects us
to work backwards because like obviously
real scientists are using this so they
have Earth and they're using it to
reconstruct the history whereas we're
using it to evolve things forward and I
think in that is where the problems
start so do not touch the zero zero line
of code here really important this one
don't touch it don't touch this one
don't touch this one super important
wise things just called bananas alright
so let us now get rid of those line
breaks we don't need those anymore in
fact again G plates will shelter us if
we leave them in we're gonna save it pop
back into G plates and then hit
controller command M to bring up manage
feature collections go to our rotation
file and reboot the rotation file now
you'll see here first of all
it stays in place wonderful but all of
our flow lines have become like really
messed up this is a thing that happens
and again I don't know why
but it's a thing that we will have to
fix every so often
depending on how particular you want to
be you could just leave it I suppose so
I'm going to go back to simulation and
basically what I'm going to do is I'm
just going to re-import the flow lines
so this was covered in a previous video
so I'm just going to skip through this
real fast it's the exact same process as
when we first added flow lines
okay floor lines added now hopefully God
my timeline has gone
weird
huh I do not know why that's occurring
that's very strange okay well anyways
nothing detrimental so we'll see here
now we have two copies of the flow line
we have one that is incorrect
so for example one here you see where it
shifted and it's moving over constant
it's no good and then one that is
correct that is pointing exactly at the
vertices and if you're unsure which is
which I hit F to choose feature I'll
choose one of these one of these flow
lines here and at the bottom here it
says created 36 seconds ago as opposed
to this other flow ends up was created
eight minutes ago when I first booted up
the system so that's the old set of flow
lines so I'm just going to go over to
the right here and hit delete and now if
I zoom out we are back in a stable
situation cool let's now add in some
subduction zones these are super
important and in fact they are probably
the most important thing in the
simulation like all of the play movement
is basically driven by subduction zones
so the whole simulation process can
basically be boiled down to one question
where should subduction zones go what
movement is caused by them what's
feeding them if you think of nothing
else but the subduction zones your
tectonic simulation is going to be solid
so to do this I'm going to scrub through
my timeline and get a feel for the rough
directionality of my Continental
movements
so I can see that the top continent here
it is moving kind of North East in a
Northeast sort of Direction
roughly
my bottom continent at the start it's a
bit southernly and then it kind of just
flattens out and kind of just goes west
so Western continent is moving just
straight west we'll say and Eastern
continent is moving Northeast and what
we're going to do is we're going to
place subduction zones along the Leading
Edge of the continent because the
subduction zone again is a plate
boundary in this case an oceanic
continental Convergent Zone continents
are going actually I should demonstrate
this continents are going that way
roughly
and this old ocean is going
that away and this has to occur because
as new ocean crust is created something
else has got to be destroyed and that
destruction is happening here and that's
making these continents move so we'll go
back to our server timeline
you want to input your seduction zones
at the moment of rifting so we know that
rifting occurred immediately it started
simulation here at a thousand million
years ago so we're going to put them in
here I'm going to take a screenshot and
pop into illustrator just to graphically
show you kind of my mental methodology
for doing this so here we are in
illustrator there's our super content to
start this is the rough Western motion
here this is kind of rough nor Eastern
motion and what I do in my head is I
take each of these points along the kind
of Leading Edge of the continent and I
mentally just extrapolate them outwards
in the direction of the motion and then
I seek to draw a subduction zone that
intersects each of these points and that
for the most part hugs the coastline
think South America but if you have like
dips and bays and stuff here you can
kind of cut across it if you so desire
and at the end you can kind of Trail it
a little bit there's like artistic
interpretation
um here available to you but the key key
point is that it has to intersect each
of these kind of mentally mapped lines
otherwise because again the subduction
zone is a thing that is dragging the
consonant along if it doesn't intersect
one of these lines this point is not
being dragged along so hopefully that
makes sense and you can see the same
thing in the western content I drew out
a bunch of lines again I would be doing
this in my head in the direction that
the content is moving and then I draw a
subduction zone that more or less hugs
the coast and ensuring that I intersect
each of these lines and once you got
that you're in the ballpark of realism
so let's implement this in G plate so
again back at the moment of rifting a
thousand million years ago as soon as
the rifting starts there will be
subduction zones so I'm gonna hit L on
my keyboard to bring up the digitized
new polyline tool and let's start with
the Eastern content let's draw in this
subduction zone so something
kinda like
this
something sword like that maybe maybe
like that
doesn't look too bad okay once I'm happy
with that I'm gonna go create feature
this is a subduction zone a zone of
descending lithospheric plate the plate
ID well it is attached to the quantum
with the big crate on here and that had
a player ID of 300 so we're going to
give it a playerity of 300. it starts at
a thousand million years ago when the
rifting starts and it continues into the
distant future and it is going to be
called
subductions on 1000.
hit next
doesn't matter about any of this hit
next and then we'll create a new feature
collection create and save and we will
save up our flow lines and we will save
our new feature collection as subduction
zone
cool all right so save perfect and if
assuming we've done everything correctly
the subduction zone will get the plate
ID color of the big Craton and it will
move with our continent
boom
beautiful let's repeat that process for
the other side I'll time lapse Drew this
because it's literally the same process
I suppose we're pointing out here again
it's attached to this continent we
wanted to move with this Continental
player ID of 100 to match up with the
crate on here and again called
subduction zone 1000.
bingo all right let's check that out
perfect so what we've created is
basically two South Americas we have a
mid-ocean ridge some continent and then
a subduction zone a mid-ocean ridge some
continent and then just hugging the
shore a subduction zone so that means
much like South America these two
continents will have Andean style
orogeny going on here so Andes like
Mountain chains same thing would occur
up here and a little bit here we will
talk about those later for now what
we're going to do is put in some Island
chains so for example over here
we have a small section here with a
boundary that is oceanic Oceanic
convergent remember this continent is
going this way it is overriding this old
ocean crust that Autumn crust is being
subducted so on the trailing edge here
inside of the Stockton Zone we would
expect Island arcs to form volcanic
island arcs same thing would occur down
here
and same thing would occur to a lesser
extent up here so what I want to do is
go back to when the stocks and zones
first appear in this case the beginning
of the simulation and then skip forward
50 million years
rule of Tom 50 million years after the
subduction zones open the first island
arcs will begin to form so I'm going to
hit G on the keyboard to bring up the
digitized new polygon tool I'm going to
zoom in lots
and I'm going to drop in
a small island arc and so what I'm going
to do is I'm going to draw half of the
island like so you'd imagine it'll go
around like this and then I'm going to
draw a line
and draw the other half of the an island
and then let's call it there and then
finish off the other side and come back
around
the reason for this is that we then
don't have to draw each individual
Little Island which is an absolute pain
and to go through all the menus to
make them features and add them the
features collections it's just a
nightmare so draw it has one object
that's just connected something like
that on the trailing Edge so again just
to make absolutely clear this is a
section of oceanic crust it is going
this way this is all Shannon crossed it
is going this way this plate is
overriding that plate so it sinks under
and causes volcanism on the trading Edge
very important
okay I'm happy with that so I'm going to
go to create feature
this is an island arc a type of volcanic
Arc formed by plate tectonics as an
oceanic plate docks under another and
produces magma which Rises to form the
arc cool hit next plate ID it has to
move with this continent so it's going
to get a player D of 100 same as this
plate or this crate on here it begins
not a thousand million years ago rather
at 950 million years and it'll continue
to distant future and we'll call this
island arc
9.50 cool oh just a quick thing here if
you use non-latin characters G plates
might shouted you and it might cause
issues so like Cyrillic characters for
example could cause problems
just heads up a few people have spotted
that anyways hit next it doesn't matter
about this hit next and we'll create a
new feature collection create and save
and we are going to call this where is
it here new feature collection we're
going to save this as
Island arcs cool
Don and we may as well save subductions
are done
okay I'm going to go over here and we're
going to repeat this process
so I'm gonna go g on the keyboard for
the digitized new polygon tool and I'm
going to run a string of Island arcs up
here now these Island arcs or these
volcanic islands they can attach to the
mainland every so often like a little
spur so I think it might be a cool idea
based on nothing but like the rule of
cool to have an island arc and an island
arc attached to the mainland here so
that'll be one half of it straight line
next half of us straight line and put
another Island here
and we do a straight line it's a bit
tight
another one here
and we'll continue up to maybe here
something like that and then I'm going
to close the loop
on to the other side
okay cool hey create feature island arc
play ID of 300.
island arc at 950 forms at 950 Coco cool
next doesn't matter this next and put it
in the iron dark folder and hit create
and then I will plop another one here as
well so same process all time lapse
through this
all right gravy let's have a look
beautiful so a couple of points on these
Island arcs these are the primary way in
which new crust is created so if you
recall back a couple of videos ago when
we started this process off I said that
if you want to imitate Earth-like
conditions about 25 of the surface of
your planet should be covered in your
supercontinent now the eagle-eyed
amongst you will notice that modern
Earth has about 30 percent land cover
which is a five percent increase and for
a second if we leave aside things like
sea level rise the way you get more land
is true Island arcs so these will like
grow over time and then like eventually
might smash into another continent
fusing with it creating more land so
they're really important in the
evolution process and the other
important thing about them is that these
aren't really the actual shape of these
Island arcs they're more like abstract
representations of them because every
time step or every million years or so
these will grow more volcanism will
occur this island will get bigger and
bigger and bigger and the longer this
subduction zone remains active the
bigger these will get and it would be an
absolute pain to have to increase the
size of these at each time steps so we
just kind of dot them in when they first
form and then let them be and only when
it comes to when they caliber continent
or at the end of the simulation if they
survive to the modern world do we stop
and take stock about how long they've
been around and then kind of figure out
the how big they would be so not literal
Island arcs just abstract
representations thereof and just a
little quick aside these are the
Aleutian Islands of the coast of Alaska
and Russia here we have a big old
subduction zone here and we have an
island arc chain formed like so this is
what you would typically expect for a
relatively young island arc so say
something that's only about like 50
million years old more or less isolated
little dots of islands that more or less
follow a line but not strictly if you're
a real stickler for the measurements
they usually occur about 100 to 300
kilometers from the trench itself inward
of of the trench so the trailing Edge at
the space about maybe 20 to 100
kilometers apart and each individual
Island at this stage in a relatively
young island arc chain can be about
maybe 10 to 20 kilometers across as
standard but you can get as low as just
like less than a kilometer and up to
about 100 kilometers and in terms of
elevation you're looking at maybe about
500 to a kilometer above sea level but
again you can have some outliers that go
up to about two kilometers and obviously
some of the islands can just barely
reach above sea level that's kind of
what you'd expect for a young island
chain and this is kind of what we're
using as our like abstract
representation of the island chains now
if the tectonic activity continues for
you know another several tens of
millions of years you might end up with
something like the Philippine Islands so
like if your island arc is about 100
million years old or so it could look a
little bit like this more land has been
created you can see the development of
like planes in between the Peaks so you
don't just have like little small
volcanic Peaks as Islands you kind of
get proper land masses some of the
larger islands in this sort of stage of
the volcanic island arc's lifespan could
be you know a thousand kilometers long
something like that several hundred
kilometers wide maybe two to three
kilometers high but you still have a
bunch of little islands that are way way
smaller and more akin to a young
volcanic island arc that's kind of like
an intermediary stage and then finally
if the volcanic island arc survives for
a long long time like several hundreds
of millions of years you get Indonesia
basically a new continent you'll get
proper like Andean style of rajini here
with a sort of Plains region behind the
mountain chain you can expect like a few
very very large islands like over a
thousand kilometers long though they're
usually not more than a couple hundred
kilometers wide and they you know and
the mountains can get real high like
over three kilometers or so at their
tallest that sort of thing so that that
would be the mature stage but like I
said for now we're just sketching in the
abstract representation of Island arcs
we're worried about whether they are
young or intermediate or mature once
they're involved in like I said some
sort of collision or if they survive
into the modern world all right Island
arcs done another thing I want to do
because things are going to get weird
and wild in the upcoming videos is I
want to color these uh continents in
slightly differently so we can better
keep track of things so to do this I'm
going to go over to illustrator or any
sort of like digital art tool Photoshop
whatever I'm going to create a canvas
that is twice as wide as it is high
that's very important let's say a
thousand by 500 pixels and we'll just
call this whatever G plates it doesn't
really make a difference and I'm going
ahead okay and then I'm Gonna Fill This
canvas uh with a kind of land color
something like that perhaps and then I'm
going to export this
I'll call it land and I will stick it in
my G plates folder
PNG will do jpeg I think will also do I
always go with PNG so stick with that
and then I'm going to change the color
of this to an ocean color
something like that and I'm going to
export that too
cool back in G plates hit file import
import roster select one of them say
let's say ocean to start off with hit
okay you can rename this if you want to
Ocean it doesn't actually make any
difference at all hit continue don't
touch any of this hit continue and then
we'll create a new feature collection
hit done and then we're going to scroll
over to our panel here on the left our
layers panel if you do not see it Ctrl
or command L go down to the ocean
section twiddle down the drop down arrow
here under reconstructed polygons hit
add new connection and then I want to
connect this ocean to this ocean layer
to Ocean crusts and what this does is it
it Clips the ocean to our ocean cross
layer so if you're familiar with
Photoshop it works like the clipping
tool I'm going to reduce the opacity of
this 0.5 something like that and then
I'm going to go up to my ocean cross
layer and I'm going to not fill polygons
and I'm going to set my draw style to
Plate ID so they're colored by plate ID
which is going to be useful in the
upcoming videos okay and then I'm going
to do the same thing for the land so I'm
going to go file import import raster go
to land hit open
I'll name it as land but again it
doesn't really matter I've got to
continue don't touch this go to continue
new feature collection done and same
thing again that's very yellow now to
look at it but here we are
um reconstruct the polygons twiddle down
the land
um drop down menu reconstruct the
polygons add new connection and I want
you to appear on the continents and I
also so it gives you another add new
connection I also want you to appear in
my island arc so I want you to color
those in as well and so that's quite
handy we'll get rid of that we'll go up
to where's the continents yes content
scroll down I'm not going to fill
polygons I'm going to set my draw style
to Plate ID so again everything now is
labeled by plate ID but we still have
colors and back to my land layer for a
second and I'm just going to drop the
opacity of this down something serious
yeah something like that it appears I've
lost my failed Rift so hold on failed
Rift
failed riffs and let's do set draw style
and I will just give you a white will do
here
much better so now let us set up a new
rifting event and we'll riff the
continent apart in the next video
clearly the obvious candidate here is
for Craton B to go up that way say and
create on C to go this way so for this
failed Rift here to reactivate spread
and go across the whole continent and
Rift it in Twain oh yeah and make sure
you're at the correct timestamp so I'm
going to say that this Rift is going to
appear at 900 million years and it will
grow over the next time step again
always be very like overly pedantic
about where you are in the timeline so
let us now select our failed Rift F on
the keyboard click on the rift I'm going
to copy that geometry so go up to top
right copy geometry digitize tool and
then going to hit I on my keyboard if it
doesn't let you do it go to which one is
it this one isn't it
yeah insert vertex in the menu here and
then basically I'm just going to keep
inserting vertices at the start and end
points of the line to complete the rift
now key thing here is that you need to
make it spread across the entire plate
so it's not good enough to just kind of
spread across the land mass it's going
to need to go all the way out to
subduction zone and all the way out to
the mid-ocean ridge like the whole plate
has to Rift apart so I am going to what
am I going to do how am I gonna do this
let's I might bring it true here just
because then I can demonstrate splitting
Island arcs yeah let's just do that
something like
again you can be a lot neater than I'm
being here
um a lot nicer and let's bring it out
until it meets the subduction zone until
it reaches the end of the plate
perfect
okay and with the eye tool still
selected go to the other end of the line
and then what is Handy here is to simply
just because we don't really care about
what's going on in the ocean per se is
to just simply drag it out to a
convenient vertices in just straight
lines so I'm going to click one here say
and then one here to meet the mid-ocean
ridge okay
looks like a solid Rift to me hit L to
bring it back into editing mode go to
create feature
this feature is not going to be an
island arc it's going to be a
continental Rift just like before
where are you they are Continental Rift
a spreading Rift on continental crust
plate ID again just like before will
make it a stationary object because as
things spread stuff happens so we're
going to give it a player ID of one the
play ID we have reserved for stationary
objects it begins not at 950 million
years it begins at 900 million years
it'll continue on to this future and its
name is going to be Rift 900.
hit next none of this matters hit next
and we're going to save it in our riffs
feature correction there and we go
create magnificent now what we can also
do is hit F on the keyboard select our
fail Rift and then just to keep things
like decluttered edit feature up on the
top right here
and I'm going to say that it's valid
time it began at a thousand million
years ago but it ceased being a failed
rift at 900 million years ago it became
a full-blown real Rift so we're going to
do that and we can hit close and then if
I scrub through the timeline we should
hopefully see that we have this failed
Rift continuing to 900 Million Years
it'll disappear and in its place we'll
get a full-blown Rift let's check that
out
tasty make sure your time stamp is back
where you need it to be
done
and just like before we can add new
failed riffs off this now reactivated
Rift so I'll demonstrate one and then
I'll put in like one or two others in
time-lapse mode so let's say we got one
here say at this triple Junction so I'm
gonna hit L on my keyboard to bring up
the digitized new polyline tool I'll
Zoom right in and let's just make a rift
along
there say
yeah something like that create feature
Continental Rift next now plate ID it's
going to need to go with the continents
but also we need to be mindful that
we're going to split them so what I
would suggest doing here is giving it
the plate ID of its nearest Craton so
this is on the green crate on side which
had a player ID of 200 so I'm going to
give it a player D of 200 began time at
900 million years ago correct it'll go
into distant future until we decide to
kill it later if we sold aside and we're
going to call it
failed Rift 900 okay done next next
and then I'm gonna put that in the field
riffs folder and hit create
beautiful I'll do another one up here
again in time-lapse mode but just the
important thing is I'm going to give it
the plate ID of 300 because it's on the
300 side of this continent of this Rift
so time-lapse mode engage
all right that is that lovely little
collection of failed riffs there let's
go through the simulation one more time
just check if everything's in order and
that will be us for today
boom beautiful beautiful oh and actually
there's one more thing I wanted to show
you guys uh just give you a summary of
what your world should kind of look like
after 100 million years if you were
doing a full-blown simulation so it
should look something like this you had
a super content it rifted apart here the
extra Rift has already happened which
we'll do in the next video but you
notice here the subduction zones around
the outside the island arcs in the
trailing on the trailing edge of the
seduction Zone same thing over here same
thing here a couple of the island arcs
are connecting to the land this is the
kind of expected state after about 100
million years okay that is that thank
you so much for watching folks I really
hope you enjoyed the usual thank you so
much to World building pasta links in
description thank you to venger Van Gogh
resident artist over here links in
description also and thank you for
watching until next time
it grows