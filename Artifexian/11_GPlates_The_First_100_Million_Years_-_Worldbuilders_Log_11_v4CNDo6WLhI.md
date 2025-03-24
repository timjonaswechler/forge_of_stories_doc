# GPlates: The First 100 Million Years - Worldbuilder’s Log 11

good morning interweb world Builders log
11. in today's video we are going to
Rift apart our supercontinent that we
created in the last video and simulate
about 100 million years of evolution on
this planet so the first thing we need
to do is we need to take our
supercontinent and split it into two
because we're going to Rift it apart and
the way we do this is we select our
super content so you hit F on your
keyboard for choose feature click on
your super constant then come over to
the menu here on the right and hit clone
feature
this clone is a consonant so we'll place
it in our consonants folder and hit OK
and then what we've done is we've
created a copy of our original Super
content you can see that down here we
have two copies of consonant ABC so the
next thing I'm going to do is I'm going
to hit V on my keyboard for the move
vertex tool and I am going to click and
drag these points
down to match our Rift
okay and so here
I'm going to zoom in a little bit and
I'm going to hit I on my keyboard for
insert vertex and I'm just gonna import
a point
here
and then I'm going to zoom out a little
bit I'm going to hit X on my keyboard
and I'm just going to delete all of
these extraneous points
okay and then I'm going to zoom in a
little bit more and just tidy things up
a little bit
cool so now we've created this half of
the continent I'm going to hit F on the
keyboard to choose feature and again
over in this right hand menu I'm going
to click edit feature or controller
command e
so this new bit of Continental cross
we've created it is not called content
ABC this will be called continent a
because it contains only Craton a in the
next menu down here it was not created
in the distant past it was created at
the moment of rifting so as per the last
video in this instance it's a thousand
million years ago and it'll continue
into the distant future and its player
ID is 100 because kraton a the player ID
of Craton a is 100 so everything there
is fine so I'm going to go close and
then I'm going to repeat that process to
cut out the other half of the consonants
I'm gonna hit F on my keyboard to select
our original Super consonant and again
if you're ever unsure as to what you've
selected or can't select the thing you
want to select pop down here's this menu
and it'll help you out okay so I'm going
to go clone feature again this is a
Content I'm creating so of course in the
continent folder hit V on the keyboard
to move vertex and once again match up
the rift
and again you don't have to be massively
precise here
just get it looking somewhat precise
okay so hit F on the keyboard find that
bit of cross that we've just created so
I'll pop down the menu here and it's the
one we created a minute ago precisely
I'm going to hit edit feature
it is not consonant ABC it's continent
BC because it contains Craton B and
kraton C it was not created in distant
past it was created at the moment of
rifting so that's a thousand million
years ago in this instance and its plate
ID is not 100 it's played ID because we
don't want it to move with this Craton
we wanted to move with these great hunts
so I'm going to choose the player ID of
the big one here I'm going to say 300
and then I'm going to hit close and then
the final final thing to do is hit F on
your keyboard go back to your original
supercontinent so that is supercontinent
a b c hit edit feature
keep everything the same but go down to
the valid time section here and uncheck
distant future
and say that it ends at a thousand
million years ago so the idea being that
at a thousand million years our super
consonant it ceases to be because it
splits into two
and we go close and hopefully we should
be able to see
you can see the drop-off and opacity
there at a thousand million years ago we
have three items here we have continent
a continent BC and then the entire
continent ABC and then if we scroll
forward that entire consonant ABC is
gone and we're left with just the left
half and the right half all right that
is how to split a feature let's now
begin to move around so to do this we
need to open up a plain text editor so
on Mac I use text edit
on Windows something like notepad plus
plus would work anything that's a plain
text editor and what I want to do is I
want you to type 100
space 0.0
space
90.0
space 0.0
0.0 threes space three zeros in a row
and an exclamation mark and we'll just
make that bigger
and then I want you to copy this
put on the next line and replace this
0.0 with 1000 and I'll explain why I'm
doing this uh in a second 1000.0
and then if you want you can space
things out so everything kind of neatly
matches up as long as one space in
between each of these elements your
gravy
okay so once you've got that exactly
copy this again
and in my case we're dealing with three
cratons so I just need to make three
copies or two additional copies but in
your case if you're dealing with the 812
recommender cratons you're gonna have to
have 8 to 12 copies of this see can I
make this bigger one just to make sure
everyone can see this at least somewhat
clearly
so what this is this column here this is
plate IDs this column here this second
column is timestamps so 0.0 is the end
of the simulation a thousand million
years ago is a startup simulation if
your simulation is longer or shorter
that would need to be changed
accordingly
these three columns here these these are
coordinates they store the location of
the continents as we move them around
and this column here is the conjugate
plate ID think of this as a linking
column so if you want one Craton to move
in tandem with another crate on you drop
the relevant player ID in here you'll
see it in action in a second then you
have an exclamation mark and thereafter
you can put in any sort of comments the
exclamation mark is mandatory you can't
G plates will crash or Not Crash but
it'll like get angry at you if you don't
have an exclamation mark even if you
don't want a comment you gotta have an
exclamation mark oh and it's worth
pointing out the G plates reads
everything backwards when it runs a
simulation just something to be aware of
it'll become more relevant in a second
so plate ID of 100 which is this fella
here for him because he's not moving
with respect to anyone else or at least
I don't want him to move respect anyone
else everything here is fine so I'll put
in a comment here saying that this is
Craton a
at the start of the simulation and this
stores the data for Craton
a at the end of the simulation again G
plates is reading backwards
then our next Craton is 200 play ID of
200.
all of this is fine for now
so crate on B
at the start of the com simulation
Craton
the at the end of simulation and then
played her D300 which would be this
fella here
oh sorry 300.
everything here is fine and so this is
Craton
C at the start
and create on C at the end now we said
in the last video that we want this
crate on and the associated a Content
across the scroll to go this way and we
want these two to go this way
so that means one of these is gonna one
of these create hands is going to follow
the other so let's say our big cratonin
is our main Craton and we want crate on
with the plate the crate on with the
plate ID of 200 to follow this chat so
we go to our 200 plate ID section and we
say hey will you please follow plate ID
300 so your motion is based on the
motion of what's Happening Here okay so
hopefully that's clear player ID
timestamps coordinates linking
comes and the final thing to do here
before we save is uh I I like to put in
these line breaks just so I can visually
see how many cratons I have to see I
have all the right things but uh G
plates is going to have a small
conniption if you leave these in so
you're going to have to delete those
otherwise g-flators Will shout at you
and no one says shouted at by a plate
tectonic simulator so with all of that
done I'm gonna hit save
and I'm going to save this in my G
plates folder and I'm going to save it
specifically as a rotation file and then
I'm going to hit save
for real so let's minimize that
and I'm going to go to where that where
that's located
so we have our rotation file you notice
here that this is a plain text document
it cannot be a plain text document so
right click get info this process might
be slightly different on Windows I don't
know how it works I'm sorry but either
way what you're looking to do is you're
looking to change the extension of the
file from txt to dot Rost to make it a
rotation file hit return
and then are you sure you want to change
the extension from dot txt to dot rot
yes use dot rush if it's not dot orot g
plate end code readers all right with
that done we can hop back into G plates
hit command M to bring up the manage
feature collections
and what I want to do is I want to open
a file
I'm going to find where I store that dot
wrap file and I'm going to load that
into G plates and assuming you've done
everything correctly you shouldn't get
any error messages and there should be a
rotation file up here so basically we've
just given code to G plates to be able
to track the movement of plates I know
horrifically obtuse if this was a
consumer application it would simply be
a case of like putting keyframes in the
timeline
but it's not so we need to go through
this obscure scientific software for the
win am I right okay now for good stuff
what I would like you to do is I'd like
you to go up to your time frame here and
I'd like you to skip forward 50 million
years so in my case I want to go to 950
billion years
in general it's a it's a good idea to
work in 50 million year chunks that
amount of time is uh large enough that
you don't spend the rest of your life
doing this simulation but also small
enough that you don't skip over a bunch
of details you can work in smaller time
chunks like if you're doing a very
complex
um like say there's many bits of content
colliding one another you could slow it
down to like every 10 million years or
so but in general work in 50 million
year time jokes so with that done I'm
going to get you to hit 5 on the
keyboard to bring up the pole
manipulation tool and from there hit F
to choose a feature and let us choose a
feature to move let's choose this chap
here now I want you to hit o I go up to
the top right or o is the uh what is
that move poll menu go up to the top
right of the move hole menu and click
enable pole and you should see this
thing up here beautiful then I want you
to hit p for the modify reconstruction
poll menu Snappy title right there and I
want you to go up here and hit highlight
children now to move things in G plates
you switch between the all menu the move
pull menu and the P menu the modify
reconstruction pool and you use those in
tandem to move stuff so check it out if
I hit all for move pole I can click and
drag this poll down here if I hit P then
for the modify reconstruction poll this
will move the continent this allows me
to click and drag the continent move it
around but only in a circle around said
Pole you see that
so you could like do something like this
then you could pop back to all for move
pole and then you can move the pole
again say over to here then you can go
back to p p and rotate it around that
pole of your soul desire and then hit
back go back to oh move it into here
Etc until you find a position you like
and once you've got a position you like
you can go apply over here in the
Reconstruction poll menu so necessarily
you have to be on the P menu all right
obviously this is a little nonsense so
I'm going to hit reset rotation the key
kind of thing to visualize here is that
if the pole is far away and if I hit p
on my keyboard the rotation is kind of
like linear see it's going to go around
like this it's not really going to
travel north or south and the closer the
pole gets to the object the more it's
kind of rotational
and the more kind of moves up lines of
latitude and the pole can move right on
top of the continent and it's purely
kind of rotational then so again moving
between o and P the menus o and P are
the menus triggered by the shortcut keys
OMP will allow you to move consonants in
any way you want so I'm let's let's do
it for real now so I'm gonna go all and
I'll move this up here so I want this
chap we said he would kind of move down
this way which is like south west or so
so I'm thinking imagine there's a big
circle here so I would imagine that my
pole should be somewhere up here
so I'm going to move my pole somewhere
up there then I'm going to hit p and I'm
going to try that
see do I like it so it is going
Southwest it's probably a little bit
much for my liking so I'm going to reset
I'm going to drag the pole around a
little bit very much try to narrow this
until you get something you're a happy
wish
maybe it is something like this
yeah maybe that's actually a nicer
movement I think and this is all just
kind of like artistic interpretation
what you think looks like a cool
movement I'm gonna go with yeah
something like that I think that looks
Niche once you got that hit apply all of
this don't touch it it's Auto generated
by g-plates hit okay
and boom we have moved our consonants so
if we scroll scroll through this we
should be able to see it nicely animate
out to where we moved it so from from
the supercontinent at one thousand year
million years ago to 950 million years
where it rests in its final position
brilliant how cool is that make sure you
go back to 950. you need to be really
precise about making sure you're at like
either the very start of your time step
or the very end if you're sloppy with
the timeline weird things can happen so
I always try and make sure I'm always
glancing up at the time I'm making sure
I'm at the exact date I want to be at
now the cool thing about this the cool
thing about using g-plates is that it's
not just simply like a a really
inconvenient way of animating low poly
things we can use some of the like
mathematical tools to kind of bring a
sense of realism to what we're doing so
once you've uh decided where your
content is going to go hit command shift
k
to bring up the command or control shift
okay to bring up the kinematics tool so
this basically measures
what your continents are doing so we're
dealing with this consonant here that
has a plate ID of 100 so I'm going to
pop that in here plated u100 and I want
to measure stuff from the beginning of
the simulation and we'll say all the way
to the end everything else is fine here
and then I want to check velocity
magnitude once I got that hit update and
it gives you a speed graph of how fast
your continents are moving in
centimeters per year
which is really useful for tracking
realistic plate motion so if I check
there's my 1000 years so end of the
simulation thus far is about here so
during that course of that uh time
period the consonant is moving at 1.97
centimeters per year now is that
realistic to answer that we can go to
World building pasta's wonderful blog
links will be in the description to this
and we have like a little speed chart
here so if you have a subducting ocean
you can expect maybe 8 to 20 centimeters
per year if you're dealing with a recent
subduction Collision about six
centimeters per year an active margin
continent about three and a passive
continent less than one but like what do
these all mean so as a shorthand think
here old India
current India current South America
current Africa so check this out here
with India down here about 90 million
years ago there's a big old subduction
zone up here so all of this old ocean is
being sucked away and that's forcing
India to travel up this way and note how
quick it travels here
see it's really it's really kind of
zipping along real quick so because that
subduction zone is sucking it in
that is this subducting ocean so India
would have been moving at about 8 to 20
centimeters per year ancient India so
current India
is where it has collided with Asia and
you'll note that it kind of slows down
here
so if you have a recent subduction
Collision so you had a subduction zone a
continent or microcontinent came racing
in then collided with some land
everything will slow down to about six
centimeters per year so active margin
constant again think modern South
America is where you have a continent on
an active margin and an active margin is
where a continent is next to a plate
boundary so if you have a situation
where you're with a mid-ocean ridge a
continent and then a subduction zone
along that continent you could expect
that plate to be moving at about three
centimeters per year and a passive
margin content is kind of like a plate
that isn't really moving like all plates
are moving all the time but obviously
some barely move and some move lots and
a good example of that like I said is
Africa if you notice here Africa is
basically apart from up here in Europe
it's basically spreading in all
directions so it's kind of not really
gone places and so its speed is fairly
low about 1 centimeter per year now for
us in our simulation
you'll notice that this here because
this continent is going to go that way
this is going to be our mid-ocean ridge
we're going to have a continent and we
will eventually have a subduction zone
here so we are basically creating and
this is how the simulation will kind of
nearly always have to start we are
creating an active constant margin here
so this consonant should be moving at
about three centimeters per year you
don't need to be precise just somewhere
in the ballpark so for me I think this
is a little bit slow 1.9 so what I'm
going to do is I'm going to click off
this I'm going to make sure I'm exactly
at the correct time frame I'm going to
hit p on my keyboard and I'm just going
to drag this a little bit further out
not a lot just just a bit and I'm going
to apply that
doesn't matter don't worry about any of
this hit okay command shift K and I'm
gonna update this so now we're at 2.3 we
can go a little bit more so p on the
keyboard and dragging it out I'm just
going to leave the poll where it is I
could be moving this around if I want
but I'm not I'm not that bothered so hit
apply it doesn't matter this is all fine
hit okay command shift K command or
control shift K update
3.1 cool all right so that's about
the expected distance that continent May
cover so let us now move
this continent hit F on your keyboard to
choose a feature there we go hit p on
your keyboard to bring up the poll
manipulation tool and now I'm going to
move this again I'm thinking that this
is probably going
this sort of Direction like North East
so I'd imagine the pole would need to be
somewhere
possibly the same place so I'll move the
pole uh using the shortcut o go back to
p and click and drag
yeah maybe something like that let's hit
apply
okay command shift K to check our
movement now this time we are dealing
with again we've just kind of assumed uh
our big crate on is the kind of main
plate ID so I'm going to put that in
player ID of 300 and I'm going to update
it and we have
1.19 centimeters per year so it's a bit
slow let me move it again I kind of want
to move that pole hold on
yeah something like that perhaps
command shift k
update to 2.6
all right 3.4 so we're we're higher than
three by a fair bit but that's okay 3.4
is fine all right so let's scroll back
in our timeline and let's see the
animation
cool okay
so one thing we should pay attention to
here if I just scrub through this
manually you'll notice everything's fine
up until 950 million years and then this
happens
all the continents just come back
together again which you know just fun
times really fun so what we need to do
is we need to like manually tell gprits
to please don't do that uh because again
G plates is not meant for usability
um so what I'm gonna do is I'm gonna go
find my rotation file
uh where I saved it and I'm going to
open it
and if you have a look at this this is
cool we can see oh sorry sorry my bad
sorry we need to go down to command m
and we need to save everything so we
have to save all that rotational and
translational data into the text edit
file we created so we'll click save all
changes and we'll go close and now I'm
going to go look for my rotation file
and I'm going to open it in my text
editor so the cool thing here is that we
can see that g plates has updated
this file so let me just put in some
line breaks we'll see exactly what's
going on notice that g plates has
automatically inserted a line of code
here at 800 sorry 950 million years it's
recorded the position of our continent
and it's done the same thing here for
plate ID of 300 so create on uh C
950 million years we have this position
cool so what we need to do to stop all
of the Mad drifting that g plates does
we're going to copy the last entry
in the simulation and remember G plates
read stuff from the bottom to the top so
this is the first entry at a thousand
million years this is our last entry
entry that we've created so we're going
to copy that
and we want to paste it above it very
important has to be above it and keep
everything the same but just replace the
time with 1.0 all right and then I would
label this
drift correction just so you know why
the hell that's happening we don't need
to do anything with played ID 200
because it's just following the big
crate on here it's just following
everything that's labeled plate ID of
300. so we don't need to worry about
this here we do need to worry about it
so we need to copy this
and we can paste it
above very important and replace 950
with 1.0 and we'll call that
drift correction
and while we're at it we should probably
say make a note in these comments that
this follows
Craton C
follows
C just to make it clear all right get
rid of the line breaks
otherwise G plates would have a hissy
fish
save
then back in gpets hit command M to
manage feature correction and G plate
doesn't know that something has changed
so we need to just reload that rotation
file and now what we've just created is
in G plates so if I scrub through here
we'll see that it holds and then only at
the very very end it snaps back
so technically this is like a 999 year
simulation as opposed to a thousand year
simulation and there's I don't know
there's little we can do about that at
least I don't know how to fix that it's
annoying but here we are
okay so next up let's start working on
some ocean crust so go back to the start
of your time step in this case it's the
start of simulation uh once you hit F on
your keyboard and and I want you to
choose your Rift the initial Rift if you
have problem selecting it pop down to
the menu here and we have rift at a
thousand million years ago select that
guy and then I want you to go up here to
the right and go copy geometry to
digitize tool and then hit the keyboard
shortcut M alternatively go over here to
digitize new multi-point geometry and
it's basically turned our Rift here it's
created a copy and turned that copy into
a series of points all right very
important now we're going to go create
feature
and we are going to find flowline tracks
plate motion away from spreading ridges
over time using half stage rotation we
don't need to worry about half state but
real half State rotation is it's not
important hit next
from here keep this the same keep this
the same enter in the adjacent plate IDs
so adjacent to this line there is this
plate ID of 100 so I'll put that in here
and then on the right here where again
we're going with the big plate of d as
being the important one so that's a
player ID of 300.
and we recall this flow lines
1 000 million years ago they will go on
to the distant future uh but they'll be
created at the moment of rifting so
that's a thousand million years ago and
just a quick note here it says left
plate ID and right plate hoodie but it
doesn't have to be left and right it's
just adjacent so like if your consonants
were splitting say north south like
these two were going this way and this
chap was going down south you just enter
in say North Plateau D here and South
play Hoodie there it's just adjacency it
doesn't actually matter about the
absolute Direction here and then once
you've got all that hit next wonderful
now here here we need to worry about
this we need to hit add
and what I want to do is go down to
insert multiple times from
where it began so it began at a thousand
million years ago and then after that
everything else is fine here don't touch
that just hit insert and you'll see a
bunch of times timestamps put in here
you don't need to worry about what those
are we just need to have them hit okay
then hit next and then create a new
feature correction so go down to create
and save or select create a new feature
connection and go create and save and
save that feature collection as
flow lines
I can't type apparently and save and now
we can close this and what we get now if
we've done everything correctly is we
should get this
isn't that pretty
so a couple of things here to note Is
That Flow lines are really useful in
tracking good plate motion
like even though you might have the like
crack speeds you might be doing like
unrealistic Maneuvers and flow lines are
a really good way of telling that so for
example in general most of the time
though not always adjacent flow lines
here they shouldn't cross each other if
they do you're potentially doing
something wrong again most of the time
also the flow lines shouldn't intersect
consonants again most of the time if
they do you might be doing something
wrong so it's a good way of tracking
realism and the second thing is you'll
notice here that if you can see these
yellow dots here
these are halfway between
these lines it's like the midpoint that
is where our mid-ocean ridge is
so you'd think that the mid-ocean ridge
would be at the point of rifting which
we've marked here in red but because
these consonants are moving won't be
moving at like identical speeds away
from one another the mid-ocean ridge
necessarily you know because it's a
mid-ocean ridge will have to like move
to compensate that so you can use use
flow lines to track where your mid-ocean
ridges precisely should be which is kind
of dope and so once we have that I would
skip forward to 950 million years to the
end of your timestamp hit F to choose a
feature and I would click on is it the
bottom floor line yes or is it any floor
line
oh I click any flow line if you've done
that correctly these should gray out and
one of them should be in white that's
how you know you got the flow line
alternatively down here at the bottom
select flow lines from there I want to
go to digitize or not to copy geometry
to digitize tool and then I want to hit
G now if like me G plates won't let you
do that you keep getting an error
just select it manually from the sidebar
here digitize new polygon tool and what
we're going to do here is so it is taken
the mid-ocean ridge and it's drawn a
line and it's set up a polygon for us
that we're going to complete and what
we're going to do is we're going to draw
it towards the coast here or Draw it at
the coast here to create our first
section of newly created ocean crust
very very exciting so I'm just going to
do that very very simple drawing we've
already covered this so not much to talk
about here I'm just going to trace
the
Coastline here
okay and we don't need to worry about
the end because jupits will fill that in
it's showing us a ghost line okay once
we got that hit create feature this is
oceanic crust which it's not letting me
choose thanks a million Oceana crust
description ocean acrossed Illuminating
um now in terms of played ID we want to
give it the plate ID of the continent
it's stock to so this consonant here has
a plate idea of 100 so we're going to
give the ocean crust I played ID of 100.
It's Beginning time it wasn't at a
thousand million years ago it begins at
the end of our first time step so at 950
billion years in this case and it'll
continue into the distant future and its
name will be ocean crossed
950 beautiful hit next don't worry about
any of this hit next and then you will
create a new feature correction create
and save and we'll save that new feature
collection as ocean crossed and then hit
save
cool and what we can do is we can come
up here to the layers panel if you don't
see it hit command L command or control
l
we'll twiddle down the menu here we'll
go to fill polygons and we will fill it
with something with a very low opacity
there we go one section of ocean crusts
done what we have to do now is repeat
the process for the other side
again you don't need to be mega mega
precise here it's fine we're going to go
create feature same thing again ocean
crossed
this time a plate ID will give it the
player ID of 300 because attached to the
continent whose primary plate ID is 300
starts at 950 million years cool
continues in this in future and it's
also ocean crossed formed at 9.50 and a
couple people pointed out that like
there might be naming conflict here they
are cute of a bunch of features named in
the exact same way that is true that is
not a bug it's a Feature Feature don't
worry about like this won't cause any
errors or duplicates to form whatever so
if you have a bunch of awesome crossed
formed at 950 million years that's fine
label them as such it's good to date
them all right don't worry about any of
this hit next and then we're going to
save it into ocean cross I know create
and it will grab the plate ID color of
the main concert cool right let's see
how that looks
beautiful and now you can really see the
mid-ocean ridge
how it's moved off from the initial
rifting point which is kinda dope it's
also worth pointing out that like at any
given moment in the simulation there's
obviously new crossed formed here in
this new ocean and then like moving
forward be like a little bit more here
but it'd be so impractical to like
smoothly animate those things using this
method so we just kind of like leave the
ocean empty until the end of a Time step
and then pop in the new ocean at the end
just FYI okay so at this point I'm Gonna
Save up everything so save all changes
close and then go to file and save
project now what I want to do is I want
to move forward another time step so
we're going to move forward to 900
million years ago and we're just going
to repeat this process so I want to
create two slabs of new ocean basically
so five on your keyboard to bring up the
pole manipulation tool I think that's
what it's called I can never remember
these tools names yes pole manipulation
and then I want to hit o and again
switch between all 4 and P to move stuff
around so let's move this chap around so
F and the keyboard to choose him oh
we'll keep the poll where it is for now
and then we'll hit p and we'll move this
guy around so let's move him
out to
hear say all right and we'll go apply
all right it doesn't matter about any of
this hit okay beautiful command shift K
to track our motion plate ID we're
dealing with this continent again so we
played a deep 100 everything else is
fine update and now you'll see that
there's kind of two sections here our
first section we're traveling about 3.1
centimeters per year cool our next
section is about 2.6 a little bit slow
so I'm going to just drag it a little
bit further
it doesn't have to be the exact same
speed obviously because these things can
like slow up or speed down depending 2.8
yeah that'll do I think that'll do for
me let me have a have a look through the
simulation
cool okay back to 900 very important be
really precise about always being at
either the beginning or the end of your
time steps of your 50 million year time
steps I'm going to hit F or five on my
keyboard first of all for hold
manipulation tool hit F to choose
feature I'm going to choose this
consonant and then again switch between
o and P to move stuff around so I'm
going to I'm going to say that maybe
this chap instead of like continuing
this part here maybe he levels out a
little bit so I'm gonna drag this pole
more to we'll say here maybe
and I'll drag him along
so if we do something like that what
does that look like apply
and you can see the flow lines can
really help you determine what's going
on
do I like that
yeah probably
it's fine
command shift K now we're tracking a
plate ID of 300
and we want to update and oh he's
dropped an awful lot so he was 3.4 and
now he's 2.2 I'd like to keep that a
little bit more similar so let's try
something like no
cool 2.2 that's nice kind of like that
okay and again I'm looking at my floor
lines and my floor lines aren't
overlapping cool very good and again we
can see that the mid-ocean ridge has
shifted from where it originally began
okay so let's go make some new cross so
F on the keyboard choose our flow lines
same thing as before copy geometry to
digitize tool hit G
GPS shouts at you so manually select
this Chap and then Trace our autocross
now this time we don't want to go to the
coastline we want to go to our older
ocean crust
ocean crossed Grand just like before
play Hoodie it stuck to the content with
a player ID of 100 so we'll give it
Affinity 100 it was created at the end
of our current timestamp which is 900.
and so it is awesome crossed at 900. hit
next don't worry about any of this hit
next and then put it in the auto cross
section and go create beautiful and then
same stick again
now at this point you might be like who
cares about ocean across and you can
totally kind of ignore ocean crust if
that's not your bag but the cool thing
about doing is in these little segments
is that you can eventually at the end of
the process get G play to color the
ocean crust by age so you can end up
making maps that look like this so it's
kind of like the red portion here would
be our first time stamp then the orange
will be next and then the lighter orange
next and the yellow and the green Etc so
you can kind of make really cool maps
really cool like tectonic maps of your
world if you do it this way all right
and let's check to see if everything's
working okay so I'm going to go back to
the start of my simulation and hit play
class now mid-ocean ridges and the
spreading Soul save with them is only
part of the equation like if new ocean
crust is being created here old ocean
crust has to be destroyed so that's
where subduction zones are going to come
in and by extension volcanic island arcs
Etc but I I want to keep these episodes
fairly bite-sized so I'm I think I might
call it here for today and we'll look at
subduction zones and Island arcs next
week okay that is that for today thank
you so much for watching folks if you
got any questions leave them in comments
and I will see you next week until next
time Edgar house
foreign