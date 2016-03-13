---
title: Backing Up Hexo Blog Source To Github Repo
date: 2016-03-12 14:06:41
tags:
---

Since documentation doesn't really cover this, I thought I'd just make note of this. If you want to prevent your Hexo blog for disappearing off the face of the planet, don't keep it in one place. In my case, I've had Octopress blogs die because my Octopress source went MIA when my SSD died. Since I also spend most my time on my desktop, having Hexo only on my laptop would be inconveniant. Time to break things.

``` bash
$ cd ~/github/kaichi.github.io
$ git init
$ git add .
$ git commit -m "putting hexo blog source on github"
$ git remote add origin git@github.com:kaichi/kaichi.github.io-source.git
$ git push -u origin source

```

Basically what you'll want to do is have a repository for your hexo deployment and one for your source. Atleast this way, if I need to clone the source repository to my desktop I can grab it on the fly. Always commit!

I've ran into issues when cloning my source to my desktop. I wasn't sure how this would go about since npm places dependencies inside the hexo blog folder. I ran into a few road blocks, but I believe this is how to go about it.

## Clone Your Hexo Blog Source From Git

First cd to your directory and clone the source.

``` bash
$ cd C:\github
$ git clone git@github.com:kaichi/kaichi.github.io-source.git
```

## Copy _config.yml To Desktop

After cloning your hexo blog source, cut _config.yml and paste it to your desktop. We will need this later. Backup package.json if you want, it will get overwritten. You will need to install your dependencies in the next few steps to setup the hexo environment. 

## Hexo Init & Install Hexo Deployer Git

Assuming you already have node.js and hexo installed on your second machine (in my case, my desktop) proceed to initiate hexo over your cloned source.

``` bash
$ cd c:\github\
$ hexo init kaichi.github.io-source
```

After that's said and done, go to your desktop and copy _config.yml and paste it over the default one init placed in your environment.

Next let's get the deployer installed.

``` bash
$ hexo install hexo-deployer-git --save
```

Don't forget about the --save flag, I completely derped out and couldn't deploy my blog and noticed it wasn't even installed.

## I Think We're In The Clear

Now you should be able to generate and deploy your hexo blog. Keep in mind, I am using Git Shell specifically because I don't want to juggle and mess with ssh keys. 

``` bash
$ hexo generate
$ hexo deploy
```

Everything should deploy fine, check your github page to see if it's broken. It might take a second to update. Worse comes to worse, it's broken and you can just redeploy from your first workstation, or in my case my laptop. Now it's time to see if I can push my local source and get this writeup to update on my laptop without exploding...

# Merging Conflicts...

Things are exploding... putting package.json in .gitignore... -update from laptop

I keep running into issues with package.json... First I noticed that package.json has a few conflicts between the two environments with versions / dependancies. I removed it from the repo and added it to .gitignore. Now when I pulled from laptop and desktop it would delete the local package.json. Perhaps from the very beginning I should have added package.json to the .gitignore folder.