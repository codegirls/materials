# hello CSS, hello templates

well, we now have a small website, with a homepage and several other
linked pages originally written in markdown. but they're not pretty yet,
let's them them prettier.

oh, and if you'd like to we can hack some advent calendars.

# devtools

on any page in your browser (in chrome or firefox) you can right-click
on any element on the page and select "inspect element" (or similar).
this will open the "inspector"-tool that allows you to see the model of
the page the browser uses. you can also edit the page with it, adding or
changing text and styles.

# CSS

* a language that is used for styling (Cascading Style Sheets)
* it consists of `selectors` and `rules` for those selectors, e.g. you
  say how part of your page should look like

        /* make headings really big and bright */
        h1 {
            font-size: 50pt;
            color: red
        }

        /* make some links annoying */
        a.highlighted {
            background-color: yellow;
        }
* that was some css, usually it's either in a `<style>` element inside
  the `<head>` of a html page or in an external file and linked to using
  `<link rel="stylesheet" href="awesome.css" />`

## let's make a menu bar

* we'd like to have a quick overview at the top of our homepage
* let's create a list of links to do that:

        <ul class="menu">
            <li><a href="/fun_times.html">Fun times!</a></li>
            <li><a href="/blargh.html">About me (or something)</a></li>
            <li><a href="/links.html">Other places</a></li>
        </ul>
* place that before everything else in the `<body>` element of your
  `index.html` file
* and put the following CSS inside a `<style>` element

        .menu {
            list-style-type: none;
            padding: 0;
        }

        .menu li {
            float: left;
            margin-right: 1em;
        }

        .menu + * {
            clear: both;
        }

# hello templates!

now that we have the ability to make our homepage prettier we'd like to
do the same for our markdown pages. but how? copying the `<style>` for
each element would be cumbersome and i didn't tell you that you can put
html inside markdown elements yet.

thankfully, jekyll supports `templates` that allow you to put the
generated markdown inside another predefined html document.

* make a directory called, `_layouts` and create a file called
  `post.html` in it
* for a start put the content from `index.html` inside the new file
* at the end of the `<body>` element, put the following template:

        <div id="content">
            <h1>{{page.title}}</h1>
            {{page.content}}
        </div>
