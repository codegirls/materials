# Let's make a Hacker Blog™

- summary: publish a github-pages enabled git repository, put some html
  in it and see it online. push to change the online version.

## Git basics

- a time-machine for (mostly text) files
- stores the state of a directory at specific points in times (commits)
- you can change stuff, delete files & generally do what you want. but
  if you want your old changes back, you can do that.

- git setup (configure email, name and probably the editor aswell)

## Creating a repository

- create an account on [GitHub](https://github.com)
- create a repository called `<your username>.github.io` in the web
  interface (the book with the plus-icon on the upper right)
- create a directory locally, make it a git repository too

        $ mkdir hackerblog
        $ cd hackerblog
        $ git init
- create a file called `index.html` in that directory and make it look
  like [this one][index.html]
- add the changes to git

        $ git add index.html
        $ git commit
- push to github: `git push -u origin master`
- wait a few minutes (probably 10 or so)
- visit your blog at `http://<your username>.github.io`, you should see
  the html page that you just created
- to preview your changes you can view the `index.html` file locally

[index.html]: https://github.com/heyLu/codegirls/tree/master/index.html
