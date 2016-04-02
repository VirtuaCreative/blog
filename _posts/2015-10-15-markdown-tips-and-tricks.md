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
date_update: 2016-03-30 20:52:42 UTC
# copy:
codingbox: true
related: jekyll
---
# **<mkp-blue>Markdown</mkp-blue>**

For those who are used to write in Markdown or are beginning to learn this language, we are here to provide you some tricks and tips that may help you to think outside the box and make some :zap: "magic" :zap: when writing your files. 

#### _Markdown Tips & Tricks - Part 1_ 

On this article, you will learn how to **[add new `HTML` elements](#mkp-blueadding-html-elementsmkp-blue)** (also **[`div` tags](#mkp-blueadding-html-divsmkp-blue)**) and how to **[apply classes to `html` elements](#mkp-blueapplying-html-classesmkp-blue)** onto your markdown files.

#### _[Markdown Tips & Tricks - Part 2](/markdown-tips-tricks-part2.html)_  

On the **next post**, we are going to show you how to **embed videos** on your markdown files. This second part will be published at October 26th.

#### _Additional Information_  

For markdown basics, you can check this [GitHub article](https://guides.github.com/features/mastering-markdown/#syntax), which provides us with a bunch of very often applied markup.

All the examples given below were tested on our [Blog] written in [Jekyll][], hosted by [GitHub Pages][], within a `gh-pages` branch for a `project` website. Depending on your server or on the way your site is build, some of these tips might not work. Anyway, feel free to give them a try, even if your markdown files don't have the same configuration or compilation. 

### **Settings**

Our Jekyll `_config.yml` settings are the following:

{% highlight yaml %}
---
# your settings ...

highlighter: rouge
markdown: kramdown
kramdown:
  input: GFM          # this is a support for GitHub Flavored Markdown

gems:
  - jemoji            # this is a support for emoticons
  - jekyll-mentions   # this is a support for GitHub user's mentions by adding @ before their names

# your settings ...
---
{% endhighlight %}

The tips provided by this post worked very well using [Kramdown][] with [GFM][] and [Rouge][]. It works fine when replacing `rouge` for `pygments` too. Other markdown and highlighters haven't been tested yet, but you are more than invited to give it a try and tell us if works or not! :smiley:

Our build has been made by running `bundle exec jekyll serve --safe` on the command prompt, at the local root folder, as [recommended by GitHub][]. Using the `--safe` mode allows you to build your site locally in the closest way that GitHub will do it, [avoiding building errors][] when uploading your files to GitHub.

**Update!**
{: .color_blue}

It seems to have a [**bug** on GitHub Pages](https://talk.jekyllrb.com/t/jekyll-3-x-with-github-pages/1832/12) regarding the `--safe` flag! So, for now, we recommend you to serve Jekyll with Bundler without this flag, at least until they fix it. Run `bundle exec jekyll serve` and watch for changes running `bundle exec jekyll serve --watch`.

Our `default.html` file (where the markdown posts are called to) is placed at our `_includes` folder and is a `HTML5` document. Our styles are written in `CSS3`.

<hr>

# **<mkp-blue>Adding HTML Elements</mkp-blue>**

Let's begin with new elements. Did you know you can add `HTML elements` to your markdown? For example, if you need a horizontal line, you can add it as the code below: 

{% highlight markdown linenos %} Some text here
// blank line
<hr>
// blank line
Something else here {% endhighlight %}

...and will be compiled to...

{% highlight html %}
<p>Some text here</p>
<hr>
<p>Something else here</p>
{% endhighlight %}

Note that we left the lines `2` and `4` empty, this is a **condition** for `html` elements to be untouched when your markdown is compiled. 

Now you can freely style your `<hr>` in your `CSS`. 

Just to let you know, in this particular case you can use just a sequence of `-----` onto your markdown and it will produce a `<hr>` tag when compiled to html. But sometimes you can't run from using some `html` tags themselves in order to have the results you want.

Feel free to use the tag `` the same way for breaking lines. 

<p class="bkggreen"><i class="fa fa-exclamation" style="color: red;"></i>&nbsp;&nbsp;Don't forget to leave a <strong>blank line</strong> between some regular markdown text and a <strong>html tag</strong>, otherwise you might face errors during files compilation!</p>

### Custom Elements 

Following the same logic, `HTML 5` allows you to add some extra elements, and you are also free to make up your own. We have added a few custom elements to this blog. For example, as you might have noticed, some of our titles on this blog are **<mkp-blue>blue</mkp-blue>**. How did we do that? 

This is not a `<span>` tag. Actually, we made a new element up, called `<mkp-blue>`. You can call elements whatever you want. This element has only one propriety defined in our `CSS`, all the others are inherit from its parent element:

{% highlight css %}

mkp-blue {
	color: blue;
}

{% endhighlight %}

We can use these new elements combined with markup, for example, this line:

{% highlight markdown %}
Hello! I'm a **<mkp-blue>blue</mkp-blue>** word in a regular markdown text!
{% endhighlight %}

...will be compiled to:

{% highlight html %}
<p>Hello! I'm a <strong><mkp-blue>blue</mkp-blue></strong> word in a regular markdown text!</p>
{% endhighlight %}

...and this is going to be the result displayed on users' browsers:

<p class="bkgblue">Hello! I'm a <strong><mkp-blue>blue</mkp-blue></strong> word in a regular markdown text!</p>

**BUT**, you **can't** do the opposite, using a markup within an html tag, like:

{% highlight markdown %}
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

**ATTENTION**

Making up your own custom elements is not recommended when you want to stick to the standards. Also, they haven't cross-browser compatibility. There is an [article](http://www.html5rocks.com/en/tutorials/webcomponents/customelements/#fromtemplate) where the author goes deep into this subject. The [minimum recommendation](http://stackoverflow.com/questions/2802687/is-there-a-way-to-create-your-own-html-tag-in-html5/#answer-11467718) is adding this code to the site `<head>` when you use them:

{% highlight html %}
<!--[if lt IE 9]> 
<script> document.createElement("element_name"); </script>
<![endif]-->
{% endhighlight %}

This will create a new element when the http request to your site is comming from _Internet Explorer 9_. 

----

# **<mkp-blue>Adding HTML Divs</mkp-blue>**

Exactly as we just have done, you can add some **html divs** to your markdown. And with divs, you can do pretty much anything you like, such as giving classes, ids, transitions, and anything that a regular `<div>` tag supports in `HTML 5`.

For example, let's say you want a particular image style at some point, you can just wrap it into a `<div>` and that's it!

{% highlight markdown %}
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

Here is the result:

<figure class="example">
	<img src="{{ site.baseurl }}/assets/media/blog_poster.png" alt="Some alternative text" style="width: 30%;	border: 1px solid #333;	box-shadow: 2px 2px 5px #999; border-radius: 5px;">
</figure>

Of course we could have styled the image itself in this case, but sometimes we need nested elements in order to produce the results we want. A very common case is giving an element a `position="relative"` and its nested element a `position="absolute"`. We cannot achieve the same results by playing around just with one of them, we'll need them both!

----

# **<mkp-blue>Applying HTML Classes</mkp-blue>**

When I first started writing in markdown, I googled something like "how to apply classes to markdown" and couldn't find much. **BUT**, when I tried something unusual, for my best surprise, it worked!

For example, let's say you want to apply a different class to a paragraph. Instead of writing the regular text on markdown, as:

{% highlight markdown %}
...
Hello! I'm a regular textile paragraph written in a markdown file!
...
{% endhighlight %}

... you are free to write it as a `<p>...</p>` HTML tag, like:

{% highlight markdown linenos %}
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

### **<mkp-blue>Update!</mkp-blue>**

I've just found out an easy way to applying **classes** to your markdown!! Look at that:

I'm in a green box now!
{: .bkggreen}

This was simply achieved by this piece of code:

{% highlight markdown %}
I'm in a green box now!
{% raw %}{: .bkggreen}{% endraw %}
{% endhighlight %}

 It's awesome, isn't it?! :dancers:

**What if I need more than one `class`?**
{: .color_blue}

{% highlight markdown %}
I have tree classes now!
{% raw %}{: .class1 .class2 .class3}{% endraw %}
{% endhighlight %}

**What if I need an `id`?**
{: .color_blue}

{% highlight markdown %}
# I have an ID now! => works for headings too!
{% raw %}{: #i_am_an_id}{% endraw %}
{% endhighlight %}

**What if I need both, an `id` and a `.class`?**
{: .color_blue}

{% highlight markdown %}
I have an ID and a CLASS now!
{% raw %}{: #i_am_an_id .class}{% endraw %}
{% endhighlight %}

I just **loved** this! Check the [full reference](http://kramdown.gettalong.org/quickref.html) out!

### **<mkp-blue>Done!</mkp-blue>**

All right then, now that you know that you can add **html elements** and **apply classes** to them in markdown files, it's time to make it work for you! Go on and use them freely, you'll see that the results are fantastic and at the same time we keep the astonishing advantages of writing in markdown!

Don't lose our next post, where we will show you how to embed videos in markdown files. It can be a little tricky, specially giving them responsiveness, but we are here to share our knowledge with you! :smiley:

### **<mkp-blue>That's all folks!</mkp-blue>**

We hope to have been helpful! Please, if you enjoyed this article, share it, recommend it or leave a comment to let us know! 

If you have any questions or suggestions, please feel free to get in touch with us by filling our  [contact form]({{ site.data.url.virtua.home_contact }}).

Thanks for reading! Check our next article **[Markdown Tips and Tricks - Part 2](/markdown-tips-tricks-part2.html)**! 

Stay tuned! Follow us on [Twitter]({{ site.data.url.virtua.twitter }}), [Google+]({{ site.data.url.virtua.googleplus }}) or subscribe to our [YouTube Channel]({{ site.data.url.virtua.youtube }})! 

### **Related Article(s)**

<ul>
{% for art in site.data.articles.github %}
  <li>
    <a href="{{ art.url }}">&#8674; {{ art.title }}</a>
  </li>
{% endfor %}
</ul>

### **References**

- &#9734; [GitHub][]
- &#9734; [GitHub Pages][]
- &#9734; [Jekyll][]
- &#9734; [GitHub Flavored Markdown][]
- &#9734; [Jekyll Documentation][]
- &#9734; [Markdown][]
- &#9734; [Kramdown][]

----

### **Image Credits**

- &#9733; Art work: [Virtua Creative](https://goo.gl/j7q6Az)
- &#9733; Illustrations: we have downloaded from Freepik the original [box](http://www.freepik.com/free-vector/vectors_785241.htm) and the original [bulb](http://www.freepik.com/free-vector/vectors_810569.htm).

[How to publish your website on GitHub]: http://virtuacreative.github.io/blog/free-hosting-website-github.html
[another article]: http://virtuacreative.github.io/blog/free-hosting-website-github.html
[recommended by GitHub]: https://help.github.com/articles/using-jekyll-with-pages/#running-jekyll
[avoiding building errors]: https://help.github.com/articles/troubleshooting-github-pages-build-failures/#viewing-jekyll-build-error-messages-locally
[Blog]: {{ site.data.url.virtua.blog }}
[GitHub]: {{ site.data.url.git.home }}
[GitHub Pages]: {{ site.data.url.git.pages }}
[Jekyll]:  {{ site.data.url.jekyll.home }}
[Kramdown]: {{ site.data.url.markdown.kramdown }}
[Rouge]: {{ site.data.url.markdown.rouge_gem }}
[GitHub Flavored Markdown]: {{ site.data.url.git.gfm }}
[Jekyll Documentation]: {{ site.data.url.jekyll.docs }}
[Markdown]: {{ site.data.url.markdown.all }}
[GFM]: {{ site.data.url.git.gfm }}