---
layout: post
title: The start of my website project.
tag: website-project-post
date: 2017-07-03 2:38:11
---
This is officially the first non-test post on my website.

After trying a lot of different frameworks (react, bootstrap, django, HTML5 Boilerplate) I finally settled on Jekyll. Here's why.

1. The main reason why I decided to use Jekyll for my website project is because it's a static page generator. I'm not really trying to build a webapp, so while framworks such as django and react are feature packed, using them for a small personal website would just lead to a bloated site. Jekyll is also faster than these alternatives, as the html is pre-generated.

2. The secondary reason I decided to use Jekyll over something like just writing a site from scratch with CSS and HTML or a Boilerplate template is because Jekyll makes it really easy for me to update my site. Instead of having to edit HTML and CSS whenever I want to add something to the site, I can just add a seperate markdown file. Being able to write new posts without actually writing new code is going to be nice in the long run.

Setting up this site definitely was not as easy as I thought it would be. For one, Jekyll is only with unix, so to get it to work on my windows laptop, I had to setup a bash shell before I could even get started. Then, I had some issues with package dependencies and a really difficult time troubleshooting paginate features, but I've been testing the site for a while and I think it's finally about where I want it to be. 

I decided on a template called [pixyll](https://github.com/johnotander/pixyll) to use for the site. I mainly like its clean minimalistic design. There's a few CSS styling aspects I might want to change, such as darkening the navbar a little and maybe applying a color gradient, but nothing too major.

I still have to figure out how I'm going to host this website. I'm probably going to just host it on github sites for free as a personal page, but I might use AWS. We'll see. Well, I guess I'll see, since nobody else will be reading this untill after I have the hosting figured out.