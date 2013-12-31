abaqis-3.0 Design HUB
=====================

[![Built with Grunt](https://cdn.gruntjs.com/builtwith.png)](http://gruntjs.com/)

Design hub for Abaqis3.0

Design HUB Dev Setup

install [NodeJS](http://http://nodejs.org/) which also installs [npm](https://npmjs.org/)

The Design HUB was built with [Yeoman](http://yeoman.io) using the Yeoman [Archetype-Jekyll generator](https://github.com/kwaledesign/generator-archetype-jekyll)

It uses [Grunt](http://gruntjs.com), [Bower](http://bower.io), and
[Jekyll](http://jekyllrb.com)

The Design HUB is hosted on Providigm’s Trinity server under Brian’s user name.

Config your local machine to access Trinity

  1. In your machine’s `/etc/hosts` file add this entry:

```
192.168.218.9   trinity trinity-bcampbell.abaqis.int
```

The credentials to trinity: bcampbell  (and the password Vinnie chose)

The `dist/` directory is served to: `trinity:/var/www/trinity-bcampbell/current/public`

The Design Hub will be available to your browser via the base URI: `https://trinity-bcampbell.abaqis.int`


## Setup Node/Grunt/Jekyll/Bower

  1.  Install Grunt
```
$ npm install -g grunt-cli
```

  2.  Install Jekyll
```
$ gem install jekyll
```

  3.  Install Bower
```
$ npm install -g bower
```

  4.  Clone the Design-HUB repo
```
$ git clone [hub git address...which will change soon...]
```

  5. `cd` to project directory
```
$ cd [hub repo name ....which could change soon]
```

  6. Wire up ruby and your gemset via RPM
```
$ rvm install ruby-2.1.0 (version/patch doesn't matter...we're only using ruby to run Sass/Compass)
$ rvm gemset create designHUB (or whatever you care to call it)
$ echo ruby-2.1.0 > .ruby-version (not actually needed but whatevah)
$ echo designHUB > .ruby-gemset (not actually needed but whatevah)
$ rvm use ruby-2.1.0@designHUB
$ bundle
```

  7. Poor yourself a double Vinnie...we're almost there!

  8. `cd` into your project root
```
$ cd [whatevah we name this thing]
```

  9. Run grunt
```
$ grunt
```
(if you get  errors, run again with the `--force` flag, which forces it to ignore non-fatal errors.)

This runs all the default tasks...which are more than we need for this, but haven't yet been cleaned up...sorry.

  10. Start up a local Node server to view your work
```
$ grunt server
```
(again, if you get errors try it with `--force`)

This will open the generated static site into your default browser and watch for changes in your root directory. Every time you save, Grunt will inject your changes into the browser for you.

## Adding a new blog post to the Design HUB

  1.  within the app/_posts/ directory, create a new file:
```
[yyyy]-[mm]-[dd]-[your-post-title].md
```
(notice the `.md` file extension)

  2. at the top of this new file add the following yaml snippet
surrounded by triple dashes (this tells jekyll which layout we
want the post to be rendered with)
---
layout: post
title: [your-post-title]
---
(take a look at any of the existing posts for additional examples)

  3. add what ever content you want to your new post using [markdown
     syntax](http://bywordapp.com/markdown/syntax.html)


  4. when you are done commit your changes (from root)
```
$ git status
$ git add [what-ever-files-you-changed]
$ git commit -m "message describing your commit"
$ git push origin [your-branch-name]
```
Now your changes have been pushed to the repo's GitHub page on your branch...yay!!!

## Uploading the updated Design HUB to Trinity:

[Grunt task to do this automatically coming soon] Until then, file a pull
request and ping on me and I'll scp it.

