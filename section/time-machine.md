---
title: Time Machine
updated: 2014-03-25
layout: section
---

# Time Machine

Ok, now that you about [numbers, variables and simple functions][hj], let's
make a time machine out of that and a bit more. You'll learn about *objects*,
functions with *return values* and a few other things along the way.

## Objects

    // And objects:
    {}

    // Objects have attributes:
    ({a: 1, b: 2});    // an object with the attributes `a` and `b`

Ok, what can you do with objects and numbers? Try and see if you can make
some of the following:

* an object describing a person that is `n` years old
* an object that describes several persons (an object can contain objects)

In general, you can put any values into an objects, even functions!

## Numbers inside objects

    // Ok, good. Now we can increment numbers, but that's still a bit
    // boring.
    // Yes, but it's a start. Let's experiment a bit with those object
    // thingies.

    var fred = {age: 10, height: 1.17};

    // That's Fred. Say hello to him. As you can see he's ten years old
    // and is very proud of his height.

    // As it happens, today is his birthday. Today he's going to get
    // older. And as you know you grow by exactly 0.03 meters on your
    // birthday. That's just how it is. So, we're going to write the
    // happyBirthday function to make him smile and proud.

    // But first, a little bit of thinking. Let's try thinking about how
    // Fred changes. Here's what we get when we call happyBirthday:

    {age: 11, height: 1.20}

    fred.age;
    fred.age + 1;

    fred.age = fred.age + 1;
    fred.age;

Try doing the same for is height. (Remember, exactly 0.03 meters.)

... (Try it!)

## `happyBirthday(fred)`

    // Ok, let's write the happyBirthday function:
    function happyBirthday(person) {
        person.age = person.age + 1;
        person.height = person.height + 0.03;
    }

    var fred = {age: 10, height: 1.17};
    happyBirthday(fred);

    fred.age;
    fred.height;

    // Hooray! Happy Birthday and stuff.

Maybe older people don't grow as much? Or younger people grow a lot more?
Try writing the functions for those. Or just change the values in the
`happyBirthday` function. Or even calculate the growth rate given the
height?

It doesn't matter what exactly you try, but it's very important that you
do it. You'll learn something about JavaScript along the way and piece by
piece you're doing cooler things.

## A time machine!

    // Okay, let's make something a little bit different. Let's pretend
    // we have a time machine.
    // (Spoiler: We don't have to pretend, we simply make one.)

    // Instead of changing Fred, we could make a second Fred that is
    // a little bit older and a little bit taller.

    {age: fred.age + 1, height: fred.height + 0.03}

    function birthdayTimeMachine(person) {
        return {age: person.age + 1, height: person.height + 0.03};
    }

    var olderFred = birthdayTimeMachine(fred);

    var paula = {age: 6, height: 0.81};
    var olderPaula = birthdayTimeMachine(paula);

Ok, this might be a little bit difficult to understand. So change some
things to see if you understand what happens.

Other things can happen if you get older, for example, you could get
smarter, less naive or happier. It's up to you, change the time machine
to do something slightly different.

## Loops

    // We can do interesting things with this, like jumping multiple
    // birthdays forward:

    var howManyJumps = 3;
    var olderPaula = paula;
    for (var i = 0; i < howManyJumps; i += 1) {
        olderPaula = birthdayTimeMachine(olderPaula);
        console.log("Paula is now " + olderPaula.age + " years old and " + olderPaula.height + " meters tall.");
    }
    console.log("Time jump finished!");

Aaand again, a good place to stop and think about what just happened.

JavaScript has `strings` (those things in quotes), you put text in them
and even "add" them. try doing that on your own, for example:
`"Hello, " + "World!"`.

## Doing it all in a loop

    // We could also cheat and do it all in one step...
    var olderPaula2 = {age: paula.age + 1 * howManyJumps, height: paula.height + 0.03 * howManyJumps};

    // But as we know time machines have fancy displays and all that
    // stuff, so we need to know what changed.

    // So here's the birthdayJumpMachine:

    function birthdayJumpMachine(person, numberOfJumps) {
        var newPerson = person;
        for (var n = 0; n < numberOfJumps; n += 1) {
            newPerson = birthdayTimeMachine(newPerson);
            console.log("Jumped " + (n + 1) + " times, now " + newPerson.age + " years old.");
        }
        return newPerson;
    }

## Why is this a time machine?

Simply put, because you put a person in and get a future person back out.
And it turns out that is a perfect example for a function, which in most
cases take some data as input and give back some data as output.

## Something to think about

It will really help you if you try this at home. Even if you don't find a
solution, you'll come with questions next time.

* repeat some of the things above. just do them again, maybe try something
    a little bit different.
* extending the time machine:
    - write your own time machine that ages differently or maybe handles
        specific ages different
    - write a reverse time machine
    - write a time machine that can walk backwards an forwards
* representing things
    - try encoding something as an object, for example a person with an age,
        favourite food and whether they like giraffes

And come back with questions!

## Summary

- object: bundling data together
- functions: bundling functionality together (and combining multiple
  functions to ease doing more complex things)
    * why a time machine? younger person in, older person out
- you can combine the two to bundle both together (e.g. a `Person` that
  knows how to celebrate it's own birthday)

## Bonus

More types.

    // JavaScript also knows other types:
    "Strings!";

    // Booleans (you know them already)
    true;
    false;

    2 < 4;
    2 == 4;

    ({a: 3}).a == ({a: 4}).a;

    // arrays
    ["i", "can", "contain", "multiple", "things"];

    ["and", "even", "different", "things:", 42];

    var cats = ["Nyan", "Pusheen", "HTTP Status Cat"];
    cats[0];

And JavaScript can ask you things:

    var ageString = prompt("How old are you?");
    var age = parseInt(ageString);

Ok, one more:

    Math.random();

    Math.random() * 1000;

    Math.round(Math.random() * 1000);

    // Run the following on http://pixl.papill0n.org

    pixl.disconnectAndClear();
    for (var i = 0; i < 50; i++) {
        var posX = -20 + Math.random() * 40;
        var posY = -20 + Math.random() * 40;
        pixl.draw_pixl({x: posX, y: posY}, "green");
    }

## Resources

* the ones from [previous sessions](2014-01-28-hello-javascript.md#phew)
* an [interactive introduction to JavaScript](http://gitbookio.github.io/javascript/)
