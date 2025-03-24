# Apparent Size & Brightness - Worldbuilder’s Log 7

good morning interweb world builders log
seven today we are going to do more work
on the apparent size and brightness of
our planetary system but first as always
follow up
so main point of follow-up today is i
want to address the lack of
interoperability between the various
sheets in this spreadsheet i've been
getting a lot of feedback about this so
just want to make clear what my
motivations are so you'll notice that i
ask you to say stellar mass in this
sheet and then i ask you to input again
in the planetary system sheet manually
and then again manually in the planet
tab and then again manually in the moon
tab this is a feature not a bug this is
by design i'm well aware that i could
link everything up simply by clicking on
a cell that i want to link hitting
equals going to where the parameter was
first input and then hit return and now
that's auto updating but i think that's
a bit of a quality of life downgrade and
here's why in the last video you'll note
that i imported a semi-major axis for
the moon's orbit which gave me an
orbital period for the moon then i went
over to the calendar tab i manually
input that orbital period here and had a
look at what it gave me in terms of
calendars i didn't like it so i adjusted
it here i think i adjusted it like five
or six times until i found something
that was vaguely something i liked that
only is so easy if the sheets are
treated like a sandbox were they all
interconnected i'd have to compute my
semi-major axis from moon go to the
calendar tab the orbital period will be
automatically updated check to see if i
like the results if i don't i have to go
back to the moon tab adjust the
semi-major axis which would auto update
this orbital period check don't like it
back to the moon edit auto update check
don't like it back to the moon etc etc
etc i just found that it got really
cumbersome really fast there was a stage
in a beta version of the spreadsheet
where everything was interconnected but
it was such a pain to use that said just
because i think it's a pain doesn't mean
that you will think it's a pain and this
is the beauty of the spreadsheet being a
spreadsheet and not say a web app
because it's user editable so if you
really don't like having to re-import
parameters manually you can simply
wire them all up again click on the cell
that you want to connect hit equals go
to where you want to connect it to say
the original input of the mass here and
then hit return and then that there is
auto updating
again though i consider this a downgrade
a quality of life downgrade so i'm going
to keep it the way it is in the official
releases final thing is that the
reference dock has been updated
with information about the homeworld
and
the
moon
beautiful artwork here by vangovan gog
links in the description go check them
out
and if you want to get your hands on the
reference doc head on over to patreon
again links in description or check out
the end screen at the end of the video
all right and that is
follow-up
done
let's get building so today we're going
to figure out the apparent size and
brightness of our star and the planets
relative to one another in our planetary
system but first let's do some
explaining time as always input your
star's mass here spreadsheet then gives
you the star's luminosity and radius but
also importantly gives you the stars
absolute magnitude when we talk about
measuring the brightness of objects in
space we talk about magnitude so imagine
this is our planet and we have these two
stars
out here star a and star b and we want
to measure how bright these are there's
two kind of related ways in which you
can approach
measuring the brightness of
objects in space you can check for the
apparent brightness
or sorry i should say apparent magnitude
and or you can check for the absolute
magnitude
so all the apparent magnitude asks is
from the perspective of the observer
which of the objects are brighter that's
it so in this case star a
is bright
whereas star b
is dim
now star a may well be brighter and star
b may well be dimmer or star a could be
fainter than star b but just happens to
be closer to the observer i.e it appears
it's apparently brighter but it may not
intrinsically be so that's where
absolute magnitude comes in and the way
this works is you take the objects
you're viewing and you mathematically
move them to the same location so you
take star b for example here and you'd
move him
over to star a irl for stars you move
them all to a distance of 10 parsecs
from the observer and for planets you
move them all to a distance of 1au but
in any case once they're all at the same
distance then you compare the
brightnesses and now we would find that
star a is in fact dimmer than star b and
star b is brighter than star a so
apparent magnitude how bright does the
object appear absolute magnitude how
bright actually is the object to
summarize it very roughly and the scale
we used to measure apparent brightness
goes a little bit like this
the more negative the number is the
brighter the object appears to be
the more positive the number is the
dimmer the object appears to be which
makes no sense but i think it's there
due to like historical blows if an
object has a magnitude of about plus
five to plus seven somewhere in that
range that's about at the limit of human
vision anything greater than plus seven
is invisible to naked human eye you'd
need a telescope to see it anything less
than plus 5i brighter than plus 5 is
able to be seen by the naked human eye
and finally each integer step on the
scale is
2.51 times as bright as the previous
value so a plus 3 magnitude star for
example is 2.512 times as bright as a
plus 4 magnitude star and a plus 3
magnitude star will be 2.512 times as
dim as a plus 2 magnitude star
so this is a log scale and that's
magnitude explained negative bright
positive dim apparent magnitude how
bright things appear to be absolute
magnitude how bright they actually are
so in the case of our sun its absolute
magnitude is above 4.81 next up the
spreadsheet works out the apparent size
and brightness of the star as viewed
from each of the worlds in your
planetary system so you input your
planets here you give them their correct
semi-major axes and the spreadsheet
tells you the apparent magnitude of the
star when viewed from a given world in
your system again absolute magnitude how
bright things actually are apparent
magnitude how bright things appear to be
the more negative the number the
brighter it is now that's cool and all
good for a stat sheet but it kind of
doesn't really make any sense what does
negative 28 actually mean like what does
it feel like and that's where the
brightness tab comes in
this checks to see the brightness of the
star
as viewed from the surface of each of
your worlds
relative to how bright the sun appears
to be on earth so on earth the sun
appears to be one times as bright as the
sun on mercury the sun appears to be
6.67 times as bright as it does on earth
and then all the way out of pluto the
sun is really dim it's like a distant
star and the final thing this section of
spreadsheet does is check the apparent
size of star again when viewed from
earth our sun is equal to one here so on
mercury the apparent size of the sun is
2.5 times that of the apparent size on
earth and the further out you go
the more the apparent size drops all
right pretty straightforward i think
next up we have the planet's apparent
brightness and size how bright do each
of the planets appear when viewed from
the surface of your home world first
thing you gotta do is put in your albedo
now note in the planetary tab the albedo
we used was bond albedo and in this tab
the albedo we're using is geometric
albedo the two are related yet kind of
unrelated it's really complicated bond
albedo is used for measurements of
temperature geometric albedo is used
when you're talking about visibility so
in the case of earth for example it has
a bond albedo of 0.306
and a geometric albedo of 0.434
close but not the same you think you'll
be able to convert really neatly from
bond to geometric albedo you can't there
is a way of converting it it involves
calculus and just it will involve me
asking you to give just
dozens of esoteric inputs in order to
just even remotely get near where you
need to be so for all intents and
purposes the bond albedo and the
geometric albedo are basically just
unrelated for our purposes so simply
click the little eye icon here and it
gives you the geometric albedos of each
of the planets in our system figure out
which of the irl planets is most like
the fictional planet you're working with
and give it a similar geometric albedo
that's kind of the only way of working
this it's annoying but we just need to
pick then you need to input the radius
of your planets and then tell the
spreadsheet whether or not the planets
have an atmosphere a tick means yes it
has an atmosphere blank means no it does
not have an atmosphere and we're talking
kind of like fairly substantial
atmospheres like the moon has an
atmosphere but it's really tenuous and
it wouldn't count in this case for
example venus mars jupiter saturn uranus
and neptune they would all count as
having atmospheres next up you want to
put the input the distance in a u
between the planet and your home world
and the value that you input here has to
be somewhere between the minimum and
maximum value that the spreadsheet
computes pro tip here if you want to
input the exact minimum or the exact
maximum value
don't import it manually hit equals and
then select the value you want otherwise
there'll be some cases where it'll just
it'll go wrong so you can manually input
any value in between these two values
but if you want these exact values
reference those cells once the
spreadsheet knows how far away the
planet you're observing is it'll do a
general check here to see if the planet
is a naked eye planet is there any point
in the orbit of the two bodies
where the observed object is visible if
the answer is yes that planet is a naked
eye planet and will be known since
antiquity on your world in our system
mercury venus mars jupiter and saturn
are naked eye planets you do not require
telescope to view them if it says maybe
your planet is at that human visibility
cusp it's somewhere in this range it
might be visible given the correct
conditions but it also may not be and if
the spreadsheet says no there is
absolutely no way you're able to see
these objects without a telescope
and the final portion here is the
current tab
and this asks well what's the current
visibility this is the general
visibility but what's happening right at
this very instance it gives you an
apparent magnitude of the object so at a
distance of
1.37 au from earth
mercury
has an apparent magnitude of negative
1.39
which is very bright but it's too close
to the star to be visible therefore its
brightness is not applicable now that
might seem a little bit crazy and that's
where you scan up here to the chart
the little red i have to zoom in here on
oh boy what's going on here we go oh oh
there we go so we have our homeworld
here in red and we have our star in
yellow
and if you notice mercury here is this
blue dot
it is right behind the sun there's a
little bit of a poking out but it's too
close to be seen
hence you can't see it it has no
brightness venus at this instant though
is negative 4.10 so it is brighter than
mercury it's visible in twilight
and it's visible with the naked eye and
it's very bright
and again you can see that on the chart
we have venus and zoom in again oh dear
there we go we have our homeworld we
have our star and there is venus
and so on and so forth pluto for example
has magnitude of plus 15 that's
invisible to the human eye it is
invisible at night but you're going to
need a telescope to view it and you can
change all the values here and see what
the current setup is so let's just
really quickly do it i want to choose
some random values
and there we go our little map has
updated now mercury venus and mars are
visible in twilight only
they're all pretty bright and all the
rest are visible at night some using a
telescope some visible without a
telescope and then the final thing is
the apparent size and brightness of the
moon we've covered this briefly in the
previous video but just to reiterate
input the semi-major axis of your moon's
orbit the radius of your moon it's
geometric albedo so again look at the
list of planets choose an albedo that's
somewhat similar to what you're shooting
for input the phase your moon is in zero
degrees is a full moon 90 degrees half
moon 180 degrees is a new moon then
spreadsheet tells you it's absolute
magnitude how bright the thing actually
is and the apparent magnitude of your
moon how bright it appears to be when
viewed from the surface of your home
world it gives you then the relative
brightness how bright it is relative to
our moon
during full moon the apparent size how
big it is relative to our moon and then
the spreadsheet compares the apparent
size of the moon and the apparent size
of the star and checks to see whether or
not those two would eclipse each other
or what sort of eclipses would occur if
the parent size of moon is equal to or
greater than the apparent size of the
star you're going to get total eclipses
on your world if it's not you're only
going to get angular eclipses all right
and that is i think the sheet explained
let's get building so i'm going to drop
back in these numbers from my system
so notice again the absolute magnitude
of the sun is 4.81
the absolute magnitude of my star
because it's bigger more luminous is
more negative it's brighter its absolute
magnitude is decreased makes sense next
i want to drop in the name of my planets
and their semi-major axes so give me two
seconds
alright so those are my worlds my rocky
planet my homeworld my gas giant my ice
giant and their relevant semi-major axes
the relative brightness of my star
on my homeworld is 0.78 times as much as
the sun so daylight is a little bit
dimmer and the apparent size because
we're so far away is 0.66 times that of
the apparent size of the sun so the sun
will appear smaller and then everything
else looks fine there so i'm i'm happy
with that let us proceed
so this has been all auto populated here
for me
let's do some clearing up
right so we need some geometric albedos
here so my rocky planet i'm envisioning
it's something like mercury so mercury
has a geometric albedo of 0.142
let's just vary that ever so slightly
there we go our gas giant
again i'm imagining it's much like
jupiter jupiter has or jupiter and
saturn are about 0.49 to 0.54 and i
think in my reference doc the image of
yeah this is quite a white object i'm
just going to
use as an excuse to give it a higher
visual albedo so maybe
yeah let's do 0.5 let's do
0.55 maybe and then my ice giant again
what does my reference dark are park
show it's kind of a blue color much like
neptune
so neptune is 0.42 let's say it's 0.41
okay so for radii
again i'm visiting my rocky inner world
to be
somewhat like mercury so let's make it
let's make a smaller version of mercury
let's make it point
point three earth radii in size our gas
giant i've always envisaged him being a
bit of a bruiser so i'm going to give
him
a radius of 12 earth radii now that is
the maximum
size a gas giant can be gas giants tend
to be between 8 and 12 earth radii in
size
in in radius the only time you can go
bigger is if you have a hot jupiter
so you have a gas giant that forms in
the outer regions of the solar system it
migrates inward
really close into the star and the
temperature causes its atmosphere to
like puff out and then you can get like
what's known as puffy planets or super
puffy plants that can have radii greater
than 12 earth radii but a standard gas
giant like jupiter like saturn out in
the outer regions of the system 12 is
the absolute maximum
and then for our ice giant i'd say
somewhere between maybe 2 earth radii
and 8 would be kind of a sensible-ish
range here i'm going to go with
maybe
2.1 actually let's put in some of those
decimals to make it look all fancy
and yeah let's fancy up these decimals a
little bit
there we go so our inner world slightly
smaller mercury our gas giant chunky
bigger than jupiter and our ice giant i
think is smaller than our ice giants
hold on a second
neptune is about 3.8
ish earth radii in size
and uranus is about 3.9 for earth
radiant size
so we kind of have a world here that's
like on the cosplay is it a super earth
is it an ice giant it's kind of a
transitional sort of body i think that's
kind of cool our little mercury analog
will definitely not have an atmosphere
our gas giant definitely will have an
atmosphere our ice giant also definitely
will have an atmosphere all right let's
put let's import some
distances here so just for the sake of
it
actually i'm gonna do a formula here
just for the crack
so random number
top of the range minus bottom of the
range
plus the bottom of the range
will just give me a random number in
between these two ranges
all right cool so are all of my planets
naked eye plants answer yes
so we have no hidden objects the
inhabitants of our homeworld will know
of all of the objects in our system
which makes sense we said we went for
like a really tight system so we have no
super distance objects so everything is
viewable all right in the current
situation let's have a look at our
system up here we have our homeworld our
star there's our rocky planet
there's our gas giant there's our ice
giant currently our rocky planet has a
magnitude of plus seven it is too close
to start to view that would make sense
air cooled brightness is not applicable
our gas giant has an apparent magnitude
of negative 1.91 it's viewable at night
with the naked eye and it's very bright
again that makes sense and our outermost
ice giant is .533
viewable at night possibly visible naked
eye because again it's in that zone
where it's it's at the limit of human
vision so that's kind of cool i think
our outermost planet will probably dip
in and out of vision
which is pretty dope let me re-roll some
of those numbers just to get a feel for
what's going on
sure yeah i'm liking what i'm seeing
there our outermost planet is just on
the cusp that's kind of cool all right
and then final final thing let's do some
moon stuff so our semi-major axes we
input this last time but i reset
everything for the sake of demonstration
is 477 900 its radius was what was that
1.06
moon radii its geometric albedo is 1.24
actually was that 1.24 hold on
geometric albedo 1.24 perfect and we'll
check it at full moon now notice in the
previous video its brightness was coming
out at 1.38 times as bright as our moon
there was a bug in the spreadsheet and
we forgot to square the inverse square
law so what's actually happening with
the moon is that its brightness at full
moon is 0.48 times as bright as our moon
so darker nights which makes more
intuitive sense and is also really fun
might be a good excuse to give some
nocturnal animals just hella big
eyeballs apparent size is 0.85 so total
eclipses are possible nothing's changed
there right that is what's going on
in our planetary system what is visible
what isn't turns out everything's
visible and how bright things are
relative to one another and that is
basically
all of the space stuff done we're
quickly going to get into mapping and
climate zones and things like that next
video though i'd like to do a sort of
polishing up episode just go back over
some of the old spreadsheets and just
tighten things up there's a couple of
things i want to tweak and change but
because everything's been explained
it'll be a really quick sort of speed
run episode and that is basically it
thank you so much for watching folks i
really hope you enjoyed
final massive shout out to vanga vangog
resident artist extraordinaire go check
them out too links to everything you
need to know in the description
until next time
edgar out
you