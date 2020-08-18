
# WashU WiCS Website run by Jekyll (static site generator)
##### Instructions below by Priyanka Iyer and some of Barry Clark's original instructions

### Instructions 

## Local Development
1. Install Jekyll and plug-ins in one fell swoop. `gem install github-pages` This mirrors the plug-ins used by GitHub Pages on your local machine including Jekyll, Sass, etc.
2.  Serve the site and watch for markup/sass changes `jekyll serve`
3. (SKIP THIS 2 WORKED) IF ^ IS NOT WORKING, try running `jekyll build` and see what happens. If there are any specific errors, try also running this: `gem install jekyll bundler` and see if it helps. Or contact me!
4. View your website at http://127.0.0.1:4000/
5. Commit any changes and push everything to the master branch of your GitHub user repository. GitHub Pages will then rebuild and serve your website.

## Check out the config file for some of the "variables" that are used throughout the site
The _config.yml file has the site name, description, avatar and lots of other details. Most of these "settings" are used as variables throughout the site so make sure they are up-to-date. 

Making a change to _config.yml (or any file in your repository) will force GitHub Pages to rebuild your site with jekyll. Your rebuilt site will be viewable a few seconds later at <https://yourgithubusername.github.io> - if not, give it ten minutes as GitHub suggests and it'll appear soon. 

**Important Note:** Don't change anything in the _site folder. This is where jekyll builds everything and stores the frontend of the site. All changes can be made outside of this folder and it will automatically get updated.

### IF CHANGES ARE MADE TO THE _config file:
Run the command `jekyll build` and then `jekyll serve` (for this to work, follow all instructions under "Local Development" above).

## Adding Pages
To add a new page, look at the existing pages .md for reference (ex. resources.md, sponsors.md, etc.) Create a new .md (markdown) document in the repo folder and follow the proper heading format. (the dashed lines) Then, go into **default.html** and add a new line of code linking to the new page in the navbar to account for the new page. 


## More about Jekyll's cool structure
Jekyll is kinda like a MUCH simpler version of React where there are different components that you can build out and "place" into other components using placeholders.
### For example, look at the default.html file
Everything builds off of this file. It has the nav bar and header, and if you go down to the "main" section, there's a variable for {{ content }}.
### Now go to the page.html file
At the top, it says the layout is "default". This means that all of the html here is embedded into the default.html file where it says {{ content }}.
This is why every new .md page has to have the **layout: page** at the top. So all the page's content can easily embed into the parent html.

## Guidance for the Event page + Calendar feature:
Because of Jekyll's cool hierarchical format (explained above), it's great for quickly/easily adding/updating blog posts, event posts, basically anything that follows a consistent format and that you'll probably add a lot of.

### See the _posts folder? 
If you look in that, you can see its markdown files with the similar dashed lines at the top. They follow the _posts layout are like blog posts that you can quickly write and just add to the folder. 

For events, I added this code to the config file: 

#adding event posts
collections:
  events:
    output: true

and added the _events folder where we can add all of our events. The layout of these files would be "event," which means **we need to flesh out the event.html layout** I added to the layouts folder. In the event .md files, we can also add additional "variables" like category, date, tags, etc. in the dotted line area and then use them in out event.html layout by calling {{ page.category }} or {{ page.date }}.

IF we add a separate events page to the navbar to display and link all the events, we can iterate through them like this:

 {% for post in site.events limit:10 %}
    {% if post.category == 'general' %} <- We can even add if statements like this!
    <div class="row col-lg-23 full-span">
        {{ post.title }}
        <date class="blog-list-date">{{ post.date | date: "%b %e, %Y" }}</date>
        some other html etc. 
    </div>
    {% endif %}
{% endfor %}


## Next Steps
Features to add:
- Add Events + Calendar
- Photo gallery
- Add a guest blog section
- Add a Contact Us form
- Add a Join Newsletter feature in the footer

## Credits

- Barry Clark's Jekyll Theme: [jekyll-now](https://github.com/barryclark/jekyll-now/)

Barry Clark's more walkthrough, [**Build A Blog With Jekyll And GitHub Pages**](http://www.smashingmagazine.com/2014/08/01/build-blog-jekyll-github-pages/) over at the Smashing Magazine website. Check it out if you'd like a more detailed walkthrough and some background on Jekyll. :metal:

It covers:

- A more detailed walkthrough of setting up your Jekyll blog
- Common issues that you might encounter while using Jekyll
- Importing from Wordpress, using your own domain name, and blogging in your favorite editor
- Theming in Jekyll, with Liquid templating examples
- A quick look at Jekyll 2.0’s new features, including Sass/Coffeescript support and Collections
