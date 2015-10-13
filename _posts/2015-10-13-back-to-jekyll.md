---
layout: post
title: "Back to Jekyll"
---
I started programming in [Ruby](https://ruby-lang.org) back in 2009 due to heavy influence from [37signals](http://37signals.com/manifesto) (now [Basecamp](https://basecamp.com)) and the [Rails community](http://rubyonrails.org). The [convention over configuration](https://en.wikipedia.org/wiki/Convention_over_configuration) paradigm was like a deep breath of fresh air and was somewhat radical for a typical [LAMP stack](https://en.wikipedia.org/wiki/LAMP_(software_bundle)) developer. Being exposed to dependency management with gems, automation with [Rake](https://github.com/ruby/rake), deployment with [Capistrano](http://capistranorb.com), and REST with [Sinatra](http://sinatrarb.com) completely changed the way I looked at development. Oh, and there was this other neat tool called [Jekyll](https://jekyllrb.com) that allowed me to generate static sites! Sweet.

Over the next couple years, I learned the Javascript community was doing—er, borrowing—all these same things, and since I already had a long history with Javascript, it made sense for me to embrace it. To make a long story short, I stopped using Jekyll when I started using a static site generator written in [node](https://nodejs.org). There was [Blacksmith](https://github.com/flatiron/blacksmith) then [Wintersmith](http://wintersmith.io) then [Assemble](http://assemble.io) and now [Hexo](https://hexo.io). (Also [Cactus](http://cactusformac.com)). All of these did basically the same thing as Jekyll, but because they were written in node, I thought I should enforce a homogeneous development workflow.

The other day, it finally dawned on me. **[Github Pages has native support for Jekyll.](https://help.github.com/articles/using-jekyll-with-pages)** Sure, I could manually deploy with any of these node tools using [grunt-gh-pages](https://github.com/tschaub/grunt-gh-pages), but I was missing out on the beauty of Github’s automated build hooks and support for clever integrations like [Prose](http://prose.io). I can now set up a simple site or blog very quickly and have a non-developer maintain it. Some good examples are this personal blog and the [family blog](http://mattmeg.com) I just created with my wife.

[Mig](https://twitter.com/migreyes) asked me many times over the past few years, “why don’t you just use Jekyll?” and I always felt like “because Javascript” was an adequate response. As it turns out, Jekyll was the best option all along.