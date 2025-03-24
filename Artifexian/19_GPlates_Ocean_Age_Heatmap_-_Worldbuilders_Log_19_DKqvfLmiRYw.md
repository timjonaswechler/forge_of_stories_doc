# GPlates: Ocean Age Heatmap - Worldbuilder’s Log 19

good morning interweb War Builders log
19. now I said I was going to talk about
topologies in this video but I'm
actually going to leave those until the
next video because in this video I want
to fix an error from the previous video
or a hotspots or specifically hotspot
Trails I want to talk about ocean age
heat maps and show you how to export
stuff from G plates all going well this
would be the penultimate episode in this
tutorial portion of the series so first
on the agenda hotspots turns out I've
been doing hotspots completely wrong
this entire time this Trail here is
actually not representative of what the
island arc that the hotspot creates will
look like and to demonstrate this off
air I made an island chain layer here
which looks a little bit like this if we
play true you'll see what's going on
here
every 10 million years I spat out a Dos
representing an island
from this hot spot here and you'll note
that the shape of the island chain
is similar
to the motion part that we put in in the
last video but like flipped and rotated
so we need to fix this motion path to
reflect what the actual State of Affairs
would be now this actually turned out to
be non-trivial to fix a y-filed I spent
days at this but I think I finally got
it so what we're going to do is we're
going to need to open up our rotation
file and in the rotation file at the
very top we're going to need to make an
entry for plate ID one
so something like this just like we did
before I suppose the only thing to note
is that plate IDs are always three
figures so Plato D1 is zero zero one
really important I'll get rid of the
line break
save it up close text editor go back
into G plates controller command M and
then I'm going to go to the rotation
file and I'm going to reboot it
crucial step without that entry in the
rotation file the hotspot path is just
never going to look right so I'm going
to go f on the keyboard I'm going to
select the erroneous hotspot Trail and
tether to be gone and just keep things
clean and what's going to turn off my
demo island chain here as well I'm going
to go back to where the hotspot first
formed so in this case it was 660. hit F
on the keyboard I'm going to select that
hotspot copy geometry's digitize tool
hit M to create a point go to create
feature motion path hit next and here's
where this differs from the previous
video in plate ID we're going to put in
one and then in the relative plate ID
we're going to put in the ID of the
plate that's overriding the hotspot so
this is the green stuff for me so in
this instance it is 101. we're going to
say that this begins at 660. it goes
into the distant future and we want to
call this hotspot Trail
660. next I'm going to hit add insert
multiple times from 660 to 0 in SEPTA 10
million years insert
Bingo okay
next and then we'll save this in hotspot
trails and go create now as you've done
this correctly we should get a motion
path that reflects reality so let's play
that looks a lot different to me and
just to confirm I'm going to turn on my
Islander chain layer again and now it
perfectly matches up and just for the
sake completion I am going to time lapse
fixing this hot spot as well same
procedure
okay next on the agenda ocean age heat
Maps this is super easy if we go to our
ocean crust layer here which is down
here to the download drop down menu go
to fill polygons and then go to set draw
style feature age and then default oh
and also go to fill opacity here and
bring the opacity back up to one
and what we'll get is we'll get a heap
map based on the age of the crust and
that's why during this procedure we were
really meticulous about dating all of
these crusts very precisely so we could
end up with this outcome so I'm just
going to quickly play through the
simulation just so you can see all this
happening
foreign
which I don't know about you but I think
this looks absolutely baller and of
course this thing of coloring things by
feature age isn't limited to just
oceanic crust any layer here which
you've meticulously dated things you can
apply this coloring too and you'll get a
heat map which is just so cool and
finally let's talk exporting whatever is
shown in the viewer here will be what is
exported so if you got anything hidden
it won't export therefore it's probably
worth going through and just selecting
and deselecting everything so you get
like the right look you're after for
example you could come down to your
ocean layer here and you could unclip it
from ocean crust so you get to fill in
blue around the whole globe and then you
can turn the opacity back up
you can do the same thing for the land
layer turn the opacity land layer up
Etc make it look the way you want it to
look next step is to select a projection
we've kind of like implicitly been
talking about these already but you have
your standard glow projection here
rectangular projection is extremely
useful for exporting maps and
re-importing them back into other
software like G projector or mapped
globe that sort of thing I tend to work
in rectangular all the time Mercator has
a world map isn't great you should
probably avoid it mold reader or more
wider I don't know how it's pronounced
is really good for just displaying
something finalized world maps look good
in wall reader same stick with Robinson
next what you might want to do is move
the orientation of what you want to
export so you can go to view set
projection
you can select one of your projections
here and then select a central meridian
so for example let's say I go for a
Meridian Ash 30 degrees we go okay and
we'll notice that the whole globe the
whole view has been skewed over 30
degrees longitude now obviously this is
cut off that's not very good you could
just manually move it back or you can go
to view camera location set location and
enter in the same Meridian value in
longitude here so for me that was 30
would go okay and now it's positioned
back in the center oh and speaking of
the view menu if you don't want to see
the lines of longitude and attitude and
go to view configure graphicals and then
set these all to Zero longitude Delta 0
or rather latitude Delta to zero and
longitude Delta to zero two and hit OK
and then all the graticules are gone so
mess with layer visibility select
projection mess with the rotation and
then we're ready to export so we'll go
to reconstruction export that's
controller command plus shift and E and
we get this dialog box so we have two
options here we can export time sequence
of snapshots or export a single snapshot
instance we'll do this one first this is
basically just taking a single still
image of your world so I would ask you
for the time of the export let's say we
want the current time we can just hit
use main window time and then we're
going to add export now there's just
like a bucket of options here the only
two you really need to be concerned with
is projected geometries which gives you
an SVG file so if you're working in
inscape or illustrator that's the one
for you or image screenshot here which
gives you the option of having jpeg or
PNG so that's used for for the likes of
Photoshop or I will do SVG select
xvg you can change the resolution of
your image if you so desire and you can
change the name here and then go okay
choose an export folder here and then
just export snapshot but let's add in
another export so let's go to add export
and we've already got an SVG we may as
well just create a PNG say so I'm going
to select Image Screen shot then I'm
gonna go PNG again I can change the
resolution if I still desire or I can
change the name doesn't matter go ok and
now both of these would be exported and
then I'm going to do export snapshot
then if I go to that folder we can see
that
those files have been export
to the PNG there you go beautiful
and then we have an SVG file
and this is it open in illustrator cool
so that is how to export single
snapshots so let's do export time
sequence of snapshots this is for when
you want to make videos of Your World
Export from let's go from the starter
simulation to well our simulation ends
at 600 million years ago so I'm just
going to do that and one million years
per frame is perfect
so basically what it's going to do is
it's going to spit out 400 still images
that you can chain together in a video
editor later on so we're going to go to
add export in this case image screenshot
is your best friend there's no point
doing this with vector graphics I'll go
PNG again you can change the resolution
if you so desire and for this one here
in the template I'd recommend getting
rid of these bits here and just put in N
so image underscore percentage n where
percentage n is the frame number in the
range of 1 to n basically what that
means is all of your pictures will be
titled image 1 image two image 3 Etc all
right and then we'll go okay again
choose your target directory and then
begin export this can take a while
depending on the size of the resolution
you've chosen
all right that took about three minutes
real time I think something like that so
we'll close that I'm gonna go controller
command M I'm Gonna Save all changes
save project and I'm gonna open up a
video editor so I use Premiere Pro but
it could be iMovie Final Cut DaVinci
Resolve all that sort of thing and with
the video editor open all we need to do
is find all of those Stills and just
drag and drop them
into the video editor and from here I
try and drop them onto the timeline and
there you go one video I don't want to
turn this into a how to use Premiere Pro
video but by default when you drag your
frames in they're gonna be way too long
yeah each frame is five seconds long so
what you can do and hit B on the
keyboard and then you can click and drag
over all of your frames
go to one of them and just drag it
backwards to make it really short maybe
something like that and everything will
correct and then you can play and hey
Presto you got yourself a video and you
can export it from here okay so um
that's all I wanted to talk about today
that is the basic methodology done from
start to finish all the way from drawing
your first super consonant to exporting
your final world as mentioned at the
start of the video next time we're going
to look at topologies which is a super
powerful albeit more advanced way of
using cheap bits that ultimately leads
to kind of nicer results but it's not as
intuitive as doing things in a very
manual way like we've been doing them so
I'm only going to touch on it very
briefly in the next video because it's a
it's a whole kettle of fish right there
anyways I hope you enjoyed thank you so
much for watching you guys the patrons
vangu Vanguard World building pasta you
are all excellent have a good one and
until next time it grows
foreign