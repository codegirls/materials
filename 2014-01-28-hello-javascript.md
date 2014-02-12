# hello, JavaScript!

today we're going to write some JavaScript. we will continue using
[pixl](http://pixl.papill0n.org), but instead of clicking around to
draw something, we will draw it using JavaScript.

## what's JavaScript

a programming language that comes with every modern browser and
which almost every website uses in some way.

for the stuff we're going to do today, we only need a small part
of JavaScript. i'll explain what we need to know, but if you want
to know more or continue on your own, then you might want to
read one of the following:

* [Codecademy: JavaScript Track](http://www.codecademy.com/tracks/javascript)
* [Eloquent JavaScript](http://eloquentjavascript.net/index.html)
* or just continue playing and search for something when you don't
    know something. (that's how most programmers start learning.)

## javascript 101

the following examples can all be run from the browser console,
which you can open with `Ctrl + Shift + I` or `Cmd + Alt + K`.
to run them, open the console and type the code you see below
in the console and type `Enter` to run it. i recommend that you
really type it out instead of copying it so you remember what
you did better and have the chance to make some mistakes.

mistakes: you're learning, so you'll be doing lots of them. if there
isn't anything that doesn't trip you up, then you probably already
know quite a lot and could help the others or do more experiments.

let's get started.

### by running some code

All the `pixl`s that are drawn are actually shared to all other users
as you draw them. For experimenting around, it is better to disconnect
and draw on your own and then come back online and show the others
what you did.

Go to [pixl](http://pixl.papill0n.org) in your browser, open the
console and type the following to disconnect:

    pixl.disconnectAndClear();

Now you can play around as much as you want and noone else's drawings
will get overdrawn.

### ... with an example

let's draw a horizontal line. in the console, type the following (use
`shift-enter` to go to a new line without executing the code you typed
so far. only type enter when you have typed all of it.)

```
function horizontal_line(start, length) {
  var y = start.y;
  for (var x = start.x; x < start.x + length; x += 1) {
    pixl.draw_pixl({x: x, y: y});
  }
}

horizontal_line({x: 0, y: 0} , 10);
```

as you may have guessed, the code above draws a line. it first defined
a *function* to do that and then *called* that function with two
*parameter values*. when a function is being called, javascript assigns the
given parameter values to the *parameters* and then "jumps" inside the
function and executes the code in it.

functions are wonderful. you just define them once and then can refer
back to them and call them with different parameters. if you do that
with the function above it will draw lots of lines all over your screen.

try calling the function with different parameters.

**(do it :)**

calling the function works a bit like the following: first you assign the
parameter values to the parameters to give them names and then you execute
the *body* of the function:

```
// assign the parameters
var start = {x: 0, y: 0};
var length = 10;

// execute the body of the function
var y = start.y;
for (var x = start.x; x < start.x + length; x += 1) {
  pixl.draw_pixl({x: x, y: y});
}
```

now, what about that `for(var x = ...; x < ...; x += ...) { ... }` thing?
that's a *for-loop*. it executes it's body (what's inside the curly braces)
until a *condition* is `true`.

what we want to do is draw a horizontal line. if you move your mouse around
you'll notice that the numbers in the bottom right of the pixl window change.
those are the coordinates (x and y) of the mouse. so if you want to draw a pixl
then you call `pixl.draw_pixl` and pass those coordinates to it:

```
pixl.draw_pixl({x: 0, y: 0});
```

to draw a horizontal line the `x` coordinate has to grow. we could do that
by repeating the line above with different values for x, but that's no better
than clicking. we want the computer to do it. so instead of repeating that
line we make the computer repeat it by writing a for loop.

the loop in `horizontal_line` above basically does the following: set `x` to
the `start` position we passed to the `horizontal_line` as a parameter and then
increment `x` until we drew enough pixls.

to see what's going on, try executing the following:

```
for (var x = 0; x < 5; x += 1) {
  console.log(x);
}
```

if you try to repeat what the computer did, then it would probably look like
this:

```
console.log(0);
console.log(1);
console.log(2);
console.log(3);
console.log(4);
```

try doing the same "repeat what the computer did" for the `horizontal_line`
function.

if you understand what it does, what about one of the following?

* write a function called `vertical_line`. (think about what would have to
    change compared to `horizontal_line`.)
* what about a function that draws a dotted line?
* or a function that draws a rectangle?

        // rectangle(start, width, height)
        rectangle({x: 0, y: 0}, 10, 10);
* `circle(center, radius)` and `ellipse(center, radius)` are also fun.
    (ellipse would be called like this: `ellipse({x: 0, y: 0}, {x: 10, y: 5}))`)

and of course, try drawing something bigger with the functions we wrote.

### phew.

if you didn't know anything about javascript, variables, functions and all those
things before this might be quite a bit overwhelming. don't worry, it'll go away
until you start discovering the next confusing thing. :)

if you want to know more, one of the following may help:

* [Codecademy: JavaScript Track](http://www.codecademy.com/tracks/javascript)
* [Eloquent JavaScript](http://eloquentjavascript.net/index.html)
* or just continue playing and search for something when you don't
    know something. (that's how most programmers start learning.)

and of course you can always ask anyone here what anything means or how it works.
just make sure to quickly google it first and ask if that's confusing too.

(there's also the [forum](http://moot.it/code-girls-leipzig) where you can post
your questions.)

## there's still more, of course.

not only there's [pixl](http://pixl.papill0n.org), now there's also
[trixl](http://pixl.papill0n.org/3)!

and if you're particularly adventurous, you can also [make music](musical-adventures.md).
