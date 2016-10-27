---
layout: post
published: false
permalink: ""
title: VM in the Cloud
---

In the WWCode Silicon Valley Slack team, someone asked about cloud-based pair programming tools.  I remembered [cloud9](http://c9.io), which it turns out met her needs, but as I re-looked at it, I realized it may meet some of my current needs, too.

I might be able to use it to solve my VM problem.  Rather than "one VM to rule them all," maybe it's better to have many, floating in the cloud.  Integration with GitHub makes it easy, but I can also start totally new workspaces from bare (Ubuntu) linux or premade dev kits for WordPress, Node, Rails, etc.

I tried cloning this (github pages jekyll site) repo, and I went from clone to `bundle exec jekyll serve` in no time.  The c9 interface gave me a warning that I'd need to add [extra parameters](https://docs.c9.io/docs/jekyll) if I wanted to actually see what I was serving.  Following that, I just ran `bundle exec jekyll serve --port $PORT` and the interface popped up a link for viewing the site.

For the OpenSMC jekyll site, my initial `bundle install` failed because the default ruby version, 2.3.0, didn't match the repo's required 2.2.2.  c9 advised me that the workspace had rvm installed, so I ran `rvm install 2.2.2`, waited about 30 seconds (sooo much quicker than rbenv installing on my local vm!), and ran `rvm use 2.2.2`.  After that, just `gem install bundler`, and the rest as usual.  To avoid specifying the version number every time in the future, I ran `rvm use --default 2.2.2`.  For future reference, I found a simple rvm cheatsheet [here](http://cheat.errtheblog.com/s/rvm).

Turning to the WWCode site, it's on Ruby 2.2.2 as well, so I followed the same procedure as above to get bundler working, and it was fine.  (Speaking of bundler, I also learned a little about the difference between `bundle install` and `bundle update`, and that I should usually do `bundle update` on shared repo projects.  More info [here](https://viget.com/extend/bundler-best-practices).)  I'm still not done getting this site running though--need to attempt the Postgres install, and get Rails going. (c9 docs for that [here](https://docs.c9.io/docs/running-a-rails-app).)  I'm also wondering about environment variables, and found [some](http://blog.honeybadger.io/ruby-guide-environment-variables/) [articles](http://railsapps.github.io/rails-environment-variables.html) about using Figaro for this, which is already in the repo's gemfile.  More notes on that one next time!

Final note, I just chuckled at the little tagline shown during a c9 loading screen: "literally makes your laptop cooler."  It's funny 'cause it's true....
