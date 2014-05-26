---
title: The Tiniest Blog!
next: pixl-1.html
updated: 2014-05-26
layout: section
---
# The Tiniest Blog

If you always thought __programming__ and __coding__ sounds kind of cool and wanna try it yourself, you came to the right adress.
This tutorial will explain to you what this magical web is everybody is talking about. Furthermore you'll learn a lot of really cool stuff and be even able to build your own blog at the end. Just wait and see, you'll be a little code monkey in no time!

## Goals
* Basic principles of creating and building Websites
* Understanding the basic principles of the web
* Creating a complete website
* Knowing where and how to learn more about the things you are interested in
* Possibilites and boundaries 

## What is "The Web"?

### Websites

* Have an address (URL)
* Your browser downloads a website and displays it
* Actually just text (HTML-code)

```
<!doctype html>
<html>
  <head>
    <title>Hallo, Web!</title>
    <meta charset="utf-8" />
  </head>
  
  <body>
    <h1>Hallo, Web!</h1>
    <p>Webseiten bestehen eigentlich bloß aus Text wie diesem hier</p>
    <p>Man kann sich diesen Text auch von jeder Website anschauen</p>
    <p>Und das wichtigste: Links sehen <a href="../introduction.html"> so aus!</a></p>
  </body>
</html>
```
[(Beispiel anschauen)] (../examples/01-structure.html)
* Are most times located on a server. You can also develop and save locally, but then nobody else can see your website.

### client / Server

* Browsers are clients (as well as screen readers, search engines and other programs)
* A server provides websites. This means the server receives requests for certain addresses (URLs) and answers them with source code.
* Clients then proceed to follow cross references (links) in these documents and embed various media (CSS styles, JavaScript code, images, videos or music)

### Standards (HTML, CSS and JavaScript)

* The source code of websites is written in a language called HTML
* Defined by a consortium
* Browser converts the definition
* HTML describes content and structure of websites
* CSS describes appereance. Put in other words: HTML is the body you can applicate your Make-up (CSS) on.
* The programming language used to realize dynamic behavior is calle JavaScript. Most websites use a form of JavaScript


## Your first website

First attempt: Only text

* own or [generated] (http://loripsum.net/api/5/plaintext) text
* Create a file called `webseite.html` and copy your text there.
  - We need a text editor for this (text ≠ document)
* Watch in your browser [(Beispiel)] (examples/00-justtext.html)

Something is still missing ...

### HTML (HyperText Markup Language)

* Consists of *elements* marked with so called *tags* so that your browser knows what to display
* Example
```
<p>
This is an paragraph.
HTML ignores paragraphs, so if you want to have paragraphs you have to create new paragraphs
</p>

```
<p>
You can cheat a little by using the `br` element. For example like this
<br />
This is not considered as good style, i.e. most times you'll just use various paragraphs
</p>

[(Beispiel anschauen)] (examples/02-paragraphs.html)
* 



