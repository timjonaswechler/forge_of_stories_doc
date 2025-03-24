# Using Blender to Map Directly onto a Sphere - Worldbuilder’s Log 25

good morning interweb War Builders log
25 polar Distortion we all hate it the
bane of every single World Builders
existence planets are 3D spheres when
you project their surfaces onto a 2d
plane the shape of the landmass is
distort and transform with respect to
whatever projection is being used near
the equator Distortion isn't too bad but
up near the poles it's a disaster now I
had said that what we're going to do is
we're going to just draw in the map
bring it into G plates look at what's
going on visually corrected in
illustrator rinse and repeat but
literally this weekend I came across
this tutorial by this chap here called
elnu how to use blender to paint on a
sphere for Fantasy Maps which if you're
anything like me was a mouth-watering
title to come across so in this video I
want to implement lnew strategy here
this video was not planned at all this
may be a disaster so let's just take it
as a bit of an experiment can we use
blender to do this Step 1 open up
blender well actually Step Zero probably
download blender but it's 2023 I'm going
to work on assumption you can use Google
and you can find a download link it's
not that difficult for those who don't
know blender is a free open source
cross-platform 3D I guess modeling
software seems really cool I know
literally nothing about it I've had a
one day's experience with it so here we
go first things first we want to click
on just new file just general will do we
have this viewport how very pretty there
are a number of different ways I think
one can manipulate the viewport but it
depends on your input device like
whether or not your Mouse has a scroll
wheel that sort of thing so I'm gonna go
for I think the most universal way of
manipulating the viewport and that is up
here you can click on this XYZ axis and
you can just twiddle things around you
can zoom by clicking on this little zoom
button up here and you can use this hand
to pan and so you can move in 3D space
pretty simple now we do not want a cube
that is no good planets not cubes we're
going to hit X on the keyboard and we're
gonna go delete I'm gonna go up to add
here alternatively hit shift and a I'm
going to scroll down to mesh and then
down to UV sphere hey Presto it's a
sphere now at the bottom of your screen
you should see an add UV sphere here
click on that number of segments uh one
two H Rings 64. this is what elnu
recommends I would suspect this depends
on what your computer can handle so I
think you want to go for as much as
possible I think again not an expert uh
radius I don't know if this makes any
difference at all but I like to just
fill up the viewport so I think three is
about three four is about right
I don't think it really matters with
that done right click on your sphere and
then go to Shades mood how very pretty
one sphere so what we want to do is we
want to take the map we've been drawing
in illustrator exporters and wrap it
around this sphere so back into
illustrator and we want to take all of
our guides with us I think yeah you want
we want to see all of our erogenies etc
etc so file export export for screens
label it base map and then hit export
back in blender we're going to go over
to the right here down to this button
here material properties and we're going
to go new
then we're going to scroll down to
surface then click on emissions and then
in color we're going to click on the dot
here and then go over to image texture
so then we're going to hit open and
we're going to load in the base map we
just spat out of Illustrator so locate
that here
and hit open image nothing happens how
sad let's fix that pop up here to the
top of the screen and click this button
which I can't make out because my mouse
is giant so just hit that and hope the
rest there we go beautiful and again we
can navigate around we can look all
around our globe everything's pretty
yada yada yada oh and I should stress
again this will only work if you export
an equirectangular projection of your
world that is two to one base map you're
bringing in has to be twice as wide as
it is high otherwise it won't wrap
correctly okay now we want to try and
draw on this and what we would like to
do is we would like a blender to treat
that which we've just wrapped around
this globe as like a base layer and we
want to create like another layer above
it that we can draw on and then use that
to bounce it out of blender
so to do this we'll go to shading
because you know obviously
um and then we're going to go right
click we're going to oh no we're not
going to right click we're going to go
shift a to add and in the search thing
here just type image texture and then
just drop it down wherever
so think of the base map here as layer
one this is going to be our blank Layer
Two drag these two Fellers over here
shift add again or shift a search and
then type in mix and click on mix and
drop that somewhere in between these
boils and these boils so see the way
these two are joined we're going to
attach them click on the little node and
just drag off
delightful next you're going to come to
the mix here and from float you're going
to go to Color you're going to take the
color node from base map and you're
going to stick that into mixes a you're
going to take the color node from image
texture and you're going to stick that
into B then you're going to take the
Alpha from image texture and put that
into factor and then the result from mix
goes into color and then final step is
you go to new on image texture and this
is the layer you're going to draw on so
whatever you want to call it sketch
whatever a heightened width again this
has to be two to one and I think you
should try and make this as big as
possible my base map in illustrator is
5000 by 2500 so I'm just going to pop
that in
then for color I'm going to click on
color I'm going to go to Alpha and I'm
going to just click and drag all the way
down until we get to zero so it's
transparent and I'm going to click off
that make sure Alpha is checked and then
hit OK
so we have our base map layer we have
our sketch layer it's getting mixed
together and it's getting outbutted to
produce this at least that's my
understanding of it could be totally
wrong and in fact I think the idea of
layers is probably the wrong mental
model to have in one's head but I know
nothing about blender so here we are so
with that setup we are now going to go
over to texture paint now if your Globe
is looking a bit stupid uh just go over
here again and click on the tool that I
can't make out and everything should be
fine you see here we have a viewport for
3D space and here we have a viewport for
what that 3D space is doing except
projected onto a 2d map pop up to the
top here and click the little drop down
menu and go to sketch so showing the
sketch which is blank how wonderful okay
so now make sure that you're on the draw
tool pop on over to the right you should
see draw written here select the layer
you want to draw on in our case that
would be sketch go down to strength here
if you're using a drawing tablet which
you should be
deselect this icon here that means the
opacity of your stroke will remain
constant regardless of pen pressure then
pop down to color and you may as well
just make this a black
and the final thing of housekeeping go
down to fall out here and if you want a
soft brush keep it as is if you want a
hard brush which I prefer uh change it
to this setting here so hopefully if
we've done everything correctly we
should be able to grab our stylus pop on
over to the globe and we should be able
to make a line and it will automatically
project onto our 2D map here let's go
now to get rid of that line you go
command Z or command or control Z
wonderful to change your brush size use
the left square bracket key to make it
smaller and the right Square back key to
make it bigger now in theory there's
another way of erasing stuff just heads
up so if you draw a line in theory you
should be able to right click go to
where it says mix here and put that to a
raise Alpha and that you should be able
to paint over the line and erase it now
it's working now but in my testing I
found that it like was really flaky and
I couldn't reliably predict when it
would work and when it wouldn't work
that's almost certainly because I'm a
total novice of this app so you know
just a heads up there so put that back
to mix and that means we're going to
draw
a positive thing wonderful okay so let's
pop down to a polar region and put this
to the test so I'm going to come down
here how beautiful I'm going to zoom in
how wonderful oh FYI if you just keep
zooming you'll end up popping through
the sphere so I'm now inside the sphere
don't do that so I'm just going to come
down a little bit
oh I am stuck inside my sphere
what is going on oh dear
oh dear
okay hold on a second okay I'm back that
took way too long uh Google tells me
just hit shift C to get rid of that I
think that's like set the camera back to
an original state or something anyhow
where were we pole okay we're going to
poll and we're going to zoom in careful
Edgar okay pull I'm gonna drop my brush
strength down or brush size down to as
small as I can get it
um while still maintaining kind of a
strongish
um black line
yeah so one pixel at the zoom level
wonderful and just for demonstration
purposes let's just draw some sort of
shape here
okay something like that now you'll
notice there are gaps in the line and
you'll notice that the pixels are kind
of doing weird things
I think this is because the pixels are
being kind of like distorted around the
sphere as well like if I come around the
pole here and draw like a circle you'll
see it has this kind of like um radial
sort of effect which you know it's
unfortunate because we're dealing with
raster stuff here not with vectors and
so we're just gonna have to deal with
that there's not much we can do about it
but in any case let's imagine that is
some amount of elevation that will now
have been copied to this map here so if
I zoom in
and try and locate us
it's very hard to see because of the
background colors but there we have it
there is that shape projected out
correctly now the only issue is that
there's these triangles here that again
um not cheap plates blender is using to
wrap this around the sphere
for for some reason
um it cuts out the shape
or these these triangles overlay the
shape and it cuts them off I've not
tested it but it just occurred to me we
could come in here and draw on this
plane
and like complete
the shape here perhaps if we wanted to
but like we're going to be doing that in
illustrator anyway so I don't think
there's much need just be aware that
near the bottom of the map you run into
this issue where it's like segmented I
don't think there's any fix for that I
haven't been able to um
work one out in my testing all right so
let's say that's done then we go up to
this fella here uh that's not where I
want to go uh not at all sorry you go up
to this fella here and then you go to
save as and then you save that somewhere
convenient it's delightful and we may as
well save the whole project
so that's file up here and then save as
okay and now we pop back into
illustrator I am going to locate that
file we just spat out of blender
oh make sure you save it as a PNG I'm
going to drag and drop and place that
onto our map
all right we'll move that into guides
lock guides and we can scroll down and
see there it is and from here it's the
same as usual
select an elevation come down and on the
keyboard for the pen tool and then we
start
painting
so on and so forth something like that
and you'll end up with um insofar as
possible correctly projected geometries
obviously there's going to be issues
here with this gapping that occurs and
the fact that blender deals with pixels
and that means the pixels themselves are
going to be distorted leading to varying
line thickness which has some
imperfections inherent kind of with that
but overall you'll be in the kind of
right Ballpark and that is basically
that now like I said this is all a big
experiment I've yet to actually do this
to completion so to speak so I might
come to regret these words but I think
the best way of doing this is to do this
one elevation step at a time so go into
blender Mark out all the areas of a
certain elevation export that PNG put it
into illustrator Trace over it and then
back into blender put in the next
elevation area something like that
export that house the reason why I don't
think it'll be wise to do all the
elevations at once is that again these
lines are quite thick even at one pixel
and they're distort so you can imagine
if you were to come in here with another
elevation here and this one here needs
to be really tight for example
you'll see that it just kind of Causes
Chaos over here so making each elevation
its own
PNG I think I think is the play here so
we're going to time-lapse now at the end
of it I'll let you know my thoughts on
whether or not this method is in any way
useful wait sorry sorry one last thing I
forgot to mention
um brush size is a bit weird in in
Blender at least from someone who's come
from illustrator Photoshop Etc you see
here it's set to one pixel right and
that means we get lines that are yay
thick but if I zoom out
and still with the brush size set of one
pixel and draw some lines you'll see
here the lines
are not the same thickness we zoom out
again if we zoom out really really far
and then go and draw a thing it's like
basically half the globe is covered by a
line I don't think this Behavior can be
turned off and it's not oh no I'm inside
my Globe again okay shift C
deadly learn something new see I don't
think this Behavior can be turned off a
little bit of Googling tells me that in
other modes in blender I think it was in
the modeling mode this you can set the
the sort of
size of your brush to be relative to the
viewport and not the zoom level or
something nonsense like that either way
this is just something you're going to
have to contend with but because I would
Advocate using this to make guides you
don't need to be that precise the
Precision will come in illustrator so
that is that time-lapse mode Picard
Topography is a goal I will talk to you
in a little bit
thank you
foreign
foreign
foreign
foreign
foreign
foreign
foreign
and after all of that here is where we
are ash maybe just me but I think Picard
is looking pretty tasty and I gotta say
this blender method shout out elnu again
please go show the guys some love links
in description is pretty good like it's
not perfect perfect will be a 3D app
that will allow you to work in vector
graphics at least that would be my
perfect basically G plates but with the
ability to be able to draw and not just
Place vertices but short of such an app
existing this is probably the best
method I've come across to deal with
polar Distortion if you're going to hand
draw things again not perfect like
overall on the macro scale the
morphology is is good it doesn't look
you know broken and artifacty but when
we zoom in because the pixels are being
distorted
there are artifacts down here but it's
really like it's really not too bad
and can be mitigated somewhat by not
having a ton of detail really tied into
the pole so I like this it's got my vote
of confidence definitely going to be
using it for when we talk about fjords
up here in the northern portal regions
so before I go
um we'll do a quick stock take here just
figure out what's happening next I think
the next step I'm going to do off camera
because it's hella boring and just is an
extension of everything we are talked
about and that is I'd like to do a bit
of blending you'll notice that we've
dropped in all of our erogenies here
we've taken our Jeep plate stuff and
we've converted into our atlas map style
world map great but we've ignored the
cratonic areas here the areas with big
ass cratons
and they haven't got any attention such
that we're in a situation where we have
these vast vast extremely flat extremely
low-lying planes
which you know is fine but it's not
something we see on Earth at least not
to this extent like this here is Earth
I'm sure we're all familiar with it if I
raise the sea levels up by 100 meters
everything that's kind of this I guess
light purple here is crustal material
between zero and 100 meters in elevation
and you can see it doesn't make up a
huge portion of the globe and if you
compare that to what I got this tear
color makes up a massive portion of the
globe so I need to do some sculpting in
here effectively what I'm going to do is
I'm going to treat the cratons as being
like effectively flat because that's
what they would be but with a slight
like dome-shaped elevation as in their
higher in their middle and then use that
to blend them into the topography some
more it's all pretty mundane I don't
think it needs to be on video so after I
have that done then it's on to seafloor
topography which I can't decide whether
or not that should be a video or not I
find it hard to gauge whether people be
interested in that so I want to leave an
informal poll in the comments see floor
topography on video yay or nay leave me
your thoughts alright I hope you enjoyed
have a great one folks and until next
time
Ed grouse