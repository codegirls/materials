# materials - codegirls

This is the source for our [materials site][]. If you were looking for our
materials, you can either visit the new site at <http://codegirls.github.io/materials>
or look at [the "old" materials][materials old].

[materials site]: http://codegirls.github.io/materials
[materials old]: https://github.com/codegirls/materials/tree/adcfbcbf8756c7087e88a582b6c335eb8fc99610

## adding tutorials

* contributions welcome, of course!
* create a new file in the [`section` subdirectory](./section)
    - the naming convention is `my-new-tutorial-3.md` (all lower caps,
      dashes between words, a number at the end if it's a series)
* add a yaml front matter at the beginning (this describes the tutorial
  and sets the title/next tutorial

    ```
    ---
    title: My new tutorial - Part 3
    next: my-new-tutorial-4.html
    updated: 2014-05-27
    ---
    
    # My new tutorial - Part 3
    
    Markdown for the tutorial goes here
    ```

    - you can omit the `next` line if there's no next tutorial, the generator
      will then link back to the main site
    - you must use a `.md` ending for the file you create (e.g. for the tutorial)
    - but the `next` field must have a `.html` ending (this is because the
      generator converts the original `.md` file to `.html` but isn't smart
      enough to change the ending in the `next` field (the next field is
      just an invention of us, it isn't "standard")
* write away!
* add a link to the first part of your tutorial to [`index.html`](./index.html)
  (this is optional, otherwise we'll do it. if you're not sure, don't do this
  right away, we'll find a place for it and then add it.)
* as always: if you have any questions: ask away!
* for bonus points:
    - do your work in your fork or in a separate branch
    - create a pull request when you have a bit of content (or want
      initial feedback)
    - we'll play a bit back and forth and then merge your changes!
* thanks a lot!

## in the future (probably)

* hacker blog pt 3: questions, linking between stuff, probably
  templating and/or css
* more ruby
* more challenging topics, e.g. something to solve alone/in teams

## ideas for topics

* a chatbot, hubot would be cool, but something of our own might be
  easier for starters
* a collaborative, 2d, colored pixel-placing game with a simple api
  (for starting out with javascript)
* a simple synthesizer ([overtone](http://overtone.github.io) would be
  awesome, otherwise something in javascript?)
* some reading material (js primer) and a task to accomplish as a
  slightly more difficult task that requires a bit of thinking and
  experimenting.
* building a simple text-adventure (with `prompt` and friends or simply
  with links, not sure yet)
