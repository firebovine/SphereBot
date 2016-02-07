# SphereBot - firebovine variant

This is my pixelperfect modified SphereBot firmware. A very simple modification.

This firmware is to be used with the ELECTRONICS from this SphereBot.

http://www.thingiverse.com/thing:7656

The actual physical construction of the spherebot is less important, as long as you configure the firmware correctly.
I myself used a 3d printed variant with minor modifications.

For my electronics, I happened to have a cheap prototype board that I wasn't intending on using, so I used that as a shield to my Uno.
It's not the best, but it works and is neat. I threw it all in a 3d printed project box.

1. http://i.imgur.com/gzIyaWb.jpg
1. http://i.imgur.com/o2aYsoZ.jpg
1. http://i.imgur.com/BrCP8KU.jpg

I made this firmware so that each unit(pixel) in an exported SVG will correlate 1:1 with hardware steps.

This firmware will work as long as you size your svg document (in pixels) with how many steps you have.

For example, at 16x microstepping for both axis and 1.9 degree motors (200 steps per rev),
your document size should be:

3200 pixels tall by
800 pixels wide.

Depending on your machine, the width may change. You can determine this emperically, 
or do the math of angles. (angle-of-movement/360) * 3200. IE: 75 degree angle gives you 
666 steps. Please ensure you calibrate the hard mins and maxes for the wiggle-waggle axis
so you don't damage your machine.


See SphereBot.ino for pin configuration settings, min/max for wiggle-waggle (side to side) axis, etc.

Under Utils/ is feeder.py ...it feeds generated g-code to the configured serial device. It could probably work with Windows with only limited modification.
When using my version of feeder.py, do not use the -e switch. It's been a while since I read through/modified the code, so I'm not sure what it does, but I
am pretty sure you do not want it in addition to the modifications I used.

To generate g-code for this firmware, I use inkscape with a plugin that I modified. It can be found here:

https://github.com/firebovine/inkscape-spherebot/
