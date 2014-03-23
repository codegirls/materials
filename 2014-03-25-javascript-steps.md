# JavaScript in small steps.

If you've never programmed before, a lot of things about JavaScript seem
weird and kind-of unexplainable. Apart from the stuff we usually do,
I'll try and explain the line example again, this time, from the ground
up.

Let's have a look at it again:

    function vertical_line(start, length) {
        var draw_y = start.y;
        for (var draw_x = start.x; draw_x < start.x + length; draw_x += 1) {
            pixl.draw_pixl({x: draw_x, y: draw_y});
        }
    }

    vertical_line({x: 0, y: 0}, 10);

Mhh. That's a lot of stuff. Here's a little image with all the different
parts highlighted:

![...](...)

As you can see, it involves a lot of parts. So let's take it apart. As
with most things, the individual parts are quite simple, actually.

## From Literals to Function Invocations

From now on, we'll mostly use code for the explanations. The
explanations themselves will be in *comments*. Comments are lines that
start with `//`. JavaScript ignores those so you can write anything you
want in them.

One more note: You should try out all the code below. Type it in the
console and see what it does. And then try to change it a bit and see
how the result you get back changes.

    // JavaScript understands numbers:
    3;
    4;
    -1;
    3.141592653589793;

    // And objects:
    {}

    // Objects have attributes:
    ({a: 1, b: 2});    // an object with the attributes `a` and `b`

    // So now we have numbers and objects, but how can we do anything
    // with them?

    // Well, we can do some obvious things with numbers:
    1 + 2;
    2 - 1;
    2 * 4;
    2 / 4;

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

    // Try describing what incrementCount does in your own words.

    // Ok, good. Now we can increment numbers, but that's still a far
    // stretch from `vertical_line`.
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

    // Try doing the same for is height. (Remember, exactly 0.03 meters.)

    // ... (Try it!)

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

    // We can do interesting things with this, like jumping multiple
    // birthdays forward:

    var howManyJumps = 3;
    var olderPaula = paula;
    for (var i = 0; i < howManyJumps; i += 1) {
        olderPaula = birthdayTimeMachine(olderPaula);
        console.log("Paula is now " + olderPaula.age + " years old and " + olderPaula.height + " meters tall.");
    }
    console.log("Time jump finished!");

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

    Math,random() * 1000;

    Math.round(Math.random() * 1000);

    // Run the following on http://pixl.papill0n.org

    pixl.disconnectAndClear();
    for (var i = 0; i < 50; i++) {
        var posX = -20 + Math.random() * 40;
        var posY = -20 + Math.random() * 40;
        pixl.draw_pixl({x: posX, y: posY}, "green");
    }
