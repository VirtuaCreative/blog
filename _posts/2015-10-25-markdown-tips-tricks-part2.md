---
layout: post
title: "Markdown Tips & Tricks - Part 2"
categories: [jekyll, github, tutorials in English]
tags: [markdown, kramdown, jekyll, github, github pages, git]
meta_keywords: markdown, kramdown, jekyll, github, github pages, git, tips and tricks, dicas e truques
author: Marcia Ramos
fb_section: Tutorials - Jekyll
description: Part 2 - Embedding videos.
image: http://goo.gl/zcwqIN
imageUrl: https://goo.gl/Kb7R0N
image_schema: 'http://farm1.staticflickr.com//636//22456839236_a446a2ef25_o.png'
fb_title: Markdown Tips & Tricks - Part 2
fb_type: article
author_fb: marciaramosmdr
author_twitter: xmdramos
date: 2015-10-25 23:36:10 UTC
comments: true
published: true
authorUrl: https://plus.google.com/+MarciaDiasRamosMD/
language: [en_US, en_GB]
date_update: 2016-02-12 19:00:48 UTC
copy: true # copy button with javascript  
codingbox: true # code type on the top-right of code block boxes 
---

# **<mkp-blue>Embedding Videos in Markdown</mkp-blue>**

<br>

This is the second article of the series **"Markdown Tips & Tricks - Thinking Outside the Box"**. On the [previous article][], it was explained how to deal with `html` **elements** and **classes** when writing markdown files. Now we are going to show you how to embed videos.

On the first part of this article, treated like **["Case A"](#i-classfa-fa-youtubeinbspnbspcase-a-iframe-tags---embedding-youtube-videos)**, we will have covered the steps for embedding videos via `iframe`, like you would do with YouTube videos. On the next, **["Case B"](#i-classfa-fa-youtube-playinbspnbspcase-b-video-tags)**, we will show you how to do that via `<video>` `html 5` tag, used when you need to display a video from your site root files.

As we have explained on the [previous article][], there's only a thing you need to worry abaout when adding `html elements` to you markdown:

<p class="bkggreen"><i class="fa fa-exclamation" style="color: red;"></i>&nbsp;&nbsp;You need to leave a <strong>blank line</strong> between some regular markdown text and a <strong>html tag</strong>, otherwise you might face errors during files compilation!</p>

<hr>

### **<i class="fa fa-youtube"></i>&nbsp;&nbsp;Case A: `<iframe>` Tags** - Embedding YouTube Videos

<br>

All right. Let's begin by showing you how to embed **YouTube videos**, as found in our post **[How to publish your website on GitHub][]**. Doing this can be a little tricky, as there are some steps to have covered up to make it be rendered correctly. Let's see a live example, with a video we have used on the post we just mentioned. Here it is, down below. You will notice that you can resize your browser's window and it will maintain its responsiveness.

<br>

<figure class="iframe_container">
	<iframe width="853" height="480" src="http://www.youtube.com/embed/E-ONNjFoOx0" frameborder="0" allowfullscreen="allowfullscreen"> </iframe> 
</figure>

<br>

<p class="bkggreen"><i class="fa fa-exclamation" style="color: red;"></i>&nbsp;&nbsp;We'll need to copy the code given by <strong>YouTube</strong> and paste it onto your markdown file, and from that we'll need to <strong>make a few corrections</strong> in order to make it work properly, according to step-by-step section below.</p>

<br>

### **Step-by-Step**

**First:** open in a web browser the YouTube video that you want to embed to your post and copy the `iframe`. If you don't know how to do that, learn from this 15 seconds video: 

<br>

<figure id="iframe-video" class="video_container">
	<video controls="controls" allowfullscreen="true" poster="{{ site.baseurl }}/assets/media/embed-youtube-poster.png">
  		<source src="{{ site.baseurl }}/assets/media/embed-youtube.mp4" type="video/mp4">
	</video> 
</figure>

<br>

**Second:** paste the `<iframe>` into a `<div>` tag:

{% highlight markdown %}
.... <!-- post content -->

<div class="iframe_container">
  <iframe width="560" height="315" src="http://www.youtube.com/embed/E-ONNjFoOx0" frameborder="0" allowfullscreen></iframe>
</div>

.... <!-- post content -->
{% endhighlight %}

**Third:** instead of leaving the atribute `allowfullscreen` with no value, give it a value of "allowfullscreen": `allowfullscreen="allowfullscreen"`. 

**Fourth:** Add a space in between opening and closing `<iframe>` tags: instead of `<iframe></iframe>`, make sure it looks like that:

`<iframe> </iframe>`. 

**Fifth:** You can remove the proprieties of `width` and `hight` given by **YouTube** iframe, as they will be replaced by the `<div>` tag styles. But you can leave it there as well, it won't make any difference.

Now your code will look like that:

<div name="clipboard-text" id="clipboard-text-1">

{% highlight markdown %}
.... <!-- post content -->

<div class="iframe_container">
  <iframe src="http://www.youtube.com/embed/E-ONNjFoOx0" frameborder="0" allowfullscreen="allowfullscreen"> </iframe>
</div>

.... <!-- post content -->
{% endhighlight %}

</div>

<p id="btn1" class="clipb"><button onclick="fDisplay()" id="target-to-copy" data-clipboard-target="clipboard-text-1" class="target-to-copy copy btn btn-lg" title="Click to copy the code above and paste it into your doc."><i class="fa fa-files-o"></i>&nbsp;&nbsp;Click to copy</button></p>

<p id="ok0" class="clipb"></p>

<script>
function fDisplay() {
    document.getElementById("ok0").innerHTML = "<button class='btn btn-success'>&nbsp;<i class='fa fa-check'>&nbsp;</button>";
}
</script>

<br>

We wrapped the `<iframe>` tag within a `<div>`, in order to provide full responsiveness to our embed videos. For making this happen, we have applied the following styles:

<div name="clipboard-text" id="clipboard-text-2">

{% highlight css %}
.iframe_container {
	position: relative;
	padding-bottom: 56.25%; /* 16:9 - this is responsive by adjusting the hight according to the width! */
	padding-top: 25px;
	height: 0;
}

.iframe_container iframe {
	position: absolute;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
}
{% endhighlight %}

</div>

<p id="btn2" class="clipb"><button onclick="Display()" id="target-to-copy" data-clipboard-target="clipboard-text-2" class="target-to-copy copy btn btn-lg" title="Click to copy the code above and paste it into your doc."><i class="fa fa-files-o"></i>
&nbsp;&nbsp;Click to copy</button></p>

<p id="ok1" class="clipb"></p>

<script>
function Display() {
    document.getElementById("ok1").innerHTML = "<button class='btn btn-success'>&nbsp;<i class='fa fa-check'>&nbsp;</button>";
}
</script>

<br>

**That's it!** Now you can use the code block we provided whenever you want to embed a YouTube video. Actually, the only thing you will need to change is the **video id**, given by the last part after the last forward slash. On this video `http://www.youtube.com/embed/E-ONNjFoOx0`, its **id** is `E-ONNjFoOx0`. 

<br>

<hr>

### **<i class="fa fa-youtube-play"></i>&nbsp;&nbsp;Case B: `<video>` Tags**

<br>

Now, if you have videos that you don't want to publish on YouTube and want them to be part of your media files, you will need a `html 5` `<video>` tag.

Adding a `<video>` tag is very straight forward, exactly as we did for `<div>` or `<hr>` tags on the [previous article][]. Just add a `<video>` tag to your markdown text and you are good to go! 

<div name="clipboard-text" id="clipboard-text-3">

{% highlight markdown %}
.... <!-- post content -->

<div class="video_container">
  <video controls="controls" allowfullscreen="true" poster="path/to/poster_image.png">
    <source src="path/to/video.mp4" type="video/mp4">
  </video> 
</div>

.... <!-- post content -->
{% endhighlight %}

</div>

<p id="btn2" class="clipb"><button onclick="nDisplay()" id="target-to-copy" data-clipboard-target="clipboard-text-3" class="target-to-copy copy btn btn-lg" title="Click to copy the code above and paste it into your doc."><i class="fa fa-files-o"></i>
&nbsp;&nbsp;Click to copy</button></p>

<p id="ok2" class="clipb"></p>

<script>
function nDisplay() {
    document.getElementById("ok2").innerHTML = "<button class='btn btn-success'>&nbsp;<i class='fa fa-check'>&nbsp;</button>";
}
</script>


<br>

Let's see a live example with the code above, using a video we have in our blog assets:

<figure id="iframe-video" class="video_container">
	<video controls="controls" allowfullscreen="true" poster="{{ site.baseurl }}/assets/media/blog_poster.png">
  		<source src="{{ site.baseurl }}/assets/media/blog.mp4" type="video/mp4">

	</video> 
</figure>

<br>


As we did for the `<iframe>`, we wrapped the `<video>` tag within a `<div>`, in order to provide full responsiveness to our videos, and we have applied exactly the same styles:

{% highlight css %}
.video_container {
	position: relative;
	padding-bottom: 56.25%; /* 16:9 */
	padding-top: 25px;
	height: 0;
}

.video_container video {
	position: absolute;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
}
{% endhighlight %}

<br>


**That's it!** Now you can use your `<video>` tags whenever you want! Just replace the path and you're done! The supported formats are: `.mp4`, `.ogg` and `.webm`. If you want to check other **methods and attributes** that can be used with `<video>` tags, go ahead and find them in **W3Schools**: a [basic usage][] or a [complete reference][].

If you are thinking about `flash` videos, it's not a good idea using them anymore. As little as you use flash, better for you. It's promised to be deprecated soon. iPhones, iPads and lots of other devices do not support flash anymore. 

<br>

<hr>

### **<mkp-blue>Well done!</mkp-blue>**

After covering all the content of this and the [previous article][], we can see that when working on markdown files, if we want to do something that is not by the books, we just need give it a try! As a matter of fact, most of them will work!

Enjoy! :dancers: :smiley: :thumbsup:

<br>

<hr>


### **<mkp-blue>That's all folks!</mkp-blue>**

We hope to have been helpfull! Please, if you enjoyed this article, leave a comment to let us know! 

If you have any questions or suggestions, please feel free to get in touch with us by filling our  [contact form]({{ site.data.url.virtua.git-contact }}).

Thanks for reading! Stay tuned for the next article: follow us on [Twitter]({{ site.data.url.virtua.twitter }}), [Google+]({{ site.data.url.virtua.googleplus }}) or subscribe to our [YouTube Channel]({{ site.data.url.virtua.youtube }}) 

<br>

---------------

### **Related Articles**

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

<!-- 
NEW WAY
Related articles (by Jekyll itself) -->


<!-- {% for post in site.related_posts limit:3 %}
{% if post.language contains 'en_US' and post.categories contains 'github' %}
	<li>
	  <a href="{{ site.baseurl }}{{ post.url }}">- {{ post.title }}</a>
	</li>
{% endif %}
{% endfor %}  -->

</ul>

<br>

<hr>

### **References**

- &#9734; [GitHub][]
- &#9734; [GitHub Pages][]
- &#9734; [Jekyll][]
- &#9734; [GitHub Flavored Markdown][]
- &#9734; [Jekyll Documentation][]
- &#9734; [Markdown][]
- &#9734; [Kramdown][]

<br>

<hr>

### **Image Credits**

- &#9733; Art work: Virtua Creative
- &#9733; Illustrations: we have downloaded from Freepik the original [box](http://www.freepik.com/free-vector/vectors_785241.htm) and the original [bulb](http://www.freepik.com/free-vector/vectors_810569.htm).

<br>

[How to publish your website on GitHub]: http://virtuacreative.github.io/blog/free-hosting-website-github.html
[another article]: http://virtuacreative.github.io/blog/free-hosting-website-github.html
[recommended by GitHub]: https://help.github.com/articles/using-jekyll-with-pages/#running-jekyll
[avoiding building errors]: https://help.github.com/articles/troubleshooting-github-pages-build-failures/#viewing-jekyll-build-error-messages-locally
[Blog]: {{ site.data.url.virtua.blog }}
[GitHub]: {{ site.data.url.git.home }}
[GitHub Pages]: {{ site.data.url.git.pages }}
[Jekyll]:  {{ site.data.url.jekyll.home }}
[Kramdown]: {{ site.data.url.markdown.kramdown }}
[GitHub Flavored Markdown]: {{ site.data.url.git.gfm }}
[Jekyll Documentation]: {{ site.data.url.jekyll.docs }}
[Markdown]: {{ site.data.url.markdown.all }}
[previous article]: {{ site.data.url.articles.tipsntricks }}
[basic usage]: http://www.w3schools.com/html/html5_video.asp
[complete reference]: http://www.w3schools.com/tags/ref_av_dom.asp
