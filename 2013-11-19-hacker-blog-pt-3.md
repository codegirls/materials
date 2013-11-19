# Hacker Blog Pt. 3: Recap

questions you should ask or maybe try to answer:

* how do i include an image?
* how do i link to other sites?
* how do i link to other pages of my site?
* how do i include videos?
* how do i add style?

* what does jekyll do?
* what is markdown?
* try writing equivalent markdown and html

## Templating

* markdown alone only lets you write basic html, but we also want
  consistent styling for all pages and probably even a list of pages
* jekyll has [templates][] with which we can do that

    <!doctype html>
    <html>
    <head>
        <title>my awesome blog!</title>
        <meta charset="utf-8" />
    </head>

    <body>
        <ul>
        {% for post in site.posts %}
            <li><h1>{{post.title}}</h1></li>
        {% endfor %}
        </ul>
    </body>
    </html>

[templates]: http://jekyllrb.com/docs/templates/
