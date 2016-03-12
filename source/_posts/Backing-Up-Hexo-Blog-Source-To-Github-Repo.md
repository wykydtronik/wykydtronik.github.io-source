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