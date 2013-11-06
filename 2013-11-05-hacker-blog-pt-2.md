# Hacker Blog Pt. 2: Jekyll & Markdown

* check that you have ruby installed

        $ ruby --version
        ruby 2.0.0p247 (2013-06-27 revision 41674) [x86_64-linux]
* install jekyll: `gem install jekyll`
    - a tiny web server that converts markdown into html
    - is used by github pages (e.g. what we use to publish the blog)
    - we use it to preview our changes locally
* commandline interlude:
    - most commands work like this: `<cmd> [<options>]`
    - some have subcommands: `<cmd> <subcmd> [<options>]`
    - options are also called "flags"
        * they often have a long and a short version, for example
          `jekyll` has a `--watch` option, but you can also use the
          short option `-w` to achieve the same
    - most commands have a builtin help (one of the following should
      work):
        * `<cmd> --help` (e.g. invoke `cmd` with the `--help` option)
        * `<cmd> help` and `<cmd> help <subcmd>`
        * or one of those: `<cmd> <subcmd> --help`, `<cmd> -h`
* check that jekyll works:

        $ jekyll --version
        jekyll 1.1.2

    other versions work too, but if it is `0.x.y` then you might have to
    use different options
* start jekyll:

        $ jekyll serve --watch   # if you have jekyll 1.x.y
        $ jekyll --server --auto # if you have jekyll 0.x.y
* create a markdown file, for example `hello_world.md` in the blog
  directory and put some markdown in it (for example [like this][hello_world.md])
* visit <http://localhost:4000/hello_world.html> in your browser (or
  `http://localhost:4000/<filename without the .md extension>.html` if
  your file is not called `hello_world.md`)
* [learn some markdown](http://markable.in/file/aa191728-9dc7-11e1-91c7-984be164924a/)

phew. :)

[hello_world.md]: https://raw.github.com/heyLu/codegirls/master/hackerblog/hello_world.md
