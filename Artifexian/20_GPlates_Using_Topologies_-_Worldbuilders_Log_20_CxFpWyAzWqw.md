# GPlates: Using Topologies - Worldbuilder’s Log 20

good morning interweb world Builders log
20. this is going to be the final video
in the G plates tutorial section of this
series today we are going to look at
more advanced ways of using g-plates
specifically looking at how to weaponize
topologies next video will be World
reveal so when it comes to working with
topologies there is one key thing that
you must do you have to go up to the G
plates menu here and down to preferences
shortcut controller command comma
and you have to have this section ticked
short topological sections if you don't
have this option ticked literally none
of this is going to work this is really
important and I believe in newer
versions of G plates this is off by
default so you you gotta turn it on
otherwise again you're gonna have no
luck all right
so with that in the bag I set up this
new little Demo World it looks very
similar to one we had before super
continent that we're eventually going to
split into three pieces Western
subduction zone eastern subduction zone
same sword dealers before but again
we're going to work with apologies so
like before eventually we'll come to the
stage where we want to split apart
continents now the old way was to copy
geometry and then individually move a
bunch of vertices which is easy to grok
but time consuming and messy so what we
can do an alternative method is to
select the supercontinent copy
geometry's digitize tool turn this copy
geometry into a line by hitting L on the
keyboard and then I'm going to go and
hit X on the keyboard to delete vertex
and I am going to delete all the points
here
until we're left with the course line of
one section of the continent we want to
cut out and in fact what I'm going to do
is I'm going to hit I on the keyboard
and I'm going to insert a point here and
then also delete this point so we have a
little bit of overlap with this Rift
here so L on the keyboard create feature
I'm going to make this an unclassified
feature playerity of 100 because the
blue Craton here has a plated 100 I'm
going to say begins life at a thousand
million years ago goes into the distant
future and all I'm going to do is just
call this line then I'm going to go next
next and I'm going to create a new
feature correction create and save and
save said feature collection as guides
and hit save
and then I'm going to go up to my guides
here set draw style and I'll just make
every guide black so next I'm going to
do the same thing I'm going to take the
geometry of the supercontinent copy it
turn it into a line but this time I'm
going to make a line for this Coastline
with a slight overlap over the ridge or
or the rift rather so X on the keyboard
and I'm going to begin deleting away
hit I I'm just going to make a short
little stop here
X again delete that point now up here
we'll have to manually add in points
which is which is fine it's not a big
deal
there won't be an awful lot of manually
adding things using this method
something like that and then I'm going
to run it down
here to get an overlap
right L on the keyboard create feature
again unclassified feature same data
except we're going to change the player
D to 200.
and we're going to put it in guides and
go create so now what we're going to do
is we're going to go to the topology
menu hotkey4 and then we're going to hit
B on the keyboard
for the build new boundary topology and
we're then going to select one of our
coastlines
so this line that we created and we're
going to come up to the right here and
hit add and you'll see that g plates
takes that line and then Auto completes
a polygon from it but obviously we don't
want this we want this to follow the
rift to cut out this half of the
continent so we're going to select that
Rift
and we're going to add that to the
topology and so with that done we're
going to go create here on the right
topological close plate boundary is fine
it doesn't make a difference this again
is a guideline plate ID of 100 let's say
it begins at a thousand goes into
distant future again doesn't matter
we're going to delete it in a second
we're going to call it Tuple next and
we're going to create a new feature
collection create and save that feature
collection as Tuple
and again we'll do the same thing for
the other side so four on the keyboard B
to build a new boundary topology then
I'm going to select the line
that we created along this Coast hit add
then select the rift and then add that
to the topology go create same deal
again topological close plate boundary
is fine next same data just change the
plate ID
and save it in Tuple so that is our
guide work done now what I'm going to do
is I'm going to select the Tuple and
you'll see it cut this out and
everything will be perfectly aligned
then I'm going to copy geometry's
digitize tool and just like before
create feature
continental crust
played ID 100 in this case to go with
the blue Craton begins life at a
thousand carries on to distant future
and we'll call it continent a
and we're going to save this
incontinence and go create and then
we're going to select that topology
again make sure it's the topology and
we're just going to delete it same
process for the other side
now all fair I already set the initial
super consonant to disappear at a
thousand million years ago so if we just
scroll forward we should be able to and
if we turn off lines or guides or other
we should see that we have one consonant
here
and one continent here and again all the
boundaries are perfectly precise and
also off air I set up a rotation file
exactly like we've done previously so we
can now move these feathers so I'm going
to skip forward 50 million years you
know the drill 5 on the keyboard then F
select the continent p
highlight children all enable pole and
we'll move these two no new information
here so I'll time-lapse my way through
this
now obviously you should use the command
shift K tool the kinematics tool to
check your speeds but I'm going to
assume we got that down so next we want
some flow lines right back to a thousand
million years ago
F on the keyboard
select our Rift
copy geometry digitize tool turn it into
a bunch of points M on the keyboard
create feature this is just like before
flow lines
left player D is 100 right later D is
200 begins at a thousand and what you
can do here
slightly different from the main series
you can just make the floor lines last
for each time step so we'll call this
flow lines
1002 950. this should mitigate so some
of the problems flow lines jumping all
around the place so next we'll add some
time steps so we'll go from a thousand
million years
to the end of this time step which is
950 insert a bunch of points hit OK
next and we'll create a new feature
collection create and save just like
before save this as flow lines
okay assume we've done that correctly we
should get some floor lines excellent
now at this point we usually just copy
the geometry of the floor lines to
create some ocean crust but let's be a
little bit more detailed right let's go
back to a thousand million years ago
let's hit F on the keyboard we'll select
the rift again copy its geometry this
time don't make a point keep it as a
line L on the keyboard then go create
and select mid ocean ridge
and really important here under
reconstruction method select half stage
rotation
and just like the floor lines put in the
relevant plate IDs this in my case blue
Craton is 100 and the green Craton
barely see it there up here is 200 this
begins a thousand million years ago
it'll go into the distant future and I'm
going to just call this mid-ocean ridge
1000.
next next and we'll create a new feature
collection create and save save that
feature collection as mid ocean
Bridges
and I'm going to go down to mid-ocean
ridges or up rather set draw Style
I make these a single color and I'm
going to make these dark red if you
don't see dark red hit choose and select
it from the color wheel alright cool
let's see what that gets us
so now we have a mid-ocean ridge that
perfectly matches these yellow dots of
the flow lines and is dynamically
updating it'll create a smooth
animation as our continent spread which
is just really cool and will lead to
kind of better more precise final
outputs so now we can put in some ocean
crossed before what we'll do again we
would copy the geometry of the flow
lines and manually move points around to
match things up using topologies we can
be a little bit more automated I guess
so what you can do is go back to a
thousand million years
F on the keyboard select the mid-ocean
ridge again copy geometry to digitize
tool make it a line hitting L on the
keyboard go create feature on classified
feature we're making another guide
reconstruction method is player ID and
we'll say we'll give this one the plate
ID of the blue Craton begins at a
thousand this future is fine and we'll
just call this line next next and we'll
put this in our guides layer and go
create with that mid ocean ridge still
selected I want to copy geometry
digitize tool again keep it as a line L
on the keyboard
then go to create feature same thing
again except we're going to change the
plate ID to 200 so one line is going to
go with this continent
everything that's the same next next and
go guides so now what happens if we turn
on our guides layer we will get two
lines that emanate from this mid-ocean
ridge that stick to the coastlines and
hopefully you can all see where we're
going to go with this in a second we'll
go to the end of the timestamp 4 on the
keyboard for our topologies and again B
to build a new boundary topology I'm
going to select this line that we've
made I'm going to hit add and then I'm
going to select the mid-ocean ridge and
I'm going to hit add and over to look at
G plates has like Auto completed the
polygon very cool Google create again
what you call this doesn't matter this
is again a guide next play the 100
recorders doesn't matter none of this
matters next next I'll put in topple and
we'll go create we'll do the same on the
other side so again we'll go to B to
build new boundary topology I'm going to
select the mid-ocean ridge I'm going to
go add and then I'm going to select the
coastline here and go add go to create
everything same
accept will change the plate ID
and we'll save it in topple
and just like we did with the consonants
then we can select our topples copy
geometry digitize tool create feature
this is ocean crust
player ID of 100 begins life at 9 50
into the distant future and we'll call
this
ocean crossed 950.
and we'll create a new feature
collection create and save and we'll
save set feature collection as ocean
cross just like before
oh and then what I'm going to do is I'm
go to file again like before import
import raster
and I'm going to select an ocean PNG
here gonna open it
doesn't matter next next everything's
fine creating a feature collection
wonderful I'm gonna go down to the ocean
there we just imported here I'll change
the name of the layer rename layer to
Ocean color yeah and then reconstruct
the polygons add new connection I want
to connect this to the ocean crusts
beautiful and I'm going to move the
mid-ocean ridges above the ocean crust
and I'll also move my guides above the
ocean crust and actually most things
will need to go above the ocean crust
floor lines should go above subduction
zones should go above Rifts should go
above cratons and continents don't
matter per se yeah okay cool and then
again F on the keyboard would select the
other topology copy geometry digitized
tool create feature same thing again
ocean crossed
potato you have 200 everything's the
same next next and pull in Ocean crusts
with the Tuple still selected delete
said Tuple it served its purpose
and then over here with the Tuple
selected delete that Tuple it has also
served its purpose so hopefully you can
see that using these topos should save
you an awful lot of time particularly if
there's a lot of ocean to fill in it's
far more efficient and neater than
manually drawing it in although it's
just it's not as intuitive okay what do
we need to do next we need to do some
drift correction same as before but
worth going over it for the sake of
reinforcement command or control M save
all changes then open up your rotation
file take the newest entry copious
immediately above it and change the days
to 1.0 same thing here
and for playlist 300 it doesn't matter
yet save close back in jupits command or
control M rotation file and then reload
and you'll notice that because the flow
lines were limited to just the times
that we're working in nothing's really
broken
which is kind of cool now at this point
let's split these two continents apart
just like before that means selecting
the failed Rift copying geometry to
digitize tool make it a line hit I and
extend it out so it severs the entire
place
L on the keyboard create feature you
know the drill Continental Rift next
plate ID of one that's our static player
ID
reserved for riffs plus hotspot related
things begins at 9 50 correct because
it's a distant future correct and this
is rift 950.
next next and we'll put that into where
is it riffs and call create so next we
need to split apart everything that
crosses the rift so everything up here
ocean crusts guidelines continents
abduction zones have to be made into one
thing unified by one plate ID and the
same thing down here I'm going to
time-lapse through anything that isn't
topology related just to save a little
bit of time the method is the same as
previously discussed
foreign
I guess worth noting here for this
mid-ocean ridge because we're doing this
half stage rotation we split it so we'll
end up with one copy that goes from 100
to 200 like we originally coded and then
here we want it to go from 100 to 300 so
right plate ID here we change it from
200 to 300 fairly self-explanatory but
just worth putting in and I'm pretty
sure
that's everything
split apart okay and while we're at it
we might as well add in missing plate
boundaries here because we're going to
use those later on to create entire
plates in a way that we wouldn't be able
to do in the manual section or at least
not comfortably so I know that this
content is going to want to go that way
and this content's got to want to go
that way so subduction zone will likely
continue along here and also here so I'm
going to put those in
L on the keyboard in fact actually I'm
gonna go f on the keyboard I'm going to
select that subduction zone copy
geometry digitize tool hit I on the
keyboard to insert some points and I'm
just going to insert a point here we
need not connect this up perfectly to
the end and you'll see why at the up
much later in the video
okay and I'm gonna go X
and I'm going to delete these points L
on the keyboard just so we get a nice
attachment here so create feature
subduction zone player D is 300 correct
begins at 950 correct goes to this in
future correct we'll call this sub
950. next next I will put this into
subduction zones and go create same deal
here
and here based on the movement of how
the continents how I want the consonants
to go
and in fact we'll talk about what's
happening up here later all right now we
decoupled these two which means going
controller command M saving all changes
going to reconstruction view total
reconstruction bolds equivalent
rotations relative to Anchor place and
we'll just shimmy that up there and then
we'll open up the rotation file and like
before we want to decouple 300 from 200
so I am going to take this line of 300
paste it above insert the current time
step 950.
paste that above find the coordinates
which in this instance are going to be
exact same as the ones already noted
above if I'm not mistaken they are so
I'm just going to copy those and I'm
going to paste them in this other line
here change the conjugate plate ID to
zero zero zero so it's no longer tied to
200 same deal here copy this fella paste
them above
and put in 1.0 here to make our drift
correction again I'm zipping by this
because it was covered in Greater detail
in previous videos this is just a sort
of recap
drift correction drift correction drift
correction fantastic save close
close Jeep lights controller command M
rotation file reload so assuming we've
done everything correctly we should be
able to move these two independently F
on the keyboard select the consonant oh
oh God we forgot to split the continent
nevermind sorry back up 950 so 4 on the
keyboard select topology just like
before we're going to go B then to build
new boundary topology we want to create
this new continent here so we are going
to select a line this line here we're
going to go add we're going to select
the rift we're going to go add and we're
going to select the other line here and
we're going to go add all going well
this should have created that shape for
us now it's not relevant here but it
will be when you have far more
complicated shapes when adding lines
like this or sections to the topology
make sure you work in a strict clockwise
or counterclockwise fashion so if we
start with this line with the next line
and a round or start with this line
follow the next line then this line if
you just like randomly add lines out of
sequence G plates will also complete the
polygon in just weird ways so always
work strictly clockwise or
counterclockwise really important so we
go create again it doesn't matter we'll
stick with what is auto completed here
play ID of 200 sure doesn't uh make it
950 yeah 950 doesn't really matter
because I'm just going to delete it
everything's fine next next put this in
topple go create we'll create a top hole
for the other side as well so again four
on the keyboard then B to build a new
boundary topology I'm going to select
this line here we're going to go add
and then again working this time in a
counterclockwise fashion I'm going to
add this line
and then I'm going to add this Rift
and we go create doesn't matter
the idea of 300 everything else is the
same next next and we go topple so now
we want to select one of our tuples now
you'll note here
there's a little bit of an inaccuracy
here and this is because when I placed
my point I didn't perfectly match things
up or actually rather when I split this
line it wasn't precisely split along
this Rift but that won't be a problem we
can fix it when we create the actual
condiment so we go copy geometry dizzo's
tool then go X on the keyboard and then
just delete this point here and
everything's gravy
G create feature continental crust
plated e of 200 or 200 there we go
begins iPhone 900 because in this future
cool and this is continent B
and we put that into continents
excellent now we'll select the other
topology and this one did work out need
for us which is cool copy geometry
digitized tool
create feature continental crust
everything's the same except we change
the pay to D to 300 and we put that in
consonants and we could do it then with
the topology still selected delete it go
back up the other topology
delete that and then go back to select
the main consonant consonant BC go to
edit feature controller command e and
then we are going to set that to
disappear at 9 50.
done
so now we should be able to move these
boils
so forward one time step five on the
keyboard then F to select the consonant
p and I'm gonna I'm gonna time-lapse
through this because there's nothing new
here it's just moving consonants like
we've always done
cool gravy same like before we got some
floor lines to add select the rift or
back one time step then select the rift
copy Jam which digitize tool make it
into a budget points create feature
flow lines left polarity is going to be
200 green right Peter D is going to be
300 the pink from 950 and again we'll
just do it per time step 950 to 900 flow
lines
950 to 900. next I'm a little ADD and
then we'll go 950 all the way to 900
insert a bunch of points go ok next I'll
put that in flow lines and go crash and
then we'll check if our movement is
decent yes it is no adjacent floor lines
are overlapping aren't we just awesome
so then we can select the rift again
copy geometry digitize tool hit L on the
keyboard to make it align go to create
feature just like before middle ocean
ridge very important half stage rotation
so left play Ready is going to be 200
again just like with the flow lines a
riper hoodie is 300 950 but this time to
the distant future mid-ocean ridge
950. next next I will put this into
mid-ocean ridges and go create
delightful I'm going to time-lapse true
adding the flow lines on these sections
here because no new information
so in keeping with what we're doing we'd
like to add some ocean crust now because
it goes flow lines mid-ocean ridge
guidelines ocean cross that's kind of
the workflow but there's this big old
hole here that's preventing us from
copying a line off this mid-ocean ridge
that can then be sent with this
Coastline here from which we can build a
topology so we're going to need to
complete this section here and we're
going to do so in a relatively new way
to kind of Aid in better animations so
I'm going to go back to 950 here and I
am going to select a section of ocean
crust so let's say or not ocean cross
sorry of mid-ocean ridge so I'm going to
select the middle ocean ridge here we'll
say
I'm going to copy that geometry I'm
going to hit I on the keyboard to insert
a point and I'm just going to insert any
random Point Beyond this line so like
through the triple Junction and Beyond
so just somewhere here we'll say
then I'm going to hit X on the keyboard
I'm going to delete away
everything that's a duplicate so we're
left with just this new section if it
disappears hit L and it'll come back I'm
going to go to create feature gonna make
this a mid ocean ridge
half stage rotation
plate ID is 100. and 200 because we're
copying it off the mid-ocean ridge whose
two plate IDs were 100 and 200. begins
at 950 goes into the distant future
mid-ocean ridge 950. next next I'm gonna
put this in mid-ocean ridges and we'll
go create okay so hopefully then we'll
see that it's just a continuation of
this Middleton Ridge and hopefully
you're going to see that what we're
going to do is continue each of these
mid-ocean ridges until they all meet at
a point in the middle so back to 950.
all right and now we have this
so very obviously not what we want so
what we're going to do is going to go f
on the keyboard we're gonna hit V and
we're just going to move these lines
around to make them intersect so let's
say we want an intersection Point
somewhere roughly in the middle of this
triangle so I'm going to go
here then I'm going to select the next
portion V on the keyboard
I'm going to move that to about
there perhaps then F on the keyboard
V move that and here's where we want to
be a little bit more precise
to get this point really Ash
that intersection
something like that is about as precise
as it can be I'm also going to insert
some points on these sections here just
to tidy it up a little bit because we
don't need all of this excess
so now I'm going to go X just delete it
back you don't have to do is it just
it's just a little bit neater
and delete this back okay cool let's
play it out and see what we got
beautiful and bearing in mind I've color
coded this Middleton Ridge dark red so
this isn't the final mid-ocean ridge
that we'll get these are again all
guidelines we can do a cool thing later
on regardless now we have some lines
that we can add to a topology to help us
create things quicker okay so now that
we got this we can create things called
toppo lines so far we've been working
with Tuple boundaries but now we can
create topple lines to really polish off
this mid-ocean ridge structure we have
here so I'm going to hit 4 on the
keyboard and this time I'm going to hit
I think is it h yes it's H or it's this
button here build new line topology and
just like with a boundary topology it's
the same thing you add a bunch of line
segments except this time it won't auto
complete a polygon it'll create a line
one that is dynamic and can be
elastically deformed which is cool so I
am going to select the first bit of the
mid-ocean ridge I'm going to add that to
the line then I'm going to add this bit
of the mid-ocean ridge I'm going to add
that to the line then I'm going to add
the next bit add that to the line and
then add this bit and add that to the
line okay we're going to go to create we
are going to go to
hmm what are we going to go to um yeah
mid-ocean ridge we'll do mid-ocean ridge
next
beginning time now we are going to put
its beginning time at the oldest section
of this line so this bit up here was
created all the way back at a thousand
million years ago so we're gonna say
this goes from a thousand million years
ago to the distant future and we're not
going to call this Tuple because this
isn't a guide this is the final thing
we're going to call this just Divergent
we're not going to give it a date
because this line contains within it
multiple objects of different dates so
we're just going to call it a divergent
boundary next next and we're going to
create a new feature correction create
and save and we are going to save this
feature collection as divergent
okay so now we take our Divergent
boundary here and we're going to move
all the way to the top
very cool looking yellow not a canonical
color for mid-ocean ridges so we're
going to twiddle down little drop down
arrow set draw style single color and
this time because it's finalized we're
going to make this bright range and
we're going to choose and you might be
like well big wolf why did you do that
the cool thing about topologies is that
you can add stuff to a topology that
doesn't already exist so if I get rid of
my middle ocean ridges there and scroll
all the way back to the start of the
simulation in fact I'll jump back for
dramatic effect we see that this line is
only yay long right because that's all
that exists of the bits that we've told
the line to contain and as we go through
this simulation it will dynamically
update as and when new lines appear now
that little glitch there don't worry
about it but to see here look at the
cool animation it's dynamically
expanding
very pretty so we will yeah again don't
worry about that it's fine that'll go
away in a second so we're gonna jump to
900 again
and we're going to do the same process
for the this section here
and this section here
and if you turn on Divergent we'll see
now we have a full set so I think
hopefully now that little glitch there
will be solved
yeah perfect so it will turn off middle
ocean ridges again and have just have a
look at how smooth this animation is
it's so cool
oh damn it it's still there wonderful
so those little glitches they usually
resolve themselves though not always G
plates is still G plates and I think
it's likely a consequence of not being
entirely precise at the triple Junction
in the dry run I did of this video it
was perfectly smooth G plates giveth G
plates take it away okay let's do some
Coastline stuff and then again the more
the more stuff you have to fill the more
topologies really help so I am going to
go to 950.
dear Lord what even are you doing there
giblets regardless I am going to select
that
crazy line I'm going to go to cup
pajamas digitized tool I am going to
turn it into a line and chances are if
it's because of inaccuracies you have to
triple point I should just be able to
delete these two points and all this
gravy
yeah and that is the case so it's just a
mild inaccuracy L on the keyboard create
feature unclassified feature uh this is
by plate ID and we're going to send this
up with 200 the green Craton 950 and
yada yada that's fine that's all looks
good to me line and save this in guides
and go create I'm going to do the same
thing for each divergent boundary
oh look at that a well-behaved line
thank you very much
okay now that we got all of our guides
say with me to apologies so four on the
keyboard B to build a new boundary and
we can select this Divergence on ADD it
select this diverting Zone add that
create feature sure topological closed
plate boundary next player D200
900 and just Tuple
and saving Topo and go create same thing
for this topology here and this topology
here
and I suppose it's worth making explicit
the way I'm working here like I created
all of the guides all at once and I just
created old apologies all at once and
then I'm gonna do all the ocean crust
all at once and the reason for this is
that g plates remembers menus to a
certain extent so if you create all like
features all at once you can Blitz
through the menus really fast
if you went like guide topple ocean
crossed guide tapple ocean crust you'd
have to constantly re-enter all the data
into the menus so work with one class of
features in one goal and then move on to
the next speaking which ocean crusts so
let's select that Tuple copper German
digitized tool and again here here's
where it really comes in clutch like
it's such a big amount to have to draw
in we just go create feature old and
crust
play IDF 200 created at 900.
Polson crossed 900 now that's the data
filled in for the menus so all we'll
need to do is just change the plate ID
and Blitz through the menus and put it
into ocean crust and go create boom with
the Tuple selected delete it select next
apple
rinse and repeat so you don't even need
to read any of this I just go next next
next and go create because everything's
already Auto filled out and then delete
Tuple so there's kind of a there's kind
of a Groove you can get into uh to make
things go quicker I won't say quick
because like it's G plate but quicker
change the parody and then everything's
fine next exercise next create done oh
sugar and that top all we need to get
rid of topple and delete boom let's have
a play
oh things are drifting back so we'll put
in some drift correction command or
control M save all changes open up a
rotation file or more accurately open up
the rotation file don't just open up a
random rotation file that's not going to
do any good and we'll take our 900 time
step coordinates and paste them into
drift correction one
two
and
three save close G plates controller
command M rotation file
reboot and once again the rotation lines
haven't broken because we're only
limiting them to a single time step so
that is
basically the gist of this video that is
how you use topologies in terms of like
creating love and cross to moving
contents around you can also use
topologies to create entire plates so
you can make cool animations of your
plates growing and shrinking over time
this is always a very much trial and
error process for me like I haven't got
like a kind of slick ABC style workflow
to make this happen so this this portion
of the the video might get a little
messy but I'm still very much trying to
figure out the the slickest way of doing
this okay so let's start with the easier
plates namely plates B and plate C so
I'm going to start there I'm going to go
back to the start of the simulation when
this section of the divergent boundary
first appeared I'm going to select a
mid-ocean ridge the mid-ocean ridge copy
geometry digitized tool I'm going to
turn into points I'm going to hit X on
the keyboard and I'm going to delete
back
all of these points
until we're left with just one here okay
and we're going to use as a kind of
anchor you'll see in a second so create
feature this would be an unclassified
feature plate ID oh no it doesn't go by
plated he has to go by half stage
rotation it must remain equidistant
between player D100 and play 3200 begins
at a thousand continues into this in the
future and I'm just going to call this
point
again no point dating it it's just a
guide and therefore goes into guides and
go crazy okay so that will stick that
black dot bit hard to see but that black
dot there will stick with the mid-ocean
ridge the entire wave through the
simulation okay now I want to do the
same thing here so that first appeared
at 9 50. I take it so you got F on the
keyboard I'm going to select that
mid-ocean ridge
copy geometry digitized tool turn it
into points by hitting M hit X
delete back these points
so we're just left with the edge one
there m on the keyboard to bring it back
create feature
on classified feature a half stage
rotation
this is between
200 and 300.
begins at 9 50 and we'll call it a point
and we'll put into guides okay so now we
have a point here and a point here
perfect so we'll go to the end of the
simulation then and we're gonna hit 4 on
the keyboard and then H to build a top
hole line and basically what we're going
to do is much like with the Divergent
zones here we're going to make a
Convergence Zone a subduction zone outer
topologies so I'm going to select that
point I'm going to add it
I'm going to select this point again
work in a logical sequential manner and
add this abduction Zone
then I'm going to add this subduction
zone and then I'm going to tie that to
this point and go add okay you'll see
that order competes for us very nicely
we go create this is a subduction zone
begins at the time of the earliest
section which is a thousand million
years ago in this instance and this is
not Tuple this is a final thing so we're
going to call this converge and
convergent next next create a new
feature connection create and save and
we will save this as
convergent
and we'll close and we'll take
conversion and pull at the top it's
already there excellent we're going to
give it a color indicative of Seduction
zones
the canonical blue color
okay so hopefully then out of all points
in this simulation with a few receptions
there will be a complete boundary on
this plate now
so it starts
here
okay cool nice okay so let's do the same
for this boundary here so immediately
the first thing I think I want to do is
put in another Point here a little
anchoring point so go over to a thousand
F on the keyboard select that mid-ocean
ridge designs tool make points hit X and
I'm going to delete back
until we're just left with that one
point create feature unclassified
feature half stage rotation this is
between 100 and 300 begins at a thousand
is a point next next and put this in
guides and go create okay so this is a
little trickier remember the movement of
this BC content is that away so we have
subduction zones to the north and to the
east because it's traveling this short
Direction this isn't a divergent
boundary it's not a Middleton Ridge it's
not a convergent boundary it's not a
subduction zone because that would
indicate movement this way as well
downwards to the South which isn't
occurring at this stage so therefore by
process of Illumination it's gonna have
to be the third type of boundary a
transform boundary so I am going to and
I think this will survive God I hope so
I'm gonna select that subduction zone
and I'll make an anchor here so between
these two points then I'll be able to
create a topple line for transform
boundary so I'm going digitized tool
turn it into points hit X
and go M create unclassified feature and
now not half stage rotation plate ID and
this is going to go with 300 so it just
sticks to that subduction zone begins at
a thousand yada yada next amberport link
guides with these two points now
hopefully I should be able to go to four
and then go to H to build a line I'm
going to select that point I'm going to
add and then I'm going to select this
point and I'm going to add right it
could create a line for us we go create
we'll make this a transform boundary
begins at a thousand sure we'll call it
transform next next and we'll create a
new feature collection create and save
and we will save this as transform
I'm gonna go close Twitter down the drop
down menu set draw style canonical
Transform boundary color is green and go
choose okay so let's see what we got
thus far
okay cool right so that's everything's
gravy there
but at this point the transform boundary
because the mid-ocean ridge has opened
up and this content is going this way at
this point that transform boundary turns
into a subduction zone so I'm gonna go f
on the keyboard I'm going to select that
edit feature doesn't go into the distant
future just goes till
9.50 okay let's see that and again very
much trial and error sort of stuff here
goes along bam cool right brilliant okay
so now we're gonna need to make this
subduction zone so again we'll make a
line we're going to take this subduction
zone and in fact actually no we're going
to take that point
I'm gonna add that
we're going to take this subduction zone
and we're going to add that
and then we're going to take that line
and we're going to add that
so it's going to continue and then we
can just skip across here
and attach it to this point because
that's all one big subduction zone at
this point so we'll go create
convergent or not convergent subduction
zone begins at the oldest piece is at a
thousand
and we'll call this Con version next
next I'm a potted in converter to create
okay let's see how that turned out
gravy gravy gravy gravy all right
consonant one the hardest content so
again we'll scan true so what's
happening here this is going in a
Southwestern Direction so we have
subduction zone along here
that subduction zone will just continue
all the way along don't feel comfortable
calling this a subduction zone as well
don't feel comfortable calling it mid
ocean ridge so again bypasses in
relation we're going to have a transform
boundary all along here for the entirety
of this Plate's existence I think so
let's do the convergent boundary first I
think that's the easiest so we'll select
this chap We'll add him we'll select
this subduction zone and add that and
then here G plates can also complete
across to this point
and we'll add that
okay create
subduction zone all this portion is a
thousand million years ago great
convergent next next save and conversion
and go create
all right so again smooth
dynamically updating boundaries pretty
cool and just like before with spanner
Transform boundary along here so I
figure I'm going to need another Point
here so I'm going to take my subduction
zone copy drums digitize tool create a
point x
M on the keyboard create feature on
classified feature plate ID it has to go
with everything that's 100
000 yada yada good pulling guides good
and then four and H to build a line
select point
add select the order Point add that g
plate autocomplete wonderful create this
is a transform a thousand yeah not
conversion
transform
next next and we'll put this in
transform and go create
okay cool now I'm glad this came up
right so have a look G plates again do
an admirable job it's just creating like
the shortest straight line distance
between here and here between these two
points but notice as we go through the
simulation this cuts across the ocean
crust which is not wonderful like we'd
want this awesome cross to be contained
within this plate here so what we can do
what we can do is we can create a line
here or a series of points if you still
desire such that this line snaps to it
we include this portion of the line
in the topology so if I go to I think
950 will do us yeah at 9 50 I'm gonna
draw when this first is created I'm
going to draw this line here and I think
a line is probably the way to go and I
think just for the sake of neatness and
making sure every all these points are
exactly where they should be I'm going
to take this topology here copper
geometry digitized tool turn it into a
line hit X and I'm going to delete away
these points I'm left with this line
where the vertices are precisely
matching with already established
vertices
L on the keyboard create feature on
classified feature plate ID of 100
correct begins at not a thousand begins
at 9.50 and we'll call this
transform humble data to 950. next next
and we'll create a new feature
correction for this create and save
because this is like a transform guide
save feature collection as we'll save it
as transform
faults okay and then we'll go to our
transform faults where are you you are
here twiddle down we'll set draw style
and just like we did for the subduction
zones in the mid-ocean ridges we'll just
give a dark version of that color so I
have pre-set up dark green so we'll make
this dark green and go choose hard to
see I know but it is there and it is
dark green so at this point when this
bit of ocean cross is created I want
this topology to conform to this line
okay so what we can do here is we can go
four on the keyboard to bring up the
topology we can select this topology and
then new feature here we can go down to
the bottom here edit topological
sections or e as a shortcut now
this menu is not wonderfully designed so
bear with us
you'll get it eventually it's just it's
a bit obtuse I'm just going to pull this
up a little bit here so we can see
what's going on
so look what we got here we have a green
feature that's labeled unclassified and
then a blue feature that's labeled
unclassified and then we have this
insertion point indicates where new
topology section will be added and if
you look up on the screen here we have a
green unclassified feature that's our
point and then we have a blue
unclassified feature which is also our
point we want to add this line in
between this point and this point so
what we're going to do is we're going to
hover over actions this is actions
column here and we're basically just
going to randomly kick click buttons
until this insertion point Falls between
our two unclassified features so I think
it's just up once should do it yeah so
we have on classify feature put stuff
new stuff in and then unclassified
feature right so what I'm going to do
then is I'm going to select that line
and I'm going to add it to the topology
and it snaps and we go apply right so up
until that point now again this won't
result in a perfectly smooth animation
and I'm sure with points and stuff you
could make it conform earlier but for
the sake of demonstration this is good
enough so this line is spanning between
the two points up until 950 at which
point is snaps again not the smoothest
thing in the world but fine
and then from there on in it's plain
sailing excellent let's have a play and
see what happened
perfect cool that's perfect and so that
brings us to the final thing in this
video creating actual plates so if we go
back to start simulation so notice we
have a bunch of lines representing our
plate boundaries we can add them
together to create a topology for our
plates so let's do that let's start with
this plate here so again four on the
keyboard for topology I want to create a
new boundary topology I'm going to take
again work clockwise or counterclockwise
very important I'm going to take this
convergence on make sure you take the
Convergence Zone and not the subduction
zone take the topology so we're putting
topologies in topologies here so I am
taking the convergence on I'm gonna add
that to my boundary I am taking the
Divergent Zone this one here again make
sure you take the topology add that and
then I'm going to take the transform and
I'm going to go add that and again
hopefully as we scroll through
we should see
this yeah that shape dynamically
perfectly within reason marks out our
play boundary wonderful absolutely
wonderful so we're gonna go to create
this one we're going to call a closed
plate boundary we go and go next we'll
give it a play ID save 100 all this
portion here is a thousand million years
ago so begin in a thousand million years
and it continues on to the end of the
simulation and we're just going to call
this plate
a
next next and then we go create new
feature collection create and save and
we'll save this feature collection as
plates okay so then I'll take my plate
and I'll put them below our boundaries
here
so the boundary sit on top of the plates
and then till down the drop down arrow
go to fill polygons and I will drop that
down to a very low opacity something
like that okay so now we have our
tectonic plate dynamically updating and
morphing over time
oh cool I love this so much and get okay
let's do that for rest of them so we'll
go 1000 now here we have one plate that
will later split into two so we'll have
to keep that in mind again four on the
keyboard create boundary topology B on
the keyboard and I'm going to add this
subduction zone not subductions I'm
sorry Divergent Zone we're going to go
add again make sure you select
topologies then we're going to
oh let me
think okay I'm going to add the
convergent I may need to go back and
import the transform boundary as well no
no it has to be transformed nevermind
transform add then I want to add again
look I'm working in a counterclockwise
manner here
then I want to add the convergence on
ADD and then I want to add the other
conversion Zone we'll add that now there
may be an issue here with overlapping
boundaries we'll we'll see and we'll bug
fix it if needs if needs be so I'm going
to go create close plate topology
wonderful this has a plate ID of 200.
it begins at a thousand yes but it only
lasts until 9 50 at which point it spits
off into two other plates and this is
plate BC and so I'll put them in plates
and we'll go create okay so um that that
opacity is quite low hold on
it's a little bit better
all right we're good we're good it
worked out okay cool all right 950. so
again at 950 we have splitting so this
becomes its own plate and then this
becomes its own plate so again four on
the keyboard create new topological
boundary B on the keyboard select that
divergent boundary the Divergent
topology we may need to do some editing
here because uh that could cause an
issue but we'll see we'll go to add and
then hold on a second we want to add
yeah and we can just add all of this
section and we should be fine we should
be okay okay create close play boundary
play ID of 200 great this will begin at
950 and go into the distant future and
this is just when we play B so next next
and put in plates and go create have you
broken anything God I'm being remarkably
lucky here sandboxing this did not go
Source mood but then again sandboxing
this didn't produce this weird artifact
here so you know again G plates give it
g take it away okay and now the final
plate and that is Austin four on the
keyboard B to build a boundary and again
I want to go I want to take this
divergent boundary I want to add it I
want to take this conversion boundary
and add that and that's perfect that
should work create
close play boundary playerity of 300
begins at 950 goes to the end that is
plate C next next and we'll put that in
plates and we'll go create and does it
work oh my God I'm so lucky today yes
excellent and then again having the
boundaries in having the plates in at
this it just enables you to produce more
animations and have more information
about your Bros like just so cool in my
opinion and I mean just look how cool
that looks like it's so cool it's all
cool all right that was that for this
video and for this whole like mini
tutorial section like I said it starts
World review next time thank you so much
to World building pasta whose
methodology this is thanks to vangavang
Gog resident artist thanks to you for
watching thanks to the patrons for
supporting the show you are all
beautiful beautiful nerds until next
time
Edgar house
thank you