# SphereBot - firebovine variant

This is my pixelperfect modified firmware. A very simple modification.

I made this firmware so that each unit(pixel) in an exported SVG will correlate 1:1 with hardware steps.

This firmware will work as long as you size your svg document (in pixels)
with how many steps you have.

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

To generate g-code for this firmware, I use inkscape with a plugin that I modified. It can be found here:

https://github.com/firebovine/inkscape-spherebot/
