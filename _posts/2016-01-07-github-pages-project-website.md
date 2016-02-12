---
layout: post
title: How to publish Project Websites on GitHub
categories: [github, github pages, tutorials in English]
tags: [github, github pages, free hosting, github tutorials]
meta_keywords: github, free hosting, tutorials github, github pages, github project website, github website, websites, create free website, free website
author: Marcia Ramos
fb_section: Tutorials - GitHub
description: Learn how to create multiple project websites hosting them on GitHub Pages for free!
image: http://goo.gl/abW5nw
imageUrl: https://goo.gl/Mrxw6b
image_schema: 'http://c2.staticflickr.com//2//1575//24207510176_1258af7c6a_h.jpg'
fb_title: How to Publish Project Websites on GitHub
fb_type: article
author_fb: marciaramosmdr
author_twitter: xmdramos
date: 2016-01-10 18:21:51 UTC
comments: true
published: true
authorUrl: https://plus.google.com/+MarciaDiasRamosMD/
language: [en_US, en_GB]
date_update: 2016-02-12 19:11:52 UTC
# copy: true # copy button with javascript
# codingbox: true # code type on the top-right of code block boxes
related: github
---

# **How to create a project website on GitHub**

<br>

## <mkp-blue> Quick overview: User/Organization Website</mkp-blue> _vs_ <mkp-blue>Project Website</mkp-blue>

<br>

When hosting your website on GitHub (it's FREE!) you'll find two primary possibilities: 

1. Create an **User** or **Organization** website - which can be accessed via `http://username.github.io` or via your own custom domain, like `http://mydomain.com`. 

2. Create a **Project Website** - which can be accessed via `http://username.github.io/projectname` or via your custom domain or subdomain. 

<br>

Note: If you are new to GitHub Pages and need a full oveview on this subject, or if you are looking for a tutorial for publishing user/organization websites, you might want to check this article out first: **[How to publish your website on GitHub](http://blog.virtuacreative.com.br/free-hosting-website-github.html)**.

<br>

<p class="bkgblue"><i class="fa fa-exclamation" style="color: red;"></i>&nbsp;&nbsp;GitHub permits ONLY <strong>ONE</strong> USER/ORG WEBSITE per account but your are allowed <strong>AS MANY PROJECT WEBSITES</strong> as you want per GitHub account!</p>

<br>

## <mkp-blue>Deciding between the options 1 and 2 above</mkp-blue>

<br>

You might ask yourself: _where should I get started then?_

The answer is: from the beginning! Just kidding :smiley: ! Well, usually we start from the first option, creating an user/org website. So you'll have our main website at this domain name: `username.github.io` and then, if you need another website, you go for the second option, as it probably will be something like a subdomain of your main domain. But this is not required, specially if you intend to use them with your own domain name. You can start by creating a project website to warm yourself up and then create a main user/org website. It's entirely up to you. 

A project website can also be useful when you want to customize a section of your website completely apart from you main website. For example, let's suppose you have an user website designed for a presentation of yourself of your business. Then you have a blog and a gallery section. You can easily have your main website as an user/organization site and two project websites to each section, blog and gallery. 

An other good use of this feature is having different websites, for completely different purposes, all hosted on GitHub with a single account.

Anyway, if you want dig a little more into this matter please read our article **[How to publish your website on GitHub](http://blog.virtuacreative.com.br/free-hosting-website-github.html)**, where we go step by step on each option and explain in details how to publish your user/organization website.

<br>

# **Setting your Project Website up**

<br>

For publishing a project website you will need to follow a few steps. Watch this video or go through the step-by-step below.

<br>

<div class="iframe_container" itemprop="video" itemscope="" itemtype="http://schema.org/VideoObject">
	<iframe width="853" height="480" src="http://www.youtube.com/embed/zWZDH9L1jMg" frameborder="0" allowfullscreen="allowfullscreen"> </iframe>
    	<meta itemprop="contentURL" content="https://youtu.be/zWZDH9L1jMg" />
      	<meta itemprop="embedURL" content="http://www.youtube.com/embed/zWZDH9L1jMg" />
      	<meta itemprop="thumbnailUrl" content="{{ site.data.url.gitlab.youtube_thumbs }}/thumb-project-websites.png" />
      	<meta itemprop="name" content="How to publish Project Websites on GitHub" />
      	<meta itemprop="description" content="Learn how to set up GitHub repositories to host multiple Project Websites for FREE!" />
      	<meta itemprop="duration" content="T4M30S" />
      	<meta itemprop="uploadDate" content="{{ page.date | date_to_xmlschema }}" />
</div>

<br>

<small>Note about this video: by the time of this screencast we had already set up our user website on GitHub to redirecting to our custom subdomain name (ramosmd.virtuacreative.com.br). When creating the new project website, GitHub redirects automatically to this previously set domain. So instead of the default GitHub Pages url (username.github.io/projectname/), we had our project redirected to subdomain.domain.com/projectname (in this case, to ramosmd.virtuacreative.com.br/blog/). </small>

<br>

## <mkp-blue>Step by Step</mkp-blue>

<br>

1. If you don't have an account on [GitHub][], create one. It's free.

2. Log into your account and create a new **public** repository. Name it as your project. For example, if you want a blog, you might want to name the repository as `blog`.

3. At this point GitHub will show you your domain name, which will be `username.github.io/blog` or instead of `blog`, it will have whatever name you'd given to the repository.

4. Create a new branch called `gh-pages` and then delete the `master` branch automatically created by GitHub.

5. Create your home page (index.html) on GitHub platform itself or upload you website content from the root folder to `gh-pages` branch (via command line or [GitHub Desktop][] application).

6. Wait a few minutes and access your new website from any web browser connected to the internet.

7. **IT'S DONE!**

<br>

<!-- <p class="bkgblue"><i class="fa fa-exclamation" style="color: red;"></i>&nbsp;&nbsp;If you want to add a <strong>custom domain name</strong> to your <strong>Project Website</strong> hosted on GitHub, please read the article <a href="#"><strong>How to Add Custom Domain Name to GitHub Website</strong></a>, where we explain how to do that.</p> -->

<br>

## <mkp-blue>Things you need to be aware of</mkp-blue>

<br>

1. [GitHub Pages][] supports **only static websites**. It means that only `html`, `css` and `javascrip` are allowed. Dynamic server-side files are **not** supported, as **php**. **Database connections** are **not** allowed either, like MySQL or MySQLi.

2. [GitHub Pages][] **does** supports CSS preprocessors like **Sass** and Scss files.

3. If you want a website written dynamically, we strongly advise you to try **[Jekyll][]** or another Static Website Generator. Jekyll is awesome to deal with, easily handled, quick to learn and fully supported by [GitHub Pages][].

4. GitHub has not a maximum storage capacity for users. That means **you can store as many files as you need** and create **as many project websites as you want**! **Awesome**, isn't it?!

5. A repository does have a [storage limit of 1 GB][], but you can create as many repos as you want. 

6. All GitHub repositories are **public** for free users' accounts. So we strongly recommend **not** uploading **sensitive information** to your repositories. By upgrading to premium accounts you'll be allowed to create private repositories, but **ALL** repos created to **hosting websites** MUST be **PUBLIC**. 


<br>

## <mkp-blue>About custom domain names</mkp-blue>

<br>

GitHub allows you to use **custom domain names** for both user/organization and project websites. You can configure as many domain names as you want when you have multiple websites. For example, if you are a web developer or a web designer, with only one GitHub account you can host unlimited numbers of websites, and you can configure a different domain or subdomain name to each website you have. 

When you configure your user/organization website for a custom domain like `mydomain.com`, if you create project websites they will be automatically redirected to `mydomain.com/projectname/`. If you want to change this, it's easily done by adding a `CNAME` file to your `gh-pages` branch (project website root), redirecting to another domain or subdomain you want.

If you need an overview for configuring your custom domain with GitHub Pages, stay tuned to Virtua Creative Blog! Our next article _"How to add custom domain to your website hosted by GitHub"_ will fully cover this subject. Follow us on [Twitter][] or subscribe to our [YouTube Channel][] for updates!

<br>

---------------

## Related Articles

<br>

<ul>

{% for art in site.data.articles.github %}
  <li>
    <a href="{{ art.url }}">- {{ art.title }}</a>
  </li>
{% endfor %}
{% for art in site.data.articles.markdown %}
  <li>
    <a href="{{ art.url }}">- {{ art.title }}</a>
  </li>
{% endfor %}


<!-- {% for post in site.related_posts limit:3 %}
{% if post.language contains 'en_US' and post.categories contains 'github' %}
	<li>
	  <a href="{{ site.baseurl }}{{ post.url }}">- {{ post.title }}</a>
	</li>
{% endif %}
{% endfor %}  -->

</ul>

<br>

---------------

## References 

<br>

\- [GitHub][]
\- [GitHub Pages][]
\- [GitHub Desktop][]
\- [GitHub - Custom Domain Name][]
\- [Jekyll][]


[GitHub]: {{ site.data.url.git.home }}
[GitHub Desktop]: {{ site.data.url.git.desktop }}
[GitHub Pages]: {{ site.data.url.git.pages }}
[Jekyll]:  {{ site.data.url.jekyll.home }}
[GitHub - Custom Domain Name]: {{ site.data.url.git.custom_domain }}
[Twitter]: {{ site.data.url.virtua.twitter }}
[YouTube Channel]: {{ site.data.url.virtua.youtube }}
[storage limit of 1 GB]: {{ site.data.url.git.quota }}