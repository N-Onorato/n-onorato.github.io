---
layout: post
title:  "First Post!"
date:   2023-01-29 09:39:18 +0000
categories: anecdote
---

Hello...

Seeing as this is the first post, I thought I'd go over my experience setting this blog up. Initially I didn't choose Github Pages but _GitLab_ pages. Which initially went very well, you create a new project and it provides a template for Jekyll (the site generator I'm using) which should make everything easy. Unfortunately parts of the template were out of date, it wanted me to change gitlab settings that were either already set correctly or didn't exist.

But I was able to get the deployment pipeline running only to find the site didn't have any CSS. The readme on the Jekyll template included "troubleshooting" about this. But only really said "your project configuration might need to change" which was pretty useless. I also couldn't enable https because I was using the default subdomain for GitLab and it doesn't seem to support lets-encrypt. Even though there's an issue for it that is 4 years old. That was discouraging to see, so I abandoned Gitlab as a platform.

In contrast Github pages was very simple to setup. I just created the repo, opened a codespace, and found a github actions template for deploying Jekyll. The only issues I did run into were that in the codespace I initialized jekyll with a new project which created a new directory. That wasn't what the default deployment pipeline was expecting so that didn't work. But moving the project out of that directory solved that. Secondly, I received a version error where two versions were incompatible. Fixing that was as simple as bumping the ruby version from 3.0 to 3.1 and incrementing a number to invalidate github's cache (there was a doc string that explained this). 

After those two things the site has been deploying smoothly, albeit with some warning messages that I'll have to look at in the future. But github pages also has https out of the box which is nice.
