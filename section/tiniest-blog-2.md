---
title: More HTML
next: tiniest-blog-3.html
updated: 2014-05-26
layout: section
---

# More HTML

Just plain text can get a bit boring. But HTML can do so much more ...
For a start, why don't you spice things up with some __images__?

## Images

* Images are marked with the `img` element

        <h1>Eine Katze!</h1>
        <img src="http://placekitten.com/400/400?image=9" />

*  HTML is a little bit more complicated because of:
  - self-closing elements  `<... />`
  - attributes `src=".."`

## Lists

Sometimes it is useful to list things. For example all the cute cate memes you collected at your journey through the web.
Your friends will love your __list__ with cute kittys!

    <p>Cute Kitty</p>
   
    <ul>
        <li><img src="http://placekitten.com/300/300?image=1" /></li>
        <li><img src="http://placekitten.com/300/300?image=5" /></li>
        <li><img src="http://placekitten.com/300/300?image=12" /></li>
        <li>And many more ...</li>
    </ul>
 
    <p>It takes three to form a hipster triangle</p>
    
    <ol>
        <li>Eins</li>
        <li>Zwei</li>
        <li>Drei</li>
    </ol>


## Tables

And sometimes you need to be *really* organized. This is a case for __tables__!


    <table>
        <thead>
            <tr>
                <td>Name</td>
                <td>Alter</td>
                <td>Beschreibung</td>
            </tr>
        </thead>

        <tbody>
            <tr>
                <td>Awesome Code Monkey</td>
                <td>12</td>
                <td>Loves code adventures on the web - bananas!</td>
            </tr>
            <tr>
                <td>Cute Kitten Cookie</td>
                <td>Cookie does not talk about age</td>
                <td>Loves sweet milk and cookies, bows and little bells </td>
            </tr>
        </tbody>
    </table>


## Videos

* element `<video src="wonderful-world.mp4" />`
* Actually it's a bit more complicated
    - you have to know the URL of your video file
    - Unfortunately the majority of platforms like YouTube or Vimeo don' allow this
* That's why we use *embed* codes
    - YouTube & Co. provide you with a HTML code you can use for your website to embed the video
    - *How to get the code?*
      Go to the page with the video, e.g. [here](https://www.youtube.com/watch?v=QncgmzH6yQU), click "Share", then             "Embed" and copy the stated code to your own website

  
            <iframe width="560" height="315"
                src="//www.youtube.com/embed/QncgmzH6yQU"
                frameborder="0" allowfullscreen>
            </iframe>
  
    
    - Tip: The code changes depending on which size and border color for your video you choose

## Audio

* Similar to videos. Just give it a try!
* [Here](https://soundcloud.com/mio_myo/sternwarte-observatory-ep-01) is a link you can use

## Many more elements

* Now we had the chance to meet the most common elements
* There are many more out there, though. It's impossible to remember them all, so we found a handy [overview](http://www.w3.org/TR/html-markup/elements.html)
 
## Several Pages

* So far we dealt just with links to *other* websites
* Different pages of one website need links *among themselves*

 One page:

    <!-- 08-links1.html -->
    <p>Link to <a href="08-links2.html">another page</a>.</p>
    <p>Or do you wanna <a"../more-html.html">go back to our tutorial</<>?</p>

 And another one:

    <!-- 08-links2.html -->
    <p>Und wieder <a href="08-links1.html">zurück</a>.</p>
  

This is a cool new trick - and it's an easy one as well. And although this may seem simple to you, you can build *choose-your-adventure* stories just with this. And of course you use links between the pages of almost every website.
    
## Interesting links you might like

German:

* [SelfHTML](http://wiki.selfhtml.org/wiki/Startseite)

English:

* [Twine](http://twinery.org/), interactive non-linear storytelling. An advanced demonstration about how to use links to tell stories
* [HTML and CSS at codeacademy](http://www.codecademy.com/tracks/web). The classic of do-it-yourself learning
* [Overview about HTML elements](http://www.w3.org/TR/html-markup/elements.html)
*  More explanations and examples has this [overview](https://developer.mozilla.org/en/docs/Web/HTML/Element)
    
    
    
    
    
    
    
    
