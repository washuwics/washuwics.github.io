
# WashU WiCS Website run by Jekyll (static site generator)
##### Instructions below by Priyanka Iyer and some of Barry Clark's original istructions

### Instructions 

Enter your site name, description, avatar and many other options by editing the _config.yml file. Most of these "settings" are used as variables throughout the site so make sure they are up-to-date. 

Making a change to _config.yml (or any file in your repository) will force GitHub Pages to rebuild your site with jekyll. Your rebuilt site will be viewable a few seconds later at <https://yourgithubusername.github.io> - if not, give it ten minutes as GitHub suggests and it'll appear soon. To view the changes locally, run the command `jekyll build`.

## Adding Pages

To add a new page, look at the existing pages for reference. Create a new .md (markdown) document in the repo folder and follow the proper heading format. Then, go into default.html and add a new line of code into the nav to account for the new page. 

<!-- ### Step 3) Publish your first blog post

Edit `/_posts/2014-3-3-Hello-World.md` to publish your first blog post. This [Markdown Cheatsheet](http://www.jekyllnow.com/Markdown-Style-Guide/) might come in handy.

![First Post](/images/first-post.png "First Post")

> You can add additional posts in the browser on GitHub.com too! Just hit the + icon in `/_posts/` to create new content. Just make sure to include the [front-matter](http://jekyllrb.com/docs/frontmatter/) block at the top of each new blog post and make sure the post's filename is in this format: year-month-day-title.md -->
## Local Development

1. Install Jekyll and plug-ins in one fell swoop. `gem install github-pages` This mirrors the plug-ins used by GitHub Pages on your local machine including Jekyll, Sass, etc.
2. Clone this repository and make sure you have access as a contributor (configure in settins on GitHub)
3. Serve the site and watch for markup/sass changes `jekyll serve`
4. View your website at http://127.0.0.1:4000/
5. Commit any changes and push everything to the master branch of your GitHub user repository. GitHub Pages will then rebuild and serve your website.

## Next Steps
Features to add:
- Add a Contact Us form
- Add a Join Newsletter feature in the footer
- Add peoples's name and links to images in the _config.yml and use variables instead of hard coding
- Having an events page that lists all upcoming events as "posts"

## Credits

- Barry Clark's Jekyll Theme: [jekyll-now](https://github.com/barryclark/jekyll-now/)

Barry Clark's more walkthrough, [**Build A Blog With Jekyll And GitHub Pages**](http://www.smashingmagazine.com/2014/08/01/build-blog-jekyll-github-pages/) over at the Smashing Magazine website. Check it out if you'd like a more detailed walkthrough and some background on Jekyll. :metal:

It covers:

- A more detailed walkthrough of setting up your Jekyll blog
- Common issues that you might encounter while using Jekyll
- Importing from Wordpress, using your own domain name, and blogging in your favorite editor
- Theming in Jekyll, with Liquid templating examples
- A quick look at Jekyll 2.0’s new features, including Sass/Coffeescript support and Collections
