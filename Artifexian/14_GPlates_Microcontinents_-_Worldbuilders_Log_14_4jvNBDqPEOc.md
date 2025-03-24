# GPlates: Microcontinents - Worldbuilder’s Log 14

good morning interweb War Builders log
14. today we are going to learn how to
create new plates Midway through the
simulation specifically we are going to
fracture this continent in half I was
going to do it over here but I think I'm
going to reserve this continent for
something in a future video so as always
when it comes to rifting things apart we
are going to find a failed Rift say this
Chap and we're going to copy him turn
him into a rearrift and use that to
split the continents in half no new
information here exact same procedure as
previous videos time lapse mode engaged
and remember that when we create this
Rift we want to make sure we stretch it
across the entire plate so that's all
the way to the mid-ocean ridge here and
all the way to this abduction Zone here
give it a plate ID of one which we're
reserving four riffs and input the
correct times here in my case I'm
looking at this riff starting at 850
million years ago continue into the
distant future call it Rift 850.
and like before I'm gonna set this
failed Riff to end at 8 50 and create
new failed riffs on either side of the
continent again no new information
Now new info here if we want failed
riffs or anything on this new section of
trust it's a little bit trickier because
there's no crate on there so thus far in
the simulation we've been assigning
playhead is based on the nearest Craton
so this failed Rift here I gave it a
player ID of 200 because this crate on
here has a player ID of 200 no such
structure exists here so what you have
to do is hit L on the keyboard to draw
out a fail Rift and let's pick say here
for example and we'll just do a little
Rift
beautiful go to create feature it's
Continental Rift hit next now for the
plate ID give it a plate ID of 201 that
is the plate ID of this continent but
incremented one and then everything else
is normal beginning time whatever
suitable failed Rift with the timestamp
noted as well alright and then hit next
don't worry about this hit next and
we'll put it in the failed riffs feature
collection and we'll go create so next
we need to split the continent the ocean
crossed subduction zone the island arcs
just like we did before on the Craton
side of a continent it's exactly the
same as before so I'll do all that real
quick in time-lapse mode on this
microcontinent side where we don't have
a Craton where we're creating a new
plate it's a little bit different so
I'll talk us through that so great
onside time-lapse mode engaged
foreign
I have this ocean crossed here cut out
this section of the continent cut out
and I split the subduction again as per
previous videos now for the
microcontinent side so to split the
continent hit F on the keyboard click on
the continent to choose that feature
usually we'd go to clone feature here
and then just drag all the vertices
that's going to cause problems because
we're creating new plate IDs so you have
to copy geometry to digitize to this
button up here then hit X on the
keyboard or come over here
and start deleting points so we can
sketch out this section
okay so there's our little
microcontinent I'm going to go to create
feature it is continental crust hit next
plate ID we're going to give it a player
ID of 201 began live at 850 million
years ago correct and its name we'll
call this micro
continent one and we hit next don't
worry about any of this hit next and we
will create a new feature collection for
this so select create new feature
collection and go create and Save
and we're going to scroll down here's
the button new feature collection and
we're going to save this as we find our
folder
we'll save this as
microcontinents
and we'll close and now we can go back
and select the entirety of the old
continent edit feature
controller command e select the valid
time and I'm going to say you need to
disappear at 850 million years ago just
as this splits in two
okay now you'll notice here this is
blank that's no good so if we go over to
our land section over here twiddle down
the drop down arrow and I'm going to go
to add new connections click on that and
I am going to select microcontinence so
our microcontinents will also get
colored the same way as our main
continents and Island arcs speaking of
Island arcs we need to do the same thing
for them so hit F on the keyboard select
the island arc again we want to cut out
the section that is to go with the new
micro consonants so we do not clone we
go to copy geometry to digitize tool and
then we hit X on the keyboard or come
over to here and start deleting points
until we're only left with the
microcontinent section
there we go hit G on the keyboard to
bring back into like polygon mode hit
create feature this is an island arc hit
next
parody 201 correct begins at 850 million
years ago correct and we're going to say
island arc
850. we're going to go next don't worry
about any of this hit next and then
we're going to drop this into Island
arcs hit create so now we should have
one section on this side of the
continent
one section or this side of the rift
another section on the other side of the
rift and then we have our original
feature so I'm going to select that go
up to edit feature controller command e
and I'm going to change that time so it
ends at 850 now is that correct that
seems weird hold on let me just do that
and we'll figure it out it seems like
it's just not going to be there at all
um hold on is that going to work for us
yeah cool same Jazz with the ocean crust
select our ocean crossed
do not clone feature go to copy geometry
to digitize tool and then hit X on the
keyboard delete points
and start deleting away all the points
on the other Continental side so we're
left with just this microcontinent
section
okay hit G let's bring up polygon mode
and then go create feature this is ocean
crossed
hit next play ID is 201 because it's on
the microcontinent side the begin time
is correct it is not an island arc it is
ocean crust 850 hit next don't worry
about any of this hit next and then
we're going to put it in our ocean cross
section and we go create and then
finally we're going to hit F to select
the entire ocean cross like we've done
before and then simply delete it so
hopefully that's all gravy yeah looks
good and finally the remaining Island
arcs now I'm going to demonstrate how
not to do this so hit F on the keyboard
select an island arc it is green so it
is going with plate ID of 200. we want
it to go with this microcontinent so
again you'd think you'd go to edit
feature controller command e and then
just simply select the plate ID and just
change it to our new plate ID 201 and
you'll notice that it has disappeared
well actually it's not disappeared it's
just bounced over here for reasons I
don't understand so whenever it comes to
creating new plate IDs or creating new
plates you got to be really particular
otherwise this jumpy thing will happen
so I'm going to undo that go back to
create feature and I'm just going to put
its plated back to where it was so to
solve this we're going to do the copy
geometry to digitize tool method before
we do that I want to check it's dating
to keep everything legit so I'm going to
go back to edit feature controller
command e and this boil was created at
950 million years ago that's in
important I need to remember that so
with it still selected copy geometry to
digitize tool go to create feature this
is an island arc Theta df201 time of
appearance here is not 850 million years
ago it is 950 million years ago when we
first created it continues into the
distant future cool and this is
island arc
950. go next don't worry about it next
and we'll drop this into Island arcs and
we'll go create so now we should have
two copies here one that I created 30
minutes ago when I first boot up the
system and another that I created 17
seconds ago so I'm going to go to the 30
minutes ago one and I'm just going to
delete that and the exact same procedure
applies to this island direct so F on
the keyboard select the island arc copy
geometry to digitize tool create feature
it's an island arc cool
plate ID of 201 cool to match our
microcontinence I'm pretty sure this
island dark
formed at the same time as this one so I
think 950 is correct so everything's
gravey there next doesn't matter about
any of this next and I'm going to drop
this into Island arcs and hit create
again there should be two copies here so
I'm going to get rid of the old copy
and I'm going to delete that and now we
want to label the seduction zones
correctly to match with the
microcontinent again we can't just
select the subduction zone and go edit
feature and change the paid ID
because it will bounce around the globe
so once again copy geometry to digitize
tools so F on the keyboard select the
feature this subduction zone formed at a
thousand million years ago cool so I'm
gonna go copy geometry to digitize tool
then create a new feature this is a
subduction zone cool 30 of 201 great
beginning time thousand million years
ago and its name is sub 1000.
next next and then into subduction zones
we go and we hit create gonna select the
old subduction zone the one created 33
minutes ago and I'm going to delete that
exact same procedure applies to this
chap here
cool now as you can see if I scrub
through the simulation everything's
broken that's because gpates doesn't
know what player ID 201 is yet so we
need to code some stuff to tell it
what's going on so hit Ctrl or command M
to bring up the manage feature
collections dialog and just make sure
that your rotation file here is saved
so I'm going to save it and then I'm
going to open up that rotation file in
text edit So Below the relevant plate ID
in this case below anything that's
labeled as 200 I'm going to insert two
new lines of code with the new player ID
so 201 that's our new play ready space
0.0
space 90.0
space 0.0 space 0.0
space three zeros
space exclamation mark and this line of
code is going to be our micro continent
end of the simulation essentially it's
the exact same as what we've done before
here
and here but with the new plate ID of
201 below that we're going to write
another line of code 201 again for the
player ID
space now for our time we want to put in
the moment that this occurs so 850 in
this case 850.0
space and then 90.0 space 0.0 space 0.0
space one two three zeros
exclamation mark and this is going to be
our start
moving
independently again akin to what was
going on
here right so let's get rid of those
line breaks save the file go back into G
plates hit controller command M to bring
up the manage feature Collections and
for the rotation file reload it okay
nothing should happen yet cool hit
control or command D alternatively go up
to reconstruction and select specify
anchored plate ID controller command D
in this dialog box insert the plate ID
from which your microcontinent is
splitting off of so our microcontinent
is spitting off of everything that has a
player ID of 200 so I'm going to put in
200 here and I'm going to hit ok now
again everything looks like it's broken
and terrible but it's okay don't panic
hit control or command P alternatively
go up to reconstruction and down to view
total reconstruction polls assuming
you've done everything correctly the
anchored plate ID here should be the one
that our microcontinent is splitting off
of that is really important if it's not
this won't work assuming that is correct
go to equivalent rotations relative to
Anchor plate and in the plate ID section
here we'll see our new microcontinent or
our new place 201 and we see the
coordinates at this time those are going
to be important so I'm just going to
push them over here and I'm going to
open up my rotation file again so now I
am going to create a new line underneath
the two lines we just created plate ID
again is 201 time is exactly the same as
the above line
but the coordinates here are going to be
these coordinates so 70.1652
space
26.3856 that's that chap space negative
38
.4047 space and now instead of putting
three zeros we're going to put in the
plate ID that the microcontinent is
spitting off of so in our case that's
200 then in Google space
exclamation mark and this line of code
is going to be the end
following
C line of code then copy that line and
paste the new line below change the time
this column here for the starter
simulation so a thousand point zero in
this instance
don't change the coordinates that's fine
don't change the conjugate plate ID here
that's also fine and maybe change the
comment to
microcontinent
at the start of the simulation or rather
actually microcontinent one at the
starter simulation and microcontinent
one at the end of the simulation so
basically what we're doing is we're
doing the decoupling of plates we did in
the last video but kind of in a sort of
reverse order okay let's lose all the
line breaks again I only put those in
just to visually clear things up for me
hit save back into G plates controller
command M and the rotation file I'm
going to reload the rotation file
nothing happens that's totally fine I'm
gonna hit controller command D to bring
up the specified anchor plate ID dialog
box and I'm going to change this back to
where it was zero zero zero
and hit OK now hopefully everything
should be fine I'm just going to close
the riffs thing here for a second just
to make it a cleaner everything should
be fine everything should be moving okay
yeah perfect no weirdness happening but
we've made it so that g plates knows
that this chunk and this chunk including
all the associated Island arcs Etc are
two distinct things so now all that's
left to do is Skip forward another 50
million years to 800 million years ago
and move these around no new information
exactly the same as previous videos time
lapse mode engaged
foreign
for the next video
not Mega realistic what I just did it
really should have just kept going
straight
foreign
okay
I'm fairly happy with this uh this isn't
great but just demonstration purposes so
we're fine so next as always I'm just
going to lock in the drift correction so
it doesn't go do something nuts like
that
oh this fella will need to create a
drift correction for him so 201 player
df201 then 1.0 to match up with all the
other 1.0s then I'm going to paste in
these coordinates
space paste space zero zero zero
exclamation mark and this is drift
correction
and then finally with plated D of 300
copy coordinates
paste them in
get rid of line breaks oh and I suppose
it's worth mentioning sometimes there
can be a shindiki line break at the end
that you don't realize that can cause
geopolitical mods just make sure that's
also gone and then hit save back into G
plates controller command M and I'm
going to reload the rotation file and
once again all of the flow lines just go
bananas
and just like before we need to repair
the flow lines and once repaired use
them to create more ocean crust most of
this is not new at all but just because
we're working on the microcontinent down
here I'll talk through the flow lines
between our old continent and this new
microcontinent so I'm going to go back
to when they first spit apart that's 850
million years ago in this instance I am
going to select this Rift copy geometry
to digitize tool and then hit M on the
keyboard
or go over to here copy new multi-point
geometry it has to be that remember
really important flow lines won't spawn
unless you've hit copy multi-point
geometry or M on the keyboard and I'm
going to go to create feature this is a
flow line next left plate ID well that
would be this plated e here which was
200 in this case and the right plate ID
that would be 201 our new place they
begin at 850 million years ago they'll
continue with the distant future and
their names are going to be flow lines
850. next now we want to go to add so
from
850 when they are first created to 0.0
in steps of 10 million years perfect hit
insert just do a quick double check 850
all the way to zero perfect hit okay
next I will put these into flow lines
and hit create
now these should be nice here
oh snap okay not a deal breaker here at
all but I really should have put a point
along the coast so we can get another
flow line here
it it's fine it's not a problem okay end
of my time stamp 800 million years gonna
hit F on the keyboard I'm going to
select those flow lines copy geometry to
digitize tool then hit G on the keyboard
or come over here to digitize new
polygon geometry and now I am going to
create ocean crust for this new Rift
plate ID it is attached to the micro
consonant Soul player df201
beginning time is at the end of this
time step so that's 800 million years
ago
and this is ocean crust
at 800 million years hit next next and
then we put this into ocean crusts and
hit create
exact same procedure on the other side
okay cool
okay now let's sort out these flow lines
so I am going to delete those and I'm
going to go back to where these
continents rifted and rifted apart so
that would be
850 oh not 850 sorry that would be 900.
yes there we go now I'm going to scrub
through and I'm going to need to split
this Rift so we get one set of floor
lines that go between pink and green and
another set of floor lines that go
between pink and microcontinent so where
is that split occurring well it's there
because that's the rift that we
re-engaged
yeah perfect so back to the moment of
rifting 900 F on the keyboard select the
rift and then hit t on the keyboard and
I'm gonna split that line
here so we should end up with half a
rift
on this side and half Rift on
this side perfect select whichever half
you want copy geometry to digitize tool
make it points by hitting M on the
keyboard go to create feature this these
are flow lines left plate ID we'll call
that 300 and the other plate ID the
right play leave will call that 201 so
we're stretching it between here and
here perfect these will begin at the
moment of this rifting so that's 900
million years
and these are going to be flow lines
900s
cool next now we want to add some floor
lines so from 900 million years ago to
zero in steps 10 insert do a quick check
900 to 0 perfect hit okay next and we'll
put these into flow lines and hit create
and then hopefully
they will split off really nicely for us
for real okay cool now I'm gonna put in
some awesome crust same as before time
lapse mode engaged
plate ID of 201 because it's attached to
the 201 plate
ID of 300 because it's attached to the
300 plate
okay and then same deal for the other
side of the rift except this time
linking pink to Green 300 to 200.
foreign
cool and like before we have this triple
Junction formed here so we're going to
select each of these adjacent segments
insert a point and then drag the point
into the center to form like a triangle
shape
all right now same deal as before are
going to connect up 100 300 and 100 to
200 so we're going to go back to our
initial rifting event in fact actually
let me just kill the flow lines as they
are
we can delete you perfect
so back to our initial rifting event the
very very start F on the keyboard select
the rift or I've turned riffs off hold
on Rift there we go and same thing again
copy geometry to digitize tool make that
point make it flow lines Etc you know
the deal
foreign
just like the previous video I'm going
to make a point so select digitize new
multi-point geometry or press M and I'm
going to insert three points here one to
join up blue and pink with floor lines
another to join up blue and green with
flow lines and a final one to join up
green and pink
okay and now I'm going to extend these
bits of ocean cross to up to meet these
new floor lines so F on the keyboard
select the ocean crust I'm gonna hit I
on the keyboard to insert point I'm
going to insert two points one here and
one here hit V on the keyboard and then
drag those points into position
same thing all around
okay and just like before when we have
this triangle shaped hole in the ocean
We'll add some points and extend them
out to the center to kind of complete
the ridges
cool
okay so that is that over the past few
videos we've basically looked at all
possible divergent boundaries I can't
think of any other way of how my one
might want to split apart continents we
covered how to split continents apart
into independently moving cratons and
coal moving cratons and then we learned
how to split those apart and in this
video we learned how to split apart
microcontinents from other continents
those handful of techniques will do the
entire simulation for you when it comes
to the divergent boundaries in the next
video we're going to look at convergent
boundaries how to work it when
continents Collide again so stay tuned
thanks for watching folks thanks to
World building pasta whose methodology
this is thanks to venger Van Gogh
resident artist and until next time
Edgar house
foreign