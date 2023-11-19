# Neptunes---getting-a-great-First-Layer
Some information on getting a great First Layer happening....

There are a number of factors that all tie in together to form that great FIrst Layer outcome.
Some are more important, or critical, than others.
Some are issues in the system/firmware that you have to overcome. eg Z_Offset reliability.

First, some outline of what is involved and what/why they matter.

In theory, your Nozzle will move 'perfectly' horizontally along an X Axis and Y axis both.
If you had a 'perfectly' horizontal printing surface then things would be great! But print
Beds are rarely 'perfect', and even worse for PEI plate type beds!! They are quite "wavey"
end results pretty well always!  So that means your 'perfectly' traveling nozzle is NOT going
to track that bed very well at all!
There is no way to fix that properly - only if the bed could be made 'perfectly' level. Any 
other idea/solution is just a "fix" to bridge the errors.

So, to correct the error in the best way possible, we have "Bed Meshing" where the Bed is 
probed to make a map of its height errors. Bt you can only probe so many positions - not
"infinite", so that means the Bed Mesh will have errors in between the probe locations.
Then you can use "maths" to fill in those unknowns - but only in a 'fudge' sort of way which
will never get it all perfect.  So the grand finale is that you have a much better way to
keep the nozzle tracking the bed, but stil NOT PERFECT.

The next 'fudge/fix' to help out is to use MORE filament extrusion than it truly needs, so it
"fills" low points better. At the cost of high points possibly being somewhat worse.

How to achieve the "best"
=========================
Level the Bed physically as best as can be done. Use the 4 corner bed screws to adjust it to
be that best level result. In Klipper they provide a "screws_tilt_adjust_routine to assist in
doing this bed leveling easier.  The Elegoo provided "Auxilliary leveling" mode is a similar
thing, and OK< but the Klipper one is better. You need to set that up in your system using
Fluidd to make some printer.cfg changes. Then run that and you willend up with the best possible
level bed.....

Now I like to do a Bed Mesh. Heat the Bed to the typical printing temperature - I use 60degC.
Once that is heated, run the Klipper built in "bed_mesh_calibrate" routine. Save it as DEFAULT.
or some other name you want to use. You will need to LOAD this Bed Mesh filename before printing,
via using the PRINT_START macro in Klipper, or in your Slicer Start G-Code section.


Incomplete outline from here (for now):

Now to do the Z_Offset. Heat the Bed and the Nozzle, so you are mimicking a printing state. Move
the nozzle to the middle of the bed and use the 'normal' controls to lower it onto a "piece of paper"
below it. Your aim is to grip the paper quite firmly under the nozzle.  So it JUST can be moved
still.  Now, in Fluid, check the Z value.  The ultimate aim is to have Z=0 be where the paper is
gripped well. At this stage maybe Z is a positive still, or is a negative...






