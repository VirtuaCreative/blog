---
layout: post
title: How to publish your website on GitHub
categories: [github, github pages, tutorials in English]
tags: [github, free hosting, github tutorials]
published: True
imageUrl: https://goo.gl/i4GnJn
fb_title: How to publish your website on GitHub
language: [en_US, en_GB]
author_twitter: xmdramos
image: http://goo.gl/TaiHua
image_schema: 'http://farm1.staticflickr.com//701//21720695025_f483d1dd95_b.jpg'
author: Marcia Ramos
comments: true
fb_type: article
meta_keywords: github, free hosting, tutorials github, github pages, github user website, github organization website, websites, create free website, free website
authorUrl: https://plus.google.com/+MarciaDiasRamosMD/
date_update: 2015-09-27 09:16:13 UTC
date: 2015-09-26 02:22:34 UTC
author_fb: marciaramosmdr
fb_section: Tutorials - GitHub
description: Learn how to create your own website hosting it on GitHub for free!
---

# **GitHub**

[GitHub] is a social network for programmers and developers, which is used for sharing their codes and contribute to others'. Furthermore, it can be used for **hosting websites for free**!

<br/>

## **Conditions for hosting websites** 

In order to publish your website with [GitHub Pages][], you must be aware of a few things:

1. **First**: your source code is going to be public, so everyone with internet connection will be able to see it.

2. **Second**: your website pages must be written in static html, css and javascript. Server language based websites, as php, are not supported by GitHub for security purposes. Also, you cannot use a database, so you will not have registered users, for example.

3. **Third**: you can use GitHub sub-domains (always **username**.github.io) or your own domain name (like **mydomain**.com).

<br/>

## **Undestanding GitHub Pages**

[GitHub Pages] is a GitHub feature that allows us to use it like a hosting provider. You can have basically two types of websites:

1. **User or Organization Websites**
2. **Project Websites**

Their permissions and features are the same, there is no difference on their base structure to host websites. But there are a few things different when you set them up.

<br/>

### **<mkp-blue>User and Organization Websites</mkp-blue>**

These websites are based on `master` branches of GitHub repositories and they will have this default URL throughout GitHub: `http://username.github.io`, where `username`, of course, is your username. 

They are build **automatically** when you create a new repository named exactly by: `username.github.io`. That's it, no letter can be changed, otherwise your website is NOT going to be build by GitHub.

There is actually no difference between user and organization websites. If your account is personal, GitHub will built your website exactly the same as if you have an organization account. There are a lot of differences between those accounts, but not for building websites purposes.

<br/>

### **<mkp-blue>Project Websites</mkp-blue>**

Project websites have the same rules in order to exist on GitHub as User or Organization websites. Their main differences are:

- :arrow_right: They live in `gh-pages` branches - not in `master`'s
- :arrow_right: They will be accessed by this default url: `http://username.github.io/repositoryname` - not `http://username.github.io`
- :arrow_right: You can create as many project websites as you want. But each GitHub account can have one user/organization website only (`username.github.io`). You don't need an user or organization website in order to create a project website itself. They can be linked, of course, but just if you want they to.

<br/>

### **<mkp-blue>Practical Examples</mkp-blue>**

1. **User/Organization websites**:
Our account @virtuacreative has one user website at [http://virtuacreative.github.io](http://virtuacreative.github.io), which lives in a specific repository, called `virtuacreative.github.io`. 

2. **Project websites**:
We also have two other project websites, and they live in their own repositories. 
  2.1. One of them is this Blog ([http://virtuacreative.github.io/blog/](http://virtuacreative.github.io/blog/)), which lives in its repository called `blog`. 
  2.2. The other is Git ([http://virtuacreative.github.io/git/](http://virtuacreative.github.io/git/)), a website we have build for demonstration purposes, and it lives in its own repository, called `git`.

Note that all of them are part of the same sub-domain `virtuacreative.github.io`, but as they live in different repositories, their structure doesn't need to be the same, and in fact they aren't! 

I suggest you check [GitHub Help Guide][] if you need more information concerning this matter.

If you wish to use your own domain name, please follow GitHub guides from [here][], as this topic is not going to be discussed on this article. 

<br/>

-----------------------

# **How to create your User/Organization website**

<br/>

It is quite simple. Please click on the following frame if you wish to **watch our video tutorial** for this purpose. If you'd rather read the tutorial, it's right below.

<br/>

<div class="iframe_container" itemprop="video" itemscope="" itemtype="http://schema.org/VideoObject">
	<iframe width="853" height="480" src="http://www.youtube.com/embed/E-ONNjFoOx0" frameborder="0" allowfullscreen="allowfullscreen"> </iframe> 
	<meta itemprop="contentURL" content="https://youtu.be/E-ONNjFoOx0" />
  	<meta itemprop="embedURL" content="http://www.youtube.com/embed/E-ONNjFoOx0" />
  	<meta itemprop="thumbnailUrl" content="{{ site.data.url.gitlab.youtube_thumbs }}/publish-website-github-EN_GB.jpg" />
  	<meta itemprop="name" content="How to publish your website on GitHub" />
  	<meta itemprop="description" content="Learn how to create your own website hosting it on GitHub for free!" />
  	<meta itemprop="duration" content="T3M07S" />
  	<meta itemprop="uploadDate" content="{{ page.date | date_to_xmlschema }}" />
</div>

<br/>

#### **<mkp-blue>Step by Step Tutorial</mkp-blue>**

1. Go to [https://github.com](https://github.com) and create your account or sign in if you already have one.

2. Create a new repository.
  2.1. Name your repository by typing on the text box, exactly: `username.github.io` (where `username` is your username).
  PS.: As you see your username beside the text box, you tend to type `.github.io` only. DO NOT DO THAT! You need to repeat your username, and your repository will have this odd name `username.github.io`.
  2.2. If you are willing to use Jekyll for writing your website, you can add a default `gitignore` just when you are creating your repository. You don't need to add it at this point, you can add it afterwards; it's up to you.
  2.3. You can add a README file at this point too - so you can describe what is the purpose to this repository in order to inform other GitHub users. But again, it's up to you.

3. After creating your repository, go to `settings` and there you will be able to see if everything worked as it was supposed to. If it's all right, you will see this warning: <strong>"Your site is published at http:// username.github.io"</strong>.
  3.1. At this point, you can click on <strong>"Launch automatic page generator"</strong> button, so GitHub will create an index file to your website. If you follow their steps, you can easily customize your content, based on one of their templates. So, if you aren't interested in designing your website, you can pick one of their templates and develop your content as you wish.

4. Let's say you are not interested in following the previous 3.1 step and you want to develop and design your website according to your needs. Click on `username.github.io` to go back to your repository. 

5. Click on the PLUS `+` sign to create your `index.html` file and type it in the text box.

6. Copy and paste your content from a file you might have ready to go. Or, write your content directly on the textarea provided by GitHub.

7. Commit your new file: if you are new to GitHub, you need to know that every time you add something or change something, you need to `commit` it. It is their way to **save your file** and track exactly what are you doing at that moment. For doing this, you will need to add a short description to tell yourself and other users and contributors what that act means. You can also add a long description, but it is not required.

8. That's it! Your website's Home Page already exists at `http://username.github.io`.

Please, if you got lost on reading those steps, please watch our video tutorial (posted above) to make it more clear. 

<br/>

## **Further steps**

<br/>

### **<mkp-blue>How to create a folder to your css styles or javascript files</mkp-blue>**

**The following steps can be found on the same video tutorial posted above.**

1. Sign in and go to your repository.

2. Click on the plus sign, as you do to add a new file.

3. Instead of typing the new file name, type the name of the folder you wish to create. After typing the folder name, add a slash `/` at the end, like, for example: `css/`.

4. There we go! You will see that now you will have the text box moved to the end of the path. 

5. Type your file name in the text box, for example `styles.css`.

6. Add your content and commit your file.

7. That's it. We are done!

Note that **you CANNOT create an empty folder**. Every time you create a folder you will need to add a file to it.

<br/>

### **<mkp-blue>How to add images folder</mkp-blue>**

This option is not possible via web platform, as far as I'm aware of. So, you will need to do that via command line or via [GitHub Desktop][] application.

Let's say you are not used to the command line way to work, so let's keep it easy for any user, programmer or not.

Please click on the following frame if you wish to **watch our video tutorial** for this purpose. If you'd rather read the step-by-step tutorial, it's right below.

<br/>

<div class="iframe_container" itemprop="video" itemscope="" itemtype="http://schema.org/VideoObject">
	<iframe width="853" height="480" src="http://www.youtube.com/embed/fayd6VWdzmU" frameborder="0" allowfullscreen="allowfullscreen"> </iframe> 
	<meta itemprop="contentURL" content="https://youtu.be/fayd6VWdzmU" />
  	<meta itemprop="embedURL" content="http://www.youtube.com/embed/fayd6VWdzmU" />
  	<meta itemprop="thumbnailUrl" content="{{ site.data.url.gitlab.youtube_thumbs }}/add-img-folder-git-english.jpg " />
  	<meta itemprop="name" content="How to add images folder to your website on GitHub" />
  	<meta itemprop="description" content="Learn how to add images folder to your website hosted on GitHub" />
  	<meta itemprop="duration" content="T3M11S" />
  	<meta itemprop="uploadDate" content="{{ page.date | date_to_xmlschema }}" />
</div>

<br/>

#### **<mkp-blue>Step by Step Tutorial</mkp-blue>**

1. Download and install [GitHub Desktop][] application to your PC or MAC.

2. Open the app and sign in to your account.

3. Clone your repository to your desktop.

4. Open the folder created in your computer - which is exactly the same as your repository on GitHub.

5. Inside your repository folder - on your computer, create a new folder and add to it the images you want to.

6. Go back to the app. You will be notified that there were changes made to your repository.

7. Commit your changes and sync your app with GitHub.

8. There we go! Your images are going to be uploaded to GitHub exactly as you did it on your computer.

<br/>

# **How to create Project Websites**

<br/>

Read the full tutorial and watch the video on the article **[How to publish Project Websites on GitHub][]**

That's all for now folks! I hope this article were useful for you! :smiley:

<br/>

--------------

#### **<mkp-blue>Stay tuned!</mkp-blue>** 

<br/>

Subscribe to our new **[YouTube Channel][]**!

Follow us on [Twitter][]!

Add our [Blog][] to your [news feed]!



[YouTube Channel]: http://www.youtube.com/c/VirtuaCreativeBrWebsites 
[Twitter]: https://twitter.com/virtuacreative
[Blog]: http://virtuacreative.github.io/blog/
[GitHub Desktop]: https://desktop.github.com/
[GitHub]: https://github.com
[GitHub Help Guide]: https://help.github.com/articles/user-organization-and-project-pages/
[news feed]: http://virtuacreative.github.io/blog/feed.xml
[GitHub Pages]: https://pages.github.com/
[here]: https://help.github.com/articles/setting-up-a-custom-domain-with-github-pages/
[How to publish Project Websites on GitHub]: {{ site.data.url.virtua.blog }}github-pages-project-website.html