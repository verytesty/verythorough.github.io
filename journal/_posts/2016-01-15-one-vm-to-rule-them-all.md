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
