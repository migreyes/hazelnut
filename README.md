
## Hazelnut: A barebones starting point for Jekyll

### About this site template:
This is a [Jekyll](http://jekyllrb.com) template which uses Sass and CoffeeScript for assets, and Rake tasks for handy help with development. It assumes you’re using [Pow to serve your site](http://pow.cx) locally. Since this is geared for designers starting from scratch, there’s no styling.

If you’re a developer looking for pre-designed Jekyll themes, I’d recommend [Poole](http://getpoole.com) by Mark Otto.

=====

### Websites started from this template:
[mig.io](http://mig.io), my personal site.  
[humblepied.com](http://humblepied.com), a video interview site. (View the [repo](http://github.com/migreyes/humblepied).)  
[basecamp.com](http://basecamp.com), the marketing site for Basecamp.  
[basecamp.com/help](http://basecamp.com/help), the help documentation site for Basecamp.  
[37signals.com/incoming-transmission](http://37signals.com/incoming-transmission/), an archive of the best of the web.

=====

### First time setup:

Open the `Rakefile` and update the top variables with your preferred Pow address, your actual website URL, and as a bonus, your GitHub repository URL. From here, you can fire off a `rake pow` to easily generate your .dev address, which the rest of the `rake` commands depend on having already set up.

=====

### Basic `rake` commands you’ll commonly use:

`rake` to watch and update your HTML, Coffee and Sass.

`rake build` to build a clean, compressed copy of the site.

`rake view` builds a fresh copy of your site, then opens it locally.

`rake view:xip` generates an [xip.io](http://xip.io) friendly URL and opens it.

`rake view:github` to head to your GitHub repository.

=====

### Adding new JavaScripts:

There’s no asset pipeline, but our `rake` tasks will automatically join any `.coffee` files we create into one file automatically for us.

All .coffee files should go into: `_source/_assets/coffescript/`  
Any external JavaScript should go into: `_source/assets/javascript/`

=====

### Adding new stylesheets:

Since thhere’s no asset pipeline, when we’re adding a new stylesheet we’ll need to do just two things. Let’s pretend we want to add a new stylesheet for an About page on our new site.

**First,** we’ll add our underscore-named file to the proper directory.  
In our case, we’ll add this: `_source/_assets/sass/pages/_about.scss`

**Last,** we’ll define our new stylesheet inside the main **style.scss** file.

```css
@import
  'pages/about', /* Adding a stylesheet for an About page. */
  'pages/home';
```

=====

### About Mig:
I’m [a graphic and web designer](http://mig.io) from Chicago. I proudly work at [Basecamp](http://basecamp.com) to help make everyone’s favorite project management app better, and I teach at [The Starter League](http://starterleague.com).

=====

Questions?  
[@migreyes](http://twitter.com/migreyes) on Twitter is your best bet.

Elsewhere online:  
http://mig.io  
http://dribbble.com/migreyes  
http://instagram.com/migreyes

=====

Happy making.