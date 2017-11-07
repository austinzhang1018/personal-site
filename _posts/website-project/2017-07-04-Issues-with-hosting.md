---
layout: post
title: Issues with hosting
category: website-project-post
date: 2017-07-04 12:55:11
---
So I ran into a minor (pretty major) issue today. I had originally planned to use GitHub sites to host my website. Jekyll, the framework I'm using to generate this site is developed by the founder of Github, and as a result, GitHub supports Jekyll with some additional features. By using GitHub sites, all one has to do to deploy their Jekyll website is add a repository with their Jekyll code, and enable GitHub sites. GitHub takes care of building and deploying your site, which means you can even edit your site online through GitHub's text editor without downloading and pushing your code. However, since GitHub is building and deploying your site, you have to make sure all the plugins you are using are supported by GitHub's build platform.

This is what's causing my hosting issues.

I did a test launch on GitHub sites and I noticed some of the HTML generate was different from what I had locally. I realized that this was because I'm using the Jekyll-paginate-v2 plugin, not the original Jekyll-paginate plugin. Unfortunately, I actually need the paginate-v2 plugin, since the original plugin is very restrictive and only allows you to have one paginate page whereas I would like a paginate page for each project I'm working on.

I think I have two options going forward.

1. I can try to see if I can still use GitHub sites to host my site, and just not take advantage of their auto-build and deploy feature.
2. I can use a different hosting service.

I'm not sure what I'll do yet, but I'm going to start looking into some other hosting services and compare them to Github's.

Oh yeah, I also need a domain name. austinzhang.com is taken, but austinzhang.io and austinmzhang.com are open. I still need to decide.