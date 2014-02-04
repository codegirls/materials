# musical adventures

if you dare to, you can make music. things might be quite a bit rough,
because i didn't prepare it very well.

we're going to make music using [overtone](https://overtone.github.io).

## quickstart

* install [Light Table](http://lighttable.com)
* download and extract [quick-make-music!](https://github.com/heyLu/templates/archive/quick-make-music!.zip)
* open Light Table and press `Ctrl + Shift + o` and open the file
    `noise.clj` from the extracted folder.

now you should have a file open with lots of parentheses in it. that's
because overtone is written in Clojure, which is a LISP, which means it
has lots of parentheses that scare some programmers and also makes it
a wonderful language for all kinds of things.

to evaluate (execute) code in that file, go to the line containing the
code and press `Ctrl + Enter`. the first time you do that it will take a
while, but when it finishes a little blue box should appear besides the
line you evaluated.

start by evaluating the very first line in `noise.clj`. (the one with
`(ns noise ...` in it.)

after that, evaluate the other expressions in the file.

## reading material

the [overtone website](https://overtone.github.io) has an overview.

the code in `noise.clj` is mostly from [these][beats] [two][chords]
articles on the [wiki][wiki].

there's also a [cheatsheet][] with lots of funny names of functions on
it that you can try out.

to view the documentation for a function, put the cursor over the function
and press `Ctrl + d`.

[beats]: https://github.com/overtone/overtone/wiki/Live-coding
[chords]: https://github.com/overtone/overtone/wiki/Chords-and-scales
[wiki]: https://github.com/overtone/overtone/wiki
[cheatsheet]: https://github.com/overtone/overtone/raw/master/docs/cheatsheet/overtone-cheat-sheet.pdf
