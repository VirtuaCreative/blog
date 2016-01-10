---
layout: post
title: Markdown Tips & Tricks - Thinking Outside the Box
categories: [jekyll, github, tutorials in English]
tags: [markdown, kramdown, jekyll, github, github pages, git]
meta_keywords: markdown, kramdown, jekyll, github, github pages, git, tips and tricks, dicas e truques
author: Marcia Ramos
fb_section: Tutorials - Jekyll
description: Part 1 - Adding elements & applying classes onto markdown files.
image: http://goo.gl/UCRjlU
imageUrl: https://goo.gl/j7q6Az
image_schema: 'http://farm6.staticflickr.com//5669//22219534621_37cf89d7ce_o.png'
fb_title: Markdown Tips & Tricks - Thinking Outside the Box - Part 1
fb_type: article
author_fb: marciaramosmdr
author_twitter: xmdramos
date: 2015-10-15 20:36:10 UTC
comments: true
published: True
authorUrl: https://plus.google.com/+MarciaDiasRamosMD/
language: [en_US, en_GB]
date_update: 2016-01-08 23:07:00 UTC
# copy:
codingbox: true
related: jekyll
---
# **<mkp-blue>Markdown</mkp-blue>**

<br>

For those who are used to write in Markdown or are beginning to learn this language, we are here to provide you some tricks and tips that may help you to think outside the box and make some :zap: "magic" :zap: when writing your files. 

<br>

#### _Markdown Tips & Tricks - Part 1_ 

On this article, you will learn how to **[add new `HTML` elements](#mkp-blueadding-html-elementsmkp-blue)** (also **[`div` tags](#mkp-blueadding-html-divsmkp-blue)**) and how to **[apply classes to `html` elements](#mkp-blueapplying-html-classesmkp-blue)** onto your markdown files.

<br>

#### _Markdown Tips & Tricks - Part 2_  

On the **next post**, we are going to show you how to **embed videos** on your markdown files. This second part will be published at October 25th.

<br>

#### _Additional Information_  

For markdown basics, you can check this [GitHub article](https://guides.github.com/features/mastering-markdown/#syntax), which provides us with a bunch of very often applied markup.

All the examples given below were tested on our [Blog] written in [Jekyll][], hosted by [GitHub Pages][], within a `gh-pages` branch for a `project` website. Depending on your server or on the way your site is build, some of these tips might not work. Anyway, feel free to give them a try, even if your markdown files don't have the same configuration or compilation. 

<br> 

### **Settings**

Our Jekyll `_config.yml` settings are the following:

{% highlight yaml %}
---
... your settings ...

highlighter: pygments
markdown: kramdown

kramdown:
  input: GFM          # this is a support for GitHub Flavored Markdown

gems:
  - jemoji            # this is a support for emoticons
  - jekyll-mentions   # this is a support for GitHub user's mentions by adding @ before their names

... your settings ...
---
{% endhighlight %}

The tips provided by this post worked very well using [Kramdown][] and [Pygments][]. Other markdown and highlighters haven't been tested yet, but you are more than invited to give it a try and tell us if works or not! :smiley:

Our build has been made by running `bundle exec jekyll serve --safe` on the command prompt, at the local root folder, as [recommended by GitHub][]. Using the `--safe` mode allows you to build your site locally in the closest way that GitHub will do it, [avoiding building errors][] when uploading your files to GitHub.

Our `default.html` file (where the markdown posts are called to) is placed at our `_includes` folder and is a `HTML 5` document. Our styles are written in `CSS 3`.

<br>

<hr>

# **<mkp-blue>Adding HTML Elements</mkp-blue>**

<br>

Let's begin with new elements. Did you know you can add `HTML elements` to your markdown? For example, if you need a horizontal line, you can add it as the code below: 

{% highlight text linenos %}
Some text here
// blank line
<hr>
// blank line
Something else here
{% endhighlight %}

...and will be compiled to...

{% highlight html %}
<p>Some text here</p>
<hr>
<p>Something else here</p>
{% endhighlight %}

Note that we left the lines `2` and `4` empty, this is a **condition** for `html` elements to be untouched when your markdown is compiled. 

Now you can freely style your `<hr>` in your `CSS`. 

Just to let you know, in this particular case you can use just a sequence of `----------` onto your markdown and it will produce a `<hr>` tag when compiled to html. But sometimes you can't run from using some `html` tags themselves in order to have the results you want.

Feel free to use the tag `<br>` the same way for breaking lines. 

<p class="bkggreen"><i class="fa fa-exclamation" style="color: red;"></i>&nbsp;&nbsp;Don't forget to leave a <strong>blank line</strong> between some regular markdown text and a <strong>html tag</strong>, otherwise you might face errors during files compilation!</p>

Following the same logic, `HTML 5` allows you to add some extra elements, and you are also free to make up your own. For example, as you might have noticed, some of our titles on this blog are **<mkp-blue>blue</mkp-blue>**. How did we do that? 

This is not a `<span>` tag. Actually, we made a new element up, called `<mkp-blue>`. You can call elements whatever you want. This element has only one propriety defined in our `CSS`, all the others are inherit from its parent element:

{% highlight css %}

mkp-blue {
	color: blue;
}

{% endhighlight %}

We can use these new elements combined with markup, for example, this line:

{% highlight text %}
Hello! I'm a **<mkp-blue>blue</mkp-blue>** word in a regular markdown text!
{% endhighlight %}

...will be compiled to:

{% highlight html %}
<p>Hello! I'm a <strong><mkp-blue>blue</mkp-blue></strong> word in a regular markdown text!</p>
{% endhighlight %}

...and this is going to be the result displayed on users' browsers:

<p class="bkgblue">Hello! I'm a <strong><mkp-blue>blue</mkp-blue></strong> word in a regular markdown text!</p>

**BUT**, you **can't** do the opposite, using a markup within an html tag, like:

{% highlight text %}
Hello! I'm a <mkp-blue>**blue**</mkp-blue> word in a regular markdown text!
{% endhighlight %}

... as it will be compiled to:

{% highlight html %}
<p>Hello! I'm a <mkp-blue>**blue**</mkp-blue> word in a regular markdown text!</p>
{% endhighlight %}

... and will produce this result:

<p class="bkgblue">Hello! I'm a <mkp-blue>**blue**</mkp-blue> word in a regular markdown text!</p>

... which probably is not what you want.

That's it, you can add as many default or non-default elements to your markdown file, as long as you leave blank lines above and below them.

<br> 

<hr>


# **<mkp-blue>Adding HTML Divs</mkp-blue>**

Exactly as we just have done, you can add some **html divs** to your markdown. And with divs, you can do pretty much anything you like, such as giving classes, ids, transitions, and anything that a regular `<div>` tag supports in `HTML 5`.

For example, let's say you want a particular image style at some point, you can just wrap it into a `<div>` and that's it!

{% highlight text %}
...

<div class="example">
	<img src="http:something.com/img/img1.png" alt="Some alternative text">
</div>

...
{% endhighlight %}

The result will be exactly as expected:

{% highlight html %}
...
<div class="example">
	<img src="http:something.com/img/img1.png" alt="Some alternative text">
</div>
...
{% endhighlight %}

And you customize your special image as you want, for example:

{% highlight css %}
.example img {
	width: 30%;	
	border: 1px solid #333;	
	box-shadow: 2px 2px 5px #999;
	border-radius: 5px;
}
{% endhighlight %}

<br>

Here is the result:

<div class="example">
	<img src="{{ site.baseurl }}/assets/media/blog_poster.png" alt="Some alternative text" style="width: 30%;	border: 1px solid #333;	box-shadow: 2px 2px 5px #999; border-radius: 5px;">
</div>

<br>

Of course we could have styled the image itself in this case, but sometimes we need nested elements in order to produce the results we want. A very common case is giving an element a `position="relative"` and its nested element a `position="absolute"`. We cannot achieve the same results by playing around just with one of them, we'll need them both!

<br>

<hr>

# **<mkp-blue>Applying HTML Classes</mkp-blue>**

<br> 

When I first started writing in markdown, I googled something like "how to apply classes to markdown" and couldn't find much. **BUT**, when I tried something unusual, for my best surprise, it worked!

For example, let's say you want to apply a different class to a paragraph. Instead of writing the regular text on markdown, as:

{% highlight text %}
...
Hello! I'm a regular textile paragraph written in a markdown file!
...
{% endhighlight %}

... you are free to write it as a `<p>...</p>` HTML tag, like:

{% highlight text linenos %}
...

<p class="myclass">Hello! I'm a regular HTML paragraph written in a markdown file!</p>

...
{% endhighlight %}

... and it will be compiled to:

{% highlight html %}
...
<p class="myclass">Hello! I'm a regular HTML paragraph written in a markdown file!</p>
...
{% endhighlight %}

... and will be displayed on the browser like:

<p class="bkgblue">Hello! I'm a regular HTML paragraph written in a markdown file!</p>

The only difference is that we have applied a new class to the paragraph, giving it a bluish background. But you can style your tags according to your needs!

That's it! As simple as it looks! This way you are free to style your `HTML tags` compiled from your markdown files however you want!

Just *do not forget* to always leave a blank line between your markdown regular text and any `HTML` tag!

<br>

### **<mkp-blue>Done!</mkp-blue>**

All right then, now that you know that you can add `html elements` and apply classes to them in markdown files, it's time to make it work for you! Go on and use them freely, you'll see that the results are fantastic and at the same time we keep the astonishing advantages of writing in markdown!

Don't lose our next post, where we will show you how to embed videos in markdown files. It can be a little tricky, specially giving them responsiveness, but we are here to share our knowledge with you! :smiley:

<br>

<hr>

### **<mkp-blue>That's all folks!</mkp-blue>**

We hope to have been helpful! Please, if you enjoyed this article, share it, recommend it or leave a comment to let us know! 

If you have any questions or suggestions, please feel free to get in touch with us by filling our  [contact form]({{ site.data.url.virtua.git-contact }}).

Thanks for reading! Stay tuned for the next article (**Markdown Tips and Tricks - Part 2**)! Follow us on [Twitter]({{ site.data.url.virtua.twitter }}), [Google+]({{ site.data.url.virtua.googleplus }}) or subscribe to our [YouTube Channel]({{ site.data.url.virtua.youtube }})! 

<br>

---------------

### **Related Article(s)**

<ul>
{% for art in site.data.articles.github %}
  <li>
    <a href="{{ art.url }}">- {{ art.title }}</a>
  </li>
{% endfor %}
</ul>

<p>{{ site.data.artigos.jekyll.title }}</p>

<br>

<hr>

### **References**

\- [GitHub][]
\- [GitHub Pages][]
\- [Jekyll][]
\- [GitHub Flavored Markdown][]
\- [Jekyll Documentation][]
\- [Markdown][]
\- [Kramdown][]

<br>

<hr>

### **Image Credits**

\- Art work: Virtua Creative
\- Illustrations: we have downloaded from Freepik the original [box](http://www.freepik.com/free-vector/vectors_785241.htm) and the original [bulb](http://www.freepik.com/free-vector/vectors_810569.htm).

[How to publish your website on GitHub]: http://virtuacreative.github.io/blog/free-hosting-website-github.html
[another article]: http://virtuacreative.github.io/blog/free-hosting-website-github.html
[recommended by GitHub]: https://help.github.com/articles/using-jekyll-with-pages/#running-jekyll
[avoiding building errors]: https://help.github.com/articles/troubleshooting-github-pages-build-failures/#viewing-jekyll-build-error-messages-locally
[Blog]: {{ site.data.url.virtua.blog }}
[GitHub]: {{ site.data.url.git.home }}
[GitHub Pages]: {{ site.data.url.git.pages }}
[Jekyll]:  {{ site.data.url.jekyll.home }}
[Kramdown]: {{ site.data.url.markdown.kramdown }}
[Pygments]: {{ site.data.url.markdown.pygments }}
[GitHub Flavored Markdown]: {{ site.data.url.git.gfm }}
[Jekyll Documentation]: {{ site.data.url.jekyll.docs }}
[Markdown]: {{ site.data.url.markdown.all }}
