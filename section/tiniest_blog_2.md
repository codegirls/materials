---
title: Tiniest Blog More HTML
next: pixl-2.html
updated: 2014-05-26
layout: section
---

# More HTML

Just plain text can get a bit boring. But HTML can do so much more ...
For a start, why don't you spice things up with some __images__?

## Images

* Images are marked with the `img`element

    ```
    <h1>
    Eine Katze!
    </h1>
    <img src="http://placekitten.com/400/400?image=9" />
    ```

*  HTML is a little bit more complicated because of:
  - self-closing elements `<... />`
  - attributes `src=".."`

## Lists

Sometimes it is useful to list things. For example all the cute cate memes you collected at your journey through the web.
Your friends will love your __list__ with cute kittys!

    ```
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
    ```
## Tables

And sometimes you need to be *really* organized. This is a case for __tables__!

```
<table>
    <thead>
    <tr>
        <td>Name</td>
        <td>Alter</td>
        <td>Beschreibung</td>
    </tr>
    </thead>
</table>

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
```

## Videos

* element `<video src="wonderful-world.mp4" />`
* Actually it's a bit more complicated
    - you have to know the URL of your video file
    - Unfortunately the majority of platforms like YouTube or Vimeo don' allow this
* That's why we use *embed* codes
    - YouTube & Co. provide you with a HTML code you can use for your website to embed the video
    - *How to get the code?*
      Go to the page with the video, e.g. (here)[https://www.youtube.com/watch?v=QncgmzH6yQU], click "Share", then             "Embed" and copy the stated code to your own website

    ```
        <iframe width="560" height="315"
    src="//www.youtube.com/embed/QncgmzH6yQU"
    frameborder="0" allowfullscreen>
</iframe>
    ```
    
    - Tip: The code changes depending on which size and border color for your video you choose

## Audio
    
    
    
    
    
    
    
    
    
    