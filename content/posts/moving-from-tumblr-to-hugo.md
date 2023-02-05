---
title: "Moving from tumblr to hugo"
date: 2023-02-05T15:42:43+01:00
tags: 
  - tutorial
  - hugo
  - tumblr
---

In 2015 I stop to post in Tumblr I don't remember why, but there are still some posts I will love to keep, and one of my new year's resolution is to get back blogging.

I don't want to use Tumblr, I'm really into using MarkDown everywhere so Hugo seems the better option to mix both things, blogging and MarkDown.

So the first thing seems obvious, migrate the old posts to hugo. It seems an easy thing after [checking hugo's documentation](https://gohugo.io/tools/migrations/#tumblr) there are 3 tools doing the work, what could go wrong? 

I will spolier you, none of them works, only tumblr-importer does some part of the job but requieres the use of a template that supports its tags, and suprise not even the example provided works. So after expending a lot of time testing all of them, generating an API key, cursing and trying to fix python 2 code I came across a different path to solve the thing.

Jekyll **did** a pretty decent work importing from Tumblr so seems it might work importing from Tumblr to Jekyell and them to Hugo, what could go wrong?

Doing the long history short, it works but it was a nice feature that worked some time ago, now it is not working, so you have to use a old version of Jekyll for the conversion. As this a pretty old it is better to run it in docker.

So the step by step guide to move your Tumblr posts to hugo via Jekyll is as follows:

First create a temporary directory :)

```
mkdir ~/workspace/blog/import
cd ~/workspace/blog/import
```

now run spin up a docker container with Jekyll

```
docker run -ti -v $(pwd):/code --entrypoint=/bin/sh jekyll/jekyll:3.8

```

now you are in the container, importer is not installed in the container so you have to manually install it.

```
gem install jekyll-import

```

now you can "import" into Jekyll your old blog, note that you don't need any API key so an extra point for Jekyll devs. Remember to change the url for your own or you will import my blog :P

```
jekyll import tumblr --url https://millaguie-blog.tumblr.com --format md --grab_images --add_highlights --rewrite_urls

```

Now you can exit the container, you have all your content in Jekyll format. 
Luckly the [importers from Jekyll](https://gohugo.io/tools/migrations/#jekyll) work pretty well.

I used *ConvertToHugo* because it was the first I tested, and it worked so just clone the code in your work environment and call it.
It is python 3, so you will probably be able to run on your own local python installation

```
cd ..
git clone https://github.com/coderzh/ConvertToHugo.git
cd import
python ../ConvertToHugo/ConvertToHugo.py _posts toImport
```

now you can just drop the content of the toImport directory in your hugo directory and voilà, you have your old posts in your brand new Hugo.

## Related readings

* [Hugo quick start](https://gohugo.io/getting-started/quick-start/)