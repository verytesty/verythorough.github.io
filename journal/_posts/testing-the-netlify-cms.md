---
title: Testing the Netlify CMS
date: 2017-01-26T22:23:41.990Z
---

I’m preparing to write some documentation for the Netlify CMS, so I’m trying it out on my own Jekyll site. Right now, I’m testing the UI a little, but mostly curious to see what happens with saves, etc.—in other words, what git commands execute when I save, etc. Checking my settings at the moment, I don’t have the editorial workflow enabled, so I think maybe when I save, it will create and save the doc, commit, and push to master all at once. Let’s see!

Now I’m testing the editorial workflow. Saving a draft makes a commit to a new branch, named for the post. Editing the draft adds a commit to the same branch. Dragging the entry from Drafts to Waiting for Review opens a pull request. Editing after this adds more commits to the same PR’d branch.