# A simple image gallery & making ruby count

Two things:
* how to make a simple image gallery
* making ruby count things for you

## Making a simple image gallery

* what we want is a html page with images on it. clicking those images
  should display larger versions of them.
* that's called a lightbox
* let's start with a simple html file

        <!doctype html>
        <html>
        <head>
            <title>foxes!</title>
            <meta charset="utf-8" />
            <style type="text/css">
            #foxes img { max-width: 100px; }
            </style>
        </head>

        <body>
            <div id="foxes">
                <img src="http://25.media.tumblr.com/0efa8bcd3ad7730781f1f37cdd5f4df4/tumblr_mtioj6TNBq1rdzz4io2_500.jpg" />
                <img src="http://31.media.tumblr.com/3b8662c5da6a4efebdba3f7a99932803/tumblr_mtioj6TNBq1rdzz4io4_500.jpg" />
                <img src="http://25.media.tumblr.com/1e90781785482abc978fcc69e62a5b5c/tumblr_mtioj6TNBq1rdzz4io5_400.jpg" />
                <img src="http://25.media.tumblr.com/a40acc7081fb3c53e9115e47f6786902/tumblr_mtioj6TNBq1rdzz4io6_500.jpg" />
                <img src="http://25.media.tumblr.com/bd984b9673425d791042753c58b47631/tumblr_mtioj6TNBq1rdzz4io10_500.jpg" />
            </div>
        </body>
        </html>
* ok, but how do we make these images clickable? by putting links around
  them! e.g. modify all the `img` elements as follows:

        <a href="http://25.media.tumblr.com/bd984b9673425d791042753c58b47631/tumblr_mtioj6TNBq1rdzz4io10_500.jpg">
            <img src="http://25.media.tumblr.com/bd984b9673425d791042753c58b47631/tumblr_mtioj6TNBq1rdzz4io10_500.jpg" />
        </a>
* usually, you would use the url for the "full image" as the value of
  the `href` attribute of the link and a smaller thumbnail version for
  the `src` attribute of the image
* mhh, that's still not *dynamic*!
* well, add the following inside the `head` element:

        <link rel="stylesheet" href="http://lokeshdhakar.com/projects/lightbox2/css/lightbox.css" />
* and the following right before the end of the `body` element:

        <script src="http://lokeshdhakar.com/projects/lightbox2/js/jquery-1.10.2.min.js"></script>
        <script src="http://lokeshdhakar.com/projects/lightbox2/js/lightbox-2.6.min.js"></script>
* aand add a `data-lightbox` attribute to all of the links around the
  images. if you want to display them as a collection set the attributes
  to the same value (e.g. `data-lightbox="foxes"`), otherwise just use
  whatever different values you want
* reload! now when you click on one of those images, it should display
  them nicely.
* what did we just do? we used [lightbox](http://lokeshdhakar.com/projects/lightbox2/),
  a javascript library to add a lightbox for all our images. the script
  searches for links with a `data-lightbox` attribute and displays the
  larger version on click.
* have a look at the [finished version](image-gallery.html)

## Making Ruby Count

counting is difficult. computers are better at it. also: instance
variables.

    class Counter
        def initialize
            @count = 0
        end

        def increment!
            @count += 1
        end
    end

* put that into a file, e.g. `counter.rb`
* start `irb` from the same directory you saved that file in

        $ cd /path/to/counter/rb/file
        $ ls
        counter.rb
        $ irb
        irb>
* then type `require "./counter.rb"`, this loads the code from the file you
  just created. then we can use the `Counter` class:

        irb> require "./counter.rb"
        => true
        irb> Counter
        => Counter
        irb> Counter.new
        => #<Counter:0x00000001020a20 @count=0>
        irb> Counter.new.increment!
        => 1
        irb> Counter.new
        => #<Counter:0x000000010d3e40 @count=0>
* mhh... how do we count higher? by storing the counter in a variable!

        irb> c = Counter.new
        => #<Counter:0x000000018bd4f8 @count=0>
        irb> c.increment!
        => 1
        irb> c
        => #<Counter:0x000000018bd4f8 @count=1>
        irb> c.increment!
        => 2
        irb> c.increment!
        => 3
        irb> c
        => #<Counter:0x000000018bd4f8 @count=3>

* things to try:
    - add a `count(amount)` method that adds `amount` to the counter
    - implement a `reset!` method that sets the counter back to zero
    - try counting things by name, e.g. it should act like the following (you
      need to know hashes/maps for this)

            irb> c = NameCounter.new
            #<NameCounter:0x00000001023d30>
            irb> c.count("cat")
            irb> c.count("mouse")
            irb> c.count("cat")
            irb> c.how_often?("cat")
            => 2
            irb> 10.times { c.count("weirdo") }
            irb> c.how_often?("weirdo")
            => 10
