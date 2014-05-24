---
title: Coding Adventures
updated: 2014-05-20
layout: section
---

# Coding Adventures

That is, either coding *adventures* or having adventures while writing
code.

Either way, I'm not sure yet what it will be.

## What happened so far ...

In the last few weeks we've played around with variables, loops, functions
and time machines. But now it's time for some adventures.

We'll write a small adventure game in the end. But at first we're just
going to be polite and greet everyone who tells us our name.

## Making the computer say things

We don't have to write all functions ourselves, actually the browser
provides *a lot of* functions already.

Today will be mainly about three that aren't (really) used much on the web,
but which are still very useful for our adventures.

* `alert(message);`: displays a small window that says whatever you passed
    to it.

    **Try it!** (Just to stress that again: Everytime you see something that
    looks even a tiny bit like code you should try it out. It might do
    funny things. And it will definitely help you learn. So, try that
    `alert` thing.)
* `confirm(message)`: Asks the user to confirm whatever message you passed
    to it. It then returns whether the user said yes or no.

        var userLikesCats = confirm("Do you like cats?");
    
        if (userLikesCats) {
            console.log("They like cats!");
        } else {
            console.log("Mhh... I don't understand this one.");
        }
* `prompt(message)`: Asks the user to input something in response to the
    message you gave.

        var name = prompt("What's your name?");
        alert("Hello, " + name + "!");

(If you didn't type anything in the last 5 minutes, you've been doing it
wrong. [Go back to start.](#making-the-computer-say-things))

## The Greeter

Ok, now we've got the computer saying things to us. But that last example
hinted at fun stuff. Let me repeat it.

    var name = prompt("What's your name?");
    alert("Hello, " + name + "!");

Try variations of that. E.g. use different greetings, ask different things,
maybe be a bit more polite or less polite or scream at your user by
converting their name to upper case (using `name.toUpperCase()`).

## The Picky One

But we can do more stuff. For example what if we don't want anyone to not
like giraffes? We'll try that.

    var likesGiraffes = confirm("Do you like giraffes?");
    
    if (likesGiraffes) {
        alert("Good.");
    } else {
        alert("Wrong.");
    }

## The Mathematician

Let me introduce another function: `parseInt(textWithANumberInIt)`. If you
pass a string to it that contains a number, then you get back that number
as a number.

Why would you ever want to do such a thing? Let me show you.

    var notQuiteANumber = "3";

    notQuiteANumber + 2;

If you try that, your computer will do something that you might not expect.

So, try `parseInt` out for a bit. I'll wait here and then I'll introduce
you to the mathematician.

(Did you do that? If so, read on.)

    var maybeOnePlusOne = prompt("What's 1 + 1?");
    if (parseInt(maybeOnePlusOne) == 2) {
        alert("Mhh... ok.");
    } else {
        alert("Almost.");
    }

(Let me bug you once again: Try with different numbers, calculating more
complex things, different answers and so on. If you don't like whole numbers
you will be delighted that `parseFloat` exists as well.)

## The Grumpy Mathematician

Mathematicians have it very hard. They think and think all day about very
complex things (and go for a walk in the park and <del>relax</del>think some
more. And then people can't tell them what `1 + 1` is. (Never mind why
they would like to know that. Figures.)

Anyway, sometimes they get grumpy, especially if people are very far off
with their guesses.

    var guess = prompt("What's 1 + 1?");
    var guessNumber = parseInt(guess);

    if (guessNumber == 2) {
        alert("Heureka!");
    } else if (guessNumber == 1 || guessNumber == 3) {
        alert("Almost.");
    } else if (guessNumber > 10) {
        alert("NO.");
    } else {
        alert("NOOOOOOOOOOOOOOOOOOOOOOOO!");
    }

Sorry, grumpy mathematician, you know you should have talked of
[drawing circles][] or [dragons][]...

[drawing circles]: https://www.youtube.com/watch?v=QncgmzH6yQU
[dragons]: https://www.youtube.com/watch?v=EdyociU35u8

## Our first adventure

Enough with the simple things, let's try an adventure. A small one, to be sure,
but an adventure nonetheless.

    alert("You are in a small room. There's a dark corner. Maybe there's a monster in it.");

    var sayHello = confirm("Do you say hello to it?");
    if (sayHello) {
        alert("You say hello to the monster. But it doesn't answer. Maybe it's just shy.");
    } else {
        alert("The corner smiles. You're not sure if that's good.");
        alert("The monster has dinner.");
    }

Ok, let's break that down a bit.

* first, you tell our adventurer something. kind of like an exposé
* then, you ask the user if they want to greet the monster

    you do this by using `confirm`, which returns `true` for an affirmative
    answer and `false` otherwise.

    we interpret those as "yes" and "no", respectively.
* depending on the answer, you display different endings to the user.

And now, you're going to write your own adventure. Have fun!

## A bigger adventure

Let's try a bigger one. It even has two rooms!

> You are in a small room. It has two doors, do you take the first?

    var takeFirstDoor = confirm("You are in a small room. It has two doors, do you take the first?");

> You take the first door. It's a nice room, with a comfy chair. Oh, it also
> has some books in it. Want to take a closer look?

    // takeFirstDoor == true
    var lookAtBooks = confirm("You take the first door. It's a nice room, with a comfy chair."
        + "\nOh, it also has some books in it.\n Want to take a closer look?");

> You take a closer look. There are three of them. The first has lots of signs
> and triangles on it, the second has an eye on it and the third one has just
> a circle one it.
> Which one do you want to see? (triangles, eye or circle)

    // lookAtBooks == true
    var whichBook = prompt("You take a closer look. There are three of them."
        + "\n\nThe first has lots of signs and triangles on it, the second"
        + " has an eye on it and the third one has just a circle one it."
        + "\n\n Which one do you want to see? (triangles, eye or circle)");

    if (whichBook == "triangle") {
        alert("Principia Mathematica, it says on the front."
            + " You think of the mathematician from before and shudder.");
        location = "https://en.wikipedia.org/wiki/Principia_Mathematica";
    } else if (whichBook == "eye") {
        alert("It's a book about cats, rejoice!");
        location = "http://www.amazon.com/Cute-Cats-Around-World-pictures/dp/148189076X";
    } else if (whichBook == "circle") {
        alert("It's not a book at all, it's some kind of moving image in a frame...");
        location = "https://www.youtube.com/watch?v=QncgmzH6yQU";
    } else {
        alert("That's not a book!");
        location = "http://httpcats.herokuapp.com/404";
    }

That was a lot of stuff, let's skip the rest. You can play the game
[here](../examples/first-adventure.html)
