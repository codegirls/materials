---
title: Hello, JavaScript
next: time-machine.html
updated: 2014-05-24
layout: section
---

# Hello, JavaScript

Ok, let's try something different today. We're going to invent a time
machine. But we're going to do it in very small steps.

We'll mostly use code for the explanations. Just open the console on
this page (`Ctrl + Shift + I` or `Cmd + Alt + K`). The explanations
themselves will be in *comments*. Comments are lines that start with
`//`. JavaScript ignores those so you can write anything you want in
them.

Try changing **everything**. The values, the names, everything. That's
how you learn how it works. If you changed something and it still works
you'll know you have understood it.

So if you see a heading and haven't tried the examples *and* changed
stuff, go back and do it. :)

And one more thing: We recommend to go through these examples with
someone else. That way you can help each other along, try explaining
things (this always helps!) and hopefully it's a more fun when it gets
a bit difficult.

So, let's go.

## Numbers

    // JavaScript understands numbers:
    3;
    4;
    -1;
    3.141592653589793;

Try and see if JavaScript understands your favourite numbers. Try writing
numbers as you would do on paper and see if JavaScript understands them. If
it doesn't, it will complain. (Most likely with a `SyntaxError`.)

Also, what's the biggest number JavaScript understands? What does it do if
you give it a bigger number than that?


## We can do stuff with numbers

    // So now we have numbers and objects, but how can we do anything
    // with them?

    // Well, we can do some obvious things with numbers:
    1 + 2;
    2 - 1;
    2 * 4;
    2 / 4;

JavaScript is a calculator. Surely, there's something you might want to calculate.
For example, here's how many millieseconds have passed between the start of this
month and now: `new Date().getTime() - new Date("2014-03-01").getTime()`.

And if you want to know how many days that are, just divide it by `1000 * 60 * 60 * 24`.
(A second has 1000 milliseconds, a minute 60 seconds, an hour ...).

## Counting

    // Ok, but numbers are quite boring. We don't even know how to count things.

    // As it turns out, JavaScript has *variables*. We can store values
    // such as numbers and objects in variables.
    var count = 0;

    count + 3;
    count;

    // Mhh. But how do we change the variable?
    count = 1;
    count = 2;
    count = 10;

    // Oops, we might want to change it depending on how it was before.
    count = count + 1;
    count;

Ok, if you haven't typed that yourself, now is the time! Change the names, add
multiple variables together and then maybe calculate how old you are in days.

## Functions.

    // Back to counting. Let's start again.
    count = 0;
    count = count + 1;
    count = count + 1;
    count = count + 1;

    // That's kind of tedious. Let's write a function to do this for us.
    var count = 0;

    function incrementCount() {
        count = count + 1;
    }

    incrementCount();
    count;
    incrementCount();
    incrementCount();
    count;

    count = 0;
    incrementCount();

As always, change all the things! Some suggestions:

* write a `doubleCount` function
* make a function that uses a different variable

## Return values

    // Very nice. But it would be nice if incrementCount told us what
    // the new count were. Just in case we forgot.

    // Well, this "make the function tell us something" is called
    // "returning a value". And which value should incrementCount
    // return? The value of count. Again, just as we did by hand before.
    function incrementCount() {
        count = count + 1;
        return count;
    }

    incrementCount();
    incrementCount();

Try describing what incrementCount does in your own words. Or maybe write
a function that returns your age in days.

## What's a `for`-loop?

- counting up and down this way would be tedious, javascript can help us

<!-- ... -->

    // Whew, that's quite a thing. But that `for`-thing still is a bit
    // mysterious, but that's just because it has a few things hiding it.

    // First, it's called a "for-loop". "loop" means that it repeats
    // something. (There are other loops in JavaScript, the "while-loop"
    // and the "do-while-loop". They're just different ways to write
    // loops. Look them up if you're curious.)

    // The thing inside the curly braces is called the "body" of the
    // for-loop. The statements in there will be executed until the
    // for-loop is finished.

    // for (...) { your_statements_here }

    // But what does "finished" mean? I'm glad you asked. Here's a
    // for-loop that never executes it's body:

    for (; false;) {
        console.log("you will never see this text printed!");
    }

    // So, after the first for-loop comes the "condition": Before
    // executing the body, the for-loop checks if the condition is true. If
    // it is, it executes the body, if not, it is finished.

    // What are the other parts of the for loop? They're the
    // "initialization" and the thing that changes. Sorry, I've got no
    // better name for the third thing.

    // for (initialization; condition; change_thing) { your_statements_here) }

    // You can read for-loops as "Initialize, and then execute the
    // statements in the body as long as the condition is true. Oh, and
    // execute the change thing each time after the statements."

    // Now we can count again:

    for (var count = 0; count < 10; count += 1) {
        console.log(count);
    }

    // With explanations:

    for (var count = 0; // At the start, count is 0.
         count < 10;    // As long as count < 10
         count += 1) {  // increment count.
        console.log(count); // But first print the count.
    } // Check again!

That's all for now.

## Ideas

* try making a loop that counts backwards
* count from 42 to 101 and than backwards from 101 to 42
* put this code in two functions
* write a function that counts *both* ways

    e.g. `fancyCount(10, 13)` counts from 10 *up to* 13 and `fancyCount(23, 19)`
    counts from 23 *down to* 19

## Summary

- variables: places to remember things
- functions: bundling functionality, saving typing, preventing errors
  from copy and paste, being lazy
