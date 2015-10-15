---
layout: post
title: "Jekyll, Pages & Prose"
---
While researching the quickest way to get a new Jekyll blog up and running, I came across several tools and tutorials detailing exactly what I was looking for (see references below). As I began to dig into each one, however, I was bothered by unnecessary features, files, semantics, etc. [Sturgeon’s law](https://en.wikipedia.org/wiki/Sturgeon%27s_law) in full effect. So I decided to write this, my own tutorial on using vanilla [Jekyll](https://jekyllrb.com), [GitHub Pages](https://pages.github.com), and [Prose.io](http://prose.io) to quickly create, host, and manage a static site for free … AKA Best Blog Ever.

These instructions are for Terminal on a Mac.

## Vanilla Jekyll

First, we need a non-system version of Ruby and the same version of Jekyll that GitHub uses.

[Complete the first 4 steps here](https://github.com/sstephenson/rbenv/#basic-github-checkout) to install rbenv.

Next, `git clone https://github.com/sstephenson/ruby-build.git ~/.rbenv/plugins/ruby-build && rbenv install 2.2.3 && rbenv global 2.2.3`.

You now have Ruby.

In a new terminal tab, `gem install bundler && echo -e "source 'https://rubygems.org'\ngem 'github-pages'" >> Gemfile && bundle install`.

You now have Jekyll.

Start a new Jekyll project with `jekyll new project-name` where `project-name` is name of your project. This will generate all the files and folders Jekyll needs to build your site.

Test to see if everything worked with `cd project-name && jekyll serve`. In a new terminal tab, `open http://localhost:4000`. We needed a new tab because `jekyll serve` is a blocking process that will continue running until you cancel it with `Ctrl+C`.

## GitHub Pages

Now we need to turn our vanilla Jekyll project into a git repo and push it up to GitHub. If you haven’t already, [create a GitHub account](https://github.com/join) and [configure your SSH keys](https://help.github.com/articles/generating-ssh-keys).

Create a new repo on GitHub, and **do not** initialize with a README. On the right side of the next screen, copy the SSH clone URL that looks like `git@github.com:username/project-name.git`.

From our Jekyll project directory, `git init && git add . && git commit -m 'Install vanilla Jekyll' && git remote add origin PASTE_HERE && git branch -m gh-pages && git push -u origin gh-pages` where `PASTE_HERE` is the SSH clone URL you just copied.

You just deployed your site.

In the background, GitHub is running the Jekyll build process to compile and serve your site. After 20 seconds, your site should be available at `http://username.github.io/project-name`.

If you want to push to your `username.github.io` instead of a project site, the previous command should be `git init && git add . && git commit -m 'Install vanilla Jekyll' && git remote add origin PASTE_HERE && git push -u origin master`.

> Protip: I keep my blog in a separate project repo so I can manage and deploy this content independently of my home page and other microsites.

## Prose.io

Ok, we now have our vanilla Jekyll project hosted on GitHub. It’s time to introduce our clever content management system.

`open http://prose.io`, then click through to **Authorize on GitHub**.

Now `open http://prose.io/#username/project-name`. You should see your Jekyll project files and folders. Click **_posts**, then click **New File**.

Use the [markdown](https://help.github.com/categories/writing-on-github) editor to create a new post and format it however you’d like. Click the **disk icon** on the right, then click **Submit Change Request**.

Boom. That’s it!

You can follow this same workflow indefinitely to create new files and edit existing ones to build up your site content.

## Now What?

At this point, you may be wondering how to use something other than the default template or how to add commenting or analytics. I will write about these things as I get to them myself, but for now, I will recommend some good starting points:

#### Analytics

- [Improving the quality of Google Analytics data for Jekyll sites](http://veithen.github.io/2015/01/05/jekyll-improving-ga-data-quality.html)
- [New Plugin Brings Google Analytics Data to Jekyll Sites](https://developmentseed.org/blog/google-analytics-jekyll-plugin)

#### Comments

- [Jekyll Installation Instructions — help.disqus.com](https://help.disqus.com/customer/portal/articles/472138-jekyll-installation-instructions)
- [Adding Disqus to your Jekyll](http://www.perfectlyrandom.org/2014/06/29/adding-disqus-to-your-jekyll-powered-github-pages)

#### Theming

- [Jekyll Documentation](http://jekyllrb.com/docs/home)
- [Jekyll From Scratch - Getting Started](http://pixelcog.com/blog/2013/jekyll-from-scratch-introduction)

> Protip: Write 10 posts, then share with 100 people you know and 1,000 people you don’t before worrying about what it looks like.

As the real [Drew Wilson](http://drewwilson.com) would say, _Go Forth and Build_.

## References

- [Using Jekyll with Pages — help.github.com](https://help.github.com/articles/using-jekyll-with-pages)
- [Poole · The Jekyll Butler — Mark Otto (creator of Bootstrap)](http://getpoole.com)
- [How I Created a Beautiful and Minimal Blog Using Jekyll, Github Pages, and poole](http://joshualande.com/jekyll-github-pages-poole)
- [Incorporated — Kippt Inc.](http://incorporated.sendtoinc.com)
- [Save 50 Hours Setting Up Your Jekyll Blog — Will Koehler](http://willkoehler.net/2014/08/26/save-50-hours-setting-up-your-jekyll-blog.html)
- [Simple Category Pages with Vanilla Jekyll](http://primalivet.com/2013/11/simple-category-pages-with-vanilla-jekyll)
- [github.com/jekyll/jekyll/wiki/Themes](https://github.com/jekyll/jekyll/wiki/Themes)
- [Jekyll Themes — Michael Rose](https://mademistakes.com/work/jekyll-themes)