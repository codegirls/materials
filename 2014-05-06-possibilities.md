# Possibilities

Sorry, I have not really "fully" prepared anything today, but we do have
stuff left over and I do have some things. (Just not fully prepared
things. :)

## Testing the time machine

Does it work? Did you finish it? Try explaining why it is a time machine
and what your favourite time machine could do better. (And of course
trying to implement that time machine would be the best.)

More questions:

* counting:
    - `1..101`
    - `13..42`
    - `47..-8`
* working with [arrays](ttps://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Values,_variables,_and_literals#Array_literals)
    - put all those numbers you produced above into arrays

        ```
        var array = [];
        array.push(1); // => array == [1]

        array.push(2);
        array.push(21); // => array = [1, 2, 21]

        array[0]; // => 1
        array[1]; // => 2
        array[2]; // => ?
    - `haveISeenYouBefore`?

## Simone

To run the functions below, put them in [pipes][] and supply the appropriate input.

* tokenize: input: the base text you want to use, [Project Gutenberg](http://gutenberg.org)
    has a huge collection of public domain texts availlable.

    ```
    return input.split(/([\s,\.\?!]+)/).filter(function(s) { return s.match(/\w+|[,\.\?!]/); }).map(function(s) { return s.trim(); });
    ```
* generate dictionary: input is the output from `tokenize`

    ```
    var dict = {};

    var previousWord = null;
    for (var i = 0; i < input.length; i++) {
        var word = input[i];
        if (previousWord != null) {
            if (!dict[previousWord]) {
                dict[previousWord] = [];
            }
            dict[previousWord].push(word);
        }
        previousWord = word;

    }

    return dict;
    ```
* generate sentence

    ```
    function chooseRandom(obj) {
        var keys = Object.keys(obj);
        var length = keys.length;
        var key = keys[Math.floor(Math.random() * length)];
        return obj[key];
    }

    var sentence = "";
    var currentWord = chooseRandom(Object.keys(input));
    for (var l = 0; ; l++) {
        sentence += currentWord + " ";
        var followWords = input[currentWord];
        if (currentWord == "." || followWords.length == 0) {
            break;
        }
        currentWord = chooseRandom(followWords);
    }

    return sentence;
    ```

## Other things

* [interact with functions][pipes]
* [babl](http://babl.papill0n.org)
* SuperCollider

[pipes]: http://papill0n.org/weird_dreams/pipes.html
