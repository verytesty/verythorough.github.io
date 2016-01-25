---
title: One VM to Rule Them All
published: false
---



Sometimes it's easier to test sites on a unix variant than on Windows, but creating a VM for every project takes up more space than I have room for.  Today I created a Vagrant-DevBox directory in my user folder, and set up a Vagrantfile to make my VM work with multiple projects in my GitHub folder.  The configuration is pretty simple:

    Vagrant.configure(2) do |config|
      #Shared with PHC VM, saving space (i.e., don't change)
      config.vm.box = "trusty64"

      #Forward ports as required by project
      #Localhost port for jekyll serve, used for opensmc and others
      config.vm.network "forwarded_port", guest: 4000, host: 4040

      #Localhost port for rails server, might be used for wwc?
      config.vm.network "forwarded_port", guest: 3000, host: 3030

      #Create synced folders mapped to local repos
      config.vm.synced_folder "../Documents/GitHub/", "~/GitHub"
    end

Later, I hope to move my current Python Hack Club project (which is set to run via apache on a separate VM) as well as any WordPress testing I do in the future.  I'm looking forward to simplified command-line work without too huge a storage cost.

OK, installing is more work than I expected!  I already tried once and hit a bunch of problems.  Then I destroyed the vm to start over.  Here's a few notes I'm learning along the way:
- To log in to vagrant's vm as root, do `vagrant ssh` as usual, then run `su -` and enter the password (default "vagrant"). The username will then be `root@vagrant-ubuntu-trusty-64`.
- To return to the regular vagrant user from root, run `exit`.
- Digital Ocean has a [nice tutorial](https://www.digitalocean.com/community/tutorials/how-to-install-ruby-on-rails-with-rbenv-on-ubuntu-14-04) for installing Ruby and Rails via rbenv, which is apparently preferable to rvm.
- After following those directions through the ruby (2.2.3) and bundler installs, verythorough.github.io `bundle install`ed without a hitch.  (Oh, I also rean `sudo apt-get install nodejs` before that, but I don't think that made a difference.) All that beautiful green text... :)
  - After running `bundle exec jekyll serve`, I navigated on my local machine to localhost:4040, and there was my site.  Port forwarding: check.
