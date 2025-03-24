# GPlates: Continent Collisions - Worldbuilder’s Log 16

good morning interweb world Builders log
16. today we are going to smash some
continents together but first as always
some follow-up I noticed in editing the
last video that this section of accrete
terrain here is just miles too big and
it just so happens I also got an email
this week from a chap called Carter hi
Carter who left the link to a bunch of
papers describing how much accreted
terrain one would expect at subduction
zone the short and sweet of it is that
you can estimate this by taking the
length of the island arc multiplying it
by its age and dividing by two to get
how many square kilometers of terrain
should be added so let's do that here
right so s on the keyboard and I'm going
to draw a line along here we'll say
that's the extent of the island arc
there so that's what size 530 kilometers
okay hit F on the keyboard select the
island arc it Formed at 950 it is
currently 650 so it is 300 million years
old so we do 530 times 300.
and then divide that by two we find that
the amount of created terrain should be
about 80 000 square kilometers so again
if we hit s on the keyboard or we hit F
on the keyboard select our feature hit s
we see that the area we got here is
about quarter a million so like miles to
Big I'm gonna move around some vertices
get it more into what's expected
yeah so hitting s on the keyboard I see
an area here of about 84 000 Square
converse that's good enough for me and I
checked off screen this chap here is
actually pretty decent so that's the
first item followed the second item
follow-up is I forgot to add Island arcs
along here and I forgot to extend my
subduction zone down to the middle ocean
ridge so I'm just going to real quickly
do that and I will see you in two
seconds
all right Dawn let's get colliding so as
mentioned in the previous video
collisions are complicated things so
we'll want to slow down our time step
here from our usual 50 million years to
about 10 million years so what I'm going
to do is I'm going to quickly save
everything
gonna skip forward 10 million years to
640 and I'm going to move these two into
Collision now what I'm looking for is
I'm looking for see the OG coastlines
here the original Coastline of our
continents I'm looking for these to
overlap and at that point I want to say
that the Collision has happened so let's
do that F on the keyboard select a
continent p
highlight children all
enable Pole
and let's get moving
okay so we can see after 10 million
years
the overlap hasn't happened so what I'm
going to do is just save a little bit of
time and hit Ctrl or command M and I am
going to go to my rotation file and I'm
going to reload it
so this snaps back into where it was at
the start and this time I'm going to go
for another 10 million years and I'm
pretty confident they'll Collide if we
go from 650 to 630 so let's again do
that
and again making sure to check my flow
lines to make sure no adjacent floor
lines are overlapping
all right flow lines look good
and we have our original course lines
overlapping now great so we're going to
deal with the Fallout of that in one
moment I'm just going to move all the
other continents around now important
Point here is that you'll notice that
I've basically neglected these two
little continents like in reality I
should have been extending the
subduction zones up as I go adding
Island arcs Etc but they have served
their purpose they were there to
demonstrate how to split apart
microcontinence and coal moving plates
so basically I've just forgotten about
these now they've done their thing
they're just going to keep moving on
until the end of the simulation nothing
will be added to them just for the sake
of like simplicity
foreign
cool so obviously this is an unphysical
situation consonants don't overlap IRL
what would actually occur as these
continents come into contact is that the
crystal material here will deform and
compress and buckle so to account for
this we are going to copy the geometry
of our continents and we're going to
deform them along this collisional
boundary such that we get rid of the
overlap all right so we're going to hit
F on the keyboard oh and what I'll
suggest here is going forward .01
million years so in this case it's
629.99 because we're going to set a
bunch of stuff to disappear at 6 30 so
we'll see it disappear because we're
just beyond that it'll help clean up
this mess so let's select the content
copy geometry to digitize tool hit I on
the keyboard or come over here to insert
vertex and we're going to insert just a
bunch of of points along this boundary
here
all right and as these were coming
together and everything was squishing we
can expect some of the contents of this
to get like squished out the side so
let's Buckle it out the sides a little
bit
something like that and then let's run a
zigzaggedy line down sort of the center
of the overlap
and then again we'll squish it out here
shoulder deformation
something like that okay hit G on the
keyboard bringing it to polygon mode
then go to create feature this is
continental crust
it is going to begin life at this
Collision time so played IDF 100 here
first of all because it's attached to
the blue Craton begin life at the
Collision time 6 30 and we're going to
call this
continent a
because it is continent just squished
and deformed next next and then we'll
stick it in the contents folder and go
create then we're going to hit F on the
keyboard highlight our original
consonant go to edit feature command or
control e and then we want to set this
to disappear at that exact moment at 6
30 and because we are a little bit ahead
of 6 30 we can see it disappear here all
right I'm going to repeat this process
for the second continent
cool so now we have this outline of our
new continent from here on in it's just
a bunch of cleanup really so these
abduction zones when two continents
Collide the subduction zones in between
them will be shut down and disappear
after a small period of time but we
don't need to worry about that we can
just disappear at this instance so to do
that we're going to hit F on the
keyboard select a subduction zone go
over here to the split feature or hit t
on the keyboard and then just split it
somewhere here say hit F select the
portion that you have split that you
want to disappear go to edit feature and
then change the date change the end date
to when you want it to go away 6 30 in
this case and it disappears so again I'm
going to do the same thing for all the
other sub blocks results
okay and while we're at it I can foresee
this now combined consonant traveling
that away
so there is no reason at all not to
extend this subduction zone all the way
across or L on the keyboard and we'll
draw a line
something like that create feature and
make a subduction zone that begins at
this current time the time of collision
boom now we have three lumps of a
created terrain we have what was an old
island arc what was an old island arc
and what currently is an island arc now
you can and this is totally legitimate
you can set each of these features to
disappear at this time but what you can
do to be a little bit more detailed if
your soul choose is create new features
along this collisional boundary that
represent these chunks of a created
terrain smushed into the Collision
boundary for the sake of pollution I'm
going to do that so I'm gonna hit F in
the keyboard I'm gonna select this guy
hit s for the measure tool he's about 84
000 square kilometers in size I'm gonna
make a feature maybe somewhere here
that's slightly less again to kind of
hint at the compression and deformation
that would have taken place G on the
keyboard and let's get drawing
s this is about 51 000 square kilometers
and go a little bit more than that maybe
something like
there we have something like that g
create feature continental crust plate
ID will give the player to the 100.
because this had a player ID of 100
begins life at 6 30 goes on to the end
and I'm going to call this
accreted terrain I'll call it 6 30 for
now but give me one moment next next
I'll put this into a creative trains and
go create now this island arc here we
said it Formed at 6 50 so let's
change that date
on the name
just to note that and then F on the
keyboard select our old feature edit
feature
and then set its end time to the point
of collision
to clean it up
done I'm going to do the same thing for
this chat now
Brill and again just the stress not at
all mandatory you could just set the
features disappear I guess this could be
useful if you wanted to like track
fossils in your modern world where they
came from Etc
but again definitely definitely not
mandatory all right now we got an island
arc so we're gonna need to just like
before select the island arc clone it so
we have two copies of the island arc
delete points away from one copy so
you're left with everything that's been
accreted in one copy and the other copy
is left with everything that remains in
the ocean same procedure as previous
videos
now once you've got the copy you need to
get rid of go to edit feature same deal
as before change the end time to the
point of collision
beautiful
so let's figure out how much terrain we
need to put along that collisional
boundary s on the keyboard
that's about 800 we'll call it 900
kilometers and then that item dark we
said appeared at 6 50 and the Collision
is at 6 30 so it's 20 million years old
so that's 900 kilometers multiplied by
20 million divided by two is 9 000
square kilometers so basically barely
anything but for the sake completion
we'll we'll mark it in
that that's already 14 000. so it really
is barely any crossed material was added
there you go
let's just have a little look see at
that
boom and now these boils okay so notice
we have some ocean overlap here we'd
like to clean that up so just like
before
select the feature you want to clean
create a copy so you now have two copies
one copy is going to be the section you
want to get rid of you're going to
change the end date the other copy is
going to be the section you want to keep
you leave that alone and while I'm at it
actually the same process applies to
cleaning up these chunks of ocean crust
so I might just do that now because
really I should have done it ages ago
when they first formed but I was too
lazy so we'll fix that in this uh step
right time-lapse mode engaged
good
foreign
foreign
okay all cleaned up now while I was
doing that I actually recalled something
that I forgot to say which is actually
really important when consonants are
coming together and you're doing the
overlap we had at no point you should
crate on overlap because the whole point
of create Hunts by definition they are
chunks of the cross that have been
undisturbed by tectonic forces so if the
overlap involves cratons necessarily
they've been Disturbed so they're not
really cratons now in reality cratons
can deform a little bit but for our
purposes here just stay clear of them
they should never be involved in the
overlap period so now that we have
a single constant here we need to tell G
plates to treat it as a single continent
so if we recall the splitting coal
moving plates video we are basically
going to do the same process but in
Reverse we're going to take two
independently moving plate IDs and bind
them together now to do this we'd want
to decide upon a parent place and a
child plate I.E the parent plate is the
one that does the moving and the child
moves with it so in keeping with how
we've been doing it already I'm going to
say that the parent plate will be
associated with the pink Craton so
plenty of 300 and play the 100 would be
the child plate it will follow pink blue
will follow pink command or control M on
the keyboard save all changes the
important thing is to save the rotation
file and I may as well just save the
file proper anyways we want to go to
reconstruction specify anchored plate
hoodie control or command d and then in
this dialog box we want to put in the
player ID of our parent place so in this
case 300.
then go reconstruction view total
reconstruction polls and we want to do
equivalent rotations relative to Anchor
plate and we want to get ready to import
the child plate ID
the coordinates of that in our rotation
file so that means we need to open up
our rotation file one rotation file so
in the child plate ID so the plate ID
that will follow your main plate ID find
your latest time step which would be
this line here above that input a new
line same player ID in this case PD of
100 same time as the line below 630 the
point of Collision in our simulation
and then we want to put in the
coordinates of player D100 at this time
so
29.5454 and so on
and then we want to hit space and input
the parent plate ID so in this instance
300 and we'll put in a comment here that
says start
following
C because if I recall correctly player
ID of 300 was kraton C correct all right
and while we're at it we may as well
take the coordinates and paste them into
our drift correction
and very important the conjugate plate
ID here needs to be the same in your
drift correction otherwise things are
going to break and I guess while we are
actually here we may as put in all the
drift Corrections so 630
copied coordinates for that imported
into drift correction for player D200
okay save the rotation file close your
text editor go back into G plates hit
Ctrl or command M and then reboot the
rotation file reconstruction specified
anchor plated D and set it back to its
default zero zero zero so now all going
well all our flow lines should be busted
which they are wonderful thanks G plates
but we should be able to move
these two as one so I'll select that hit
p on the keyboard and will you look at
that with children highlighted all of
this would move so this all will move as
one now now it's worth noting at this
point that if you select the child date
ID and try to move it it will move on
its own so you could totally do a thing
where the Collision starts say at 6 30
and they begin to move together through
to say 620 but as they are moving
together the child pity is kind of
further grinding into the parent plate
so you kind of have a prolonged
Collision process if that's something
you're interested in but for sake
Simplicity I'm just gonna say it all
happens in this one time Step At 6 30.
all right so penultimate thing here is
I'm going to delete these flow lines set
them up again and paint in some ocean
crust again no new information so I'll
just skip straight to it it should look
a little bit like this
now two things before I go number one
believe it or not we now actually have
covered everything you need to know
about colliding landmasses we've covered
what happens when island arc collides
with a continent and now we've covered
what happens when a continent collides
with a continent the
the other structure that you may come
across in full simulations is Island are
colliding with island arc but it follows
the same process as this two Island arcs
come together you overlap them you
figure out how much train each one of
them accounts for drawing that train
smash it together that's basically it
the other thing is recall that
subduction zones are the most important
part of the process at all times we need
to be like micromanaging our subduction
zones where are they what are they doing
what is feeding them that's the key
thing most time you'll have a nice
mid-ocean ridge that's putting out
across that's being sucked into dock
console everything's nice and stable but
in this instance here you see we have
these like dangling subduction zones
that are no longer being fed by a
mid-ocean ridge they're kind of just
stuck in this place doing nothing that's
a situation we'd want to resolve now
there's a number of ways we could
resolve this situation but I think the
most logical one is that we can open up
a subduction zone along the coastline of
our new continent why because this crust
is really old it's what is a 100 200 to
300 350 plus 20 it's 370 million years
old that is super old natural place to
produce production and if we run a
subduction zone along here we'll have a
mid-ocean ridge
feeding this subduction zone which will
eventually gobble up our kind of errant
subduction zones here so I am not going
to do that now for the sake of time but
I'm just going to plop in this abduction
Zone and we'll move it in the next video
a given player ID of 300 again now pink
is our primary crate on for this entire
plate so we'll tie everything to 300.
Bingo and I just want to stress that
again because it is so crucially
important subduction zones are the key
here they always need to be fed by
something if they aren't being fed you
need to resolve the situation most of
the time by making them Disappear by
sucking them up into something else
alright that is that next time we'll see
what happens when these fellas begin to
be sucked away and we're going to start
putting in orogeny thanks to
whirlpooling Pasta thanks to venger
vangog thanks to you for watching thanks
to the patrons for supporting the show
y'all are the best of nerds until next
time
Edgar house