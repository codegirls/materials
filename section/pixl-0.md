---
title: Let's pixl!
next: pixl-1.html
updated: 2013-12-17
layout: section
---

# Let's pixl!

today, we're going to draw little pixels together.

[let's start!](http://pixl.papill0n.org)

now you can place pixels on the screen by clicking somewhere. you can
move around using the arrow keys and zoom in and out using the scroll
wheel.

these are just the basics, the fun begins when you write some javascript
to create some bigger shapes, rather than clicking them together
yourself.

here's an example:

    function straight_line(from, to) {
        if (from.x == to.x) {
            for (var y = from.y; y < to.y; y++) {
                pixl.draw_pixl({x: from.x, y: y});
            }
        } else if (from.y == to.y) {
            for (var x = from.x; x < to.x; x++) {
                pixl.draw_pixl({x: x, y: from.y});
            }
        }
    }

in firefox, you can open the console using `Ctrl + Shift + K` or open a
"scratchpad" by pressing `Shift + F4`. the console is ok for shorter
commands, but for defining functions and little programs the scratchpad
is better suited.

a small warning: don't try to draw your masterpiece in here without
saving the code for it. i wrote the server in a day and it breaks easily
and doesn't save the pixels across restart.

## short reference

* `pixl.draw_pixl(position, color)`
    - example position: `{x: 0, y: 0}`
* `pixl.color`: the default color. you can specify any css color value
  you want, though starting with `red`, `green` or `yellow` might be
  easiest. if you want a special color, try the [css color picker][] and
  set the color to the value it gives you.
    - example: `pixl.color = "red";`
* `pixl.online`: set to `false` if you want to try things out alone.
  (note that you will loose your state if you reload.)

[css color picker]: http://csscolorpicker.com/

## some ideas

* write a function that draws ...
    - a rectangle
    - a triangle
    - a circle
    - a christmas tree
    - a moon
    - a reindeer
    - a house
    - a checkerboard
* try creating an animation together
* create a little light-show
