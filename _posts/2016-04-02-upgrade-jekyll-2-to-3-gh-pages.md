---
layout: post
title: Upgrading Jekyll 2 to 3 on GitHub Pages
categories: [github, github pages, git, jekyll, tutorials in English]
tags: [github, github pages, jekyll, upgrade, markdown, kramdown]
meta_keywords: jekyll, jekyll upgrade, github, github pages, github website, broken site
author: Marcia Ramos
fb_section: Tutorials - Jekyll on GitHub
description: "Broken Jekyll site on GitHub Pages? Learn how to fix it!"
image: http://goo.gl/Tz42UV
imageUrl: https://goo.gl/nKQCBu
image_schema: 'http://farm2.staticflickr.com//1563//25576817513_3751945298_o.png'
fb_title: Upgrading Jekyll 2 to 3 on GitHub Pages
fb_type: article
author_fb: marciaramosmdr
author_twitter: xmdramos
date: 2016-04-02 09:07:14 BRT
comments: true
published: true
authorUrl: https://plus.google.com/+MarciaDiasRamosMD/
language: [en_US, en_GB]
date_update: 2016-04-10 18:16:52 BRT
# copy: true # copy button with javascript
# codingbox: true # code type on the top-right of code block boxes
related: github
css: [table]
---

# Is your Jekyll site broken on GitHub Pages?

If you didn't know about the new [Jekyll 3 release][jekyll-3], you probably got surprised when you opened your website hosted by GitHub and saw that some things were broken (and they weren't before). The problem is not due to Jekyll upgrade though. The thing is, GitHub Pages environment has changed!

Until January of 2016, the version running on GitHub Pages was [Jekyll 2.4.0][gem-jek-240]. On February 1st, they changed it to [Jekyll 3.0.2][gh-jek-3], which provoked a bunch of broken sites. Currently (on 2016-03-30), GH Pages is building with [Jekyll 3.0.3][gem-jek-303]. Looks like they will keep upgrading. You can check here which [version and dependencies are running][gh-versions] on GitHub Pages at the time you read this article.

GitHub recently published another [post][gh-post] on their blog explaing themselves a little better and providing the community with some answers.

Bottom line, another wave of **broken sites** is expected to [May 1st, 2016][gh-jek-3]. From this date on, GitHub Pages will **not** support `redcarpet`, `rdiscount` nor `redcloth` anymore. It means we'll need to work with `kramdown` only. 

# What has changed?

Jekyll 3.x has changed substantially from it's 2.x version. The main reasons for these changes was decreasing the number of dependencies and avoid [Python], they wanted everything running on [Ruby] only. Take a look at the table below.

| Propriety | Jekyll 2.x Default | Jekyll 3.x Default |
| :-------- | :--------: | :--------: | 
|Markdown|Redcarpet |Kramdown|
|Highlighter|Pygments|Rouge|
|Collection|`collection[0]`|`collection.label`|
|Requirement|Python|---|
|Gem |`jekyll-paginate`|---|
|Gem |`jekyll-gist`|---|
|Post Date|---|`future: false`|
|Flag|---|`--incremental`|
|Flag|---|`--profile`|
|Relative permalinks|`relative_permalinks`|---|
|Permalinks trailing slash|automatic|---| 

If you use any of the features listed on the second column of the table, you'll have to adapt your site.  

The changes that mostly affected or will affect the users are regarding Markdown, Highlighter and Collections. For the new flags, they are very welcome!

Let's take a look one by one on the overview below. We'll focus on markdown, highlighter and the gems mentioned above. We'll also give you a brief description on the other changes.

If the changes to adapt your project are substancial and you would like a **better alternative**, please check the [alternative methods](#){: .scroll-link data-id="alternative"} at the end of this post.

----

# Overview

## Markdown
{: .color_blue}

Moving from `redcarpet` or `rdiscount` to `kramdown` shouldn't be so painful. [Kramdown][kramdown] has a lot of interesting features. For example, you can easily apply in-line classes and IDs to your markdown text and you can add as many html tags you want to markdown files. Here you learn some [Markdown Tips & Tricks][] for Kramdown and here you can read more about [Kramdown Syntax][kramdown-syntax].

Now, if you were using **RedCloth** though, here you will find an [article][redcloth-post] where the author walk you through the process.

Let's get it done. In your `_config.yml` file, make sure you have this:

```yaml
markdown: kramdown
kramdown:
  input: GFM
```

`GFM` stands for [_GitHub Flavored Markdown_][GFM].

There is something boring that you'll need to deal with. Perhaps you used to add headings to your markdown files like this:

```
#My h1 heading

##My h2 heading
```

Now, with Kramdown, make sure you have a blank space between the `#` markup and the title itself, otherwise you will most likely face some output errors:

```
# My h1 heading

## My h2 heading
```

## Code Highlighter
{: .color_blue}

Now GitHub Pages **only** supports [Rouge] as code highlighter. If you used `pygments` before, don't worry, Rouge is fully compatible with it. So, the only thing to do is changing your `_config.yml`, making sure it has:

```yaml
highlighter: rouge
```

With Rouge, you won't need [Python] installed locally to work on your Jekyll site. It is fully written in Ruby. It also provides full  backtick support for highlighting your code.

Instead of writing the usual `{% raw %}{% highlight %}{% endraw %}` tag to every code block:

```liquid
{% raw %}{% highlight %} 
...code...
{% endhighlight %}{% endraw %}
```

You can do the same with backticks:

{% highlight md %}{% raw %}```html
...code...
```{% endraw %}{% endhighlight %} 

Here you'll find all [languages and lexers supported by Rouge][rouge-lang].

And you can also add line numbers:

{% highlight ruby linenos %}
def foo
  puts 'foo'
end
{% endhighlight %}

with the standard `{% raw %}{% highlight %}{% endraw %}` markup:

```liquid
{% raw %}{% highlight ruby linenos %}
def foo
  puts 'foo'
end
{% endhighlight %}{% endraw %}
```

If you want to display line numbers on every code block, you can easily do that by adding this line to your `_config.yml`:

```yaml
line_numbers: true
```

Note that both `{% raw %}{% highlight %}{% endraw %}` and backticks are fully supported by Rouge.

## Dropped Dependencies
{: .color_blue}

As we explained before, one of the major requirements for running Jekyll has dropped: [Python]. This saves us a lot of trouble, and makes Jekyll installation on Windows a lot easier. Also, all the following dependencies have dropped.

- &#8615; `jekyll-paginate` – Jekyll’s pagination solution from days past
- &#8615; `jekyll-coffeescript` – processing of CoffeeScript
- &#8615; `jekyll-gist` – the `gist` Liquid tag
- &#8615; `pygments.rb` – the Pygments highlighter
- &#8615; `redcarpet` – the Markdown processor
- &#8615; `toml` – an alternative to YAML for configuration files
- &#8615; `classifier-reborn` – for `site.related_posts`

As they are not required by default anymore, if your site uses any of this gems, you'll need to add them manually, otherwise your site most likely won't build or will break. Or even worst, it's already broken. But don't worry, all those changes have a workaround. 

### Jekyll-Gist
{: .color_gray}

A nice touch for code blocks is using embed [GitHub Gist Snippets][gist-virtua]:

<script src="https://gist.github.com/VirtuaCreative/ef47c25b7f8933dd78fcb0f848464dde.js"></script>

This can be done with a single `<script>` tag:

```html
<script src="https://gist.github.com/VirtuaCreative/ef47c25b7f8933dd78fcb0f848464dde.js"></script>
```

The gem `jekyll-gist` would allow us to simplify embed GitHub Gist Snippets, with just a simple tag like `{% raw %}{% gist <user/id> %}{% endraw %}`, where `<user/id>` is your `username/gist_id`. 

For example, the liquid tag below would reproduce the same result as we just did with the `<sript>` tag:

```liquid
{% raw %}{% gist VirtuaCreative/ef47c25b7f8933dd78fcb0f848464dde %}{% endraw %}
```

#### Troubleshooting `jekyll-gist`

When trying to use `jekyll-gist` locally, I've faced the error shown below.

```bash
Generating...
  Liquid Exception: SSL_connect returned=1 errno=0 state=SSLv3 read server certificate B: certificate verify failed in C:/Users/Me/websites/test/_posts/2016-03-30-code-blocks.markdown jekyll 3.0.3 | Error:  SSL_connect returned=1 errno=0 state=SSLv3 read server certificate B: certificate verify failed
```

After some research, I've noticed that it is a known issue [reported at GitHub issue tracker][issue-gist]. The bottom line is, `jekyll-gist` works on GitHub Pages, but (for me, on Win 7) the error persists locally. 


### Jekyll-Paginate
{: .color_gray}

Jekyll 3.x also dropped `jekyll-paginate`, which tons of Jekyll developers use frequently. But you can [add it back](#){: .scroll-link data-id="add-the-gems-back-with-bundler"} to your project and use it as before.

#### Troubleshooting `jekyll-paginate`

When I first tried to upgrade this blog from Jekyll 2.x to Jekyll 3.x, my posts were not displaying. I [reported the error][issue-paginator] and Parkr (who is a Jekyll core developer) helped me to find out what the issue relied on. The problem was serving Jekyll in the `--safe` mode (the method [recommended by GitHub][safe]). So, when I ran `bundle exec jekyll serve --safe` my posts didn't displayed within `{% raw %}{% for post in paginator.posts %}{% endraw %}` at all. But, by running `bundle exec jekyll serve` they were back there, exactly as they should be.

### Add the gems back with Bundler
{: .color_gray}

The good news is, any of those gems can be added back to our projects. :smiley: 

Actually, the best and safest way to build Jekyll locally is using [Bundler]. For Jekyll sites hosted by GitHub Pages, the only required gem is `github-pages`. Bundler is a fantastic dependency manager, when we use it, we don't need to worry about dependencies anymore. 

#### Serving Jekyll with Bundler

Follow these steps:

\- 1. Install Bundler locally `gem install bundler`

\- 2. On a terminal, navigate to your project `cd path/to/project` 

\- 3. On your `_config.yml`, add the `gems` you want as an array:

```yaml
gems:
  - jekyll-paginate
  - jekyll-gist
```

\- 4. Create a `Gemfile` (without any extensions) with the following content:

```ruby
source 'https://rubygems.org'
gem 'github-pages'
gem 'jekyll-paginate'
gem 'jekyll-gist'
```

\- 5. Run `bundle install` 

\- 6. Serve Jekyll with Bundler `bundle exec jekyll serve --watch`

You're good to go, then! You can add any flag to the last command. E.g. `bundle exec jekyll serve --watch --incremental --baseurl ""`. Once and awhile, run `bundle update` on your project to make sure all gems are up to date.

Of course, you can add more gems to your `Gemfile` if you need. For example, on this blog we use `jemoji` and `jekyll-mentions` too. [Here][gh-versions] you'll find a list of all gems whitelisted by GitHub Pages.

## Collections
{: .color_blue}

This is just a brief description. Using collections has become a little better in terms of its logic: `site.collections` is an array of `collections`, thus:

`collection[0]` becomes `collection.label`

`collection[1]` becomes `collection`

To know more about it, please read the doc [Jekyll - Upgrading from 2 to 3](http://jekyllrb.com/docs/upgrading/2-to-3/#sitecollections-has-changed).

## Post Date
{: .color_blue}

The future flag allows post authors to give the post a date in the future and to have it excluded from the build until the system time is equal or after the post time. If you want to create posts with future dates, you will need to add the flag `--future` when serving Jekyll, as in `jekyll serve --future`. Alternatively, you can enable it on your `_config.yml`:

```yaml
future: true
```
 
## Liquid Profiler
{: .color_blue}

By adding the flag `--profile` to the `build` or `serve` command, Jekyll will analyze your site's build time, so you can see exactly where things can be sped up, ensuring you spend more time authoring content, and less time waiting for your site to build.

## Incremental
{: .color_blue}

Our builds can also speed up considerably with by adding the flag `--incremental`. This will only re-build the files that had been changed. It means it won't build everything again. For example, if we are writing a post, running `jekyll serve --incremental` will re-build the post page only, not the entire site. Alternatively, you can set `incremental: true` in your `_config.yml`.

## Relative Permalinks
{: .color_blue}

Jekyll 3.x does **not** support relative permalinks anymore. If you have on your `_config.yml` the following line, you'll need to remove it.

```yaml
relative_permalinks: true
```

## Permalinks Trailing Slash
{: .color_blue}

In Jekyll 2, any URL constructed from the `permalink:` variable had a trailing slash (`/`) added to it automatically. Jekyll 3 no longer adds trailing slashes automatically to `permalink:` URLs.

Basically, instead of, for example:

```yaml
permalink: /:year-:month-:day-:title
```

you'll need to make sure it has a trailing slash at the end, otherwise you might face a lot of 404 errors:

```yaml
permalink: /:year-:month-:day-:title/
```

## Alternative Methods
{: #alternative}

You might ask yourself if there is a better way to walk trough this process. The answer is: yes and no! :grin: If you want to do everything by the book, no. If you want a smart workaround, yes. I see three alternatives, described below.

### 1. Upload the `_site` folder
{: .color_gray}

Instead of letting GitHub build your site for you, you can upload **only** the `_site` folder. By doing this, you will push to your repository the site pre-compiled from your local machine. It's a quick way out. And there is a plus here: you can use **any** Jekyll Plugin available (building locally) and upload the static site only.

### 2. Travis CI
{: .color_gray}

You can use [Travis CI] to trigger a non-default build for you. But it's a little complicated if you don't know anything about it so far. It's a quick way out too, if you know what you're doing! 

### 3. GitLab Pages
{: .color_gray}

I really think it's worth considering to migrate your site to [GitLab Pages]. [GitLab] is a `git` remote repository manager, with extended functionality. You can create a [free account][gitlab-sign-up] at GitLab.com and enjoy its features, including unlimited free private repos. 

The thing is, with [GitLab Pages] you can choose which Jekyll version you want your project to be build with (you can do a lot more that that, actually). E.g. on [this project][carte-noire], the Jekyll version building this [site][carte-noire-site] is 2.5.3. So, despite of any Jekyll upgrades, we wouldn't be obligated to change anything at all on our sites! The choice of upgrading or not, would be up to ourselves only.

If your project on GitHub already has a `CNAME` pointing to your custom domain, you'd need just to import it to GitLab and add a `.gitlab-ci.yml` configuration file like [this][carte-noire-ci]. Then you just specify the Jekyll version on your `Gemfile` and that's it! No stress, no redirects, no problems! :+1:

[Setting up your site on GitLab Pages][blog-gitlab-pages] will be the subject of our very [next post](#){: .scroll-link data-id="next-post"}. We'll try to bring you video tutorials to make it easier to follow through.

We'll migrate this blog to GitLab Pages soon! :smiley:

## Questions?

Please, let us know if you have any questions by commenting below. If you want to ask questions to the Jekyll Team directly, they have a forum for that, called [Jekyll Talk].

## Contribute

Did we miss something? Spotted an error? Please add a [new issue on GitHub][blog-issue-tracker] to let us know! Any contribution is more than welcome!

## Next Post

On our next post we will bring you an alternative for GitHub Pages, **[GitLab Pages]**. It's a fantastic alternative to GitHub itself, actually. They both have pros and cons, but [GitLab] is really worth trying. We'll discuss it soon! So, stay tunned for our updates!! Follow us on [Twitter] and/or subscribe to our [YouTube Channel]!

## Related Articles

<ul>
{% for art in site.data.articles.github %}
  <li>
    <a href="{{ art.url }}">&#8674; {{ art.title }}</a>
  </li>
{% endfor %}
{% for art in site.data.articles.markdown %}
  <li>
    <a href="{{ art.url }}">&#8674; {{ art.title }}</a>
  </li>
{% endfor %}
</ul>

## References 

- &#9734; [GitHub]
- &#9734; [GitHub Pages]
- &#9734; [Jekyll - Upgrading from 2.x for 3.x][jek-full-2to3]
- &#9734; [Jekyll upgrade on GitHub Pages][gh-jek-3]
- &#9734; [Jekyll Docs][jek-docs]
- &#9734; [Travis CI]
- &#9734; [GitLab Pages]

[jekyll-3]: https://jekyllrb.com/news/2015/10/26/jekyll-3-0-released/
[Jekyll Talk]: https://talk.jekyllrb.com
[jek-full-2to3]: http://jekyllrb.com/docs/upgrading/2-to-3/
[jek-docs]: https://jekyllrb.com/docs/
[redcloth-post]: https://github.com/blog/2115-upgrading-your-textile-posts-to-markdown
[gh-post]: https://github.com/blog/2136-a-look-behind-our-decision-to-standardize-on-a-single-markdown-engine-for-github-pages

[gh-versions]: https://pages.github.com/versions/
[gem-jek-240]: https://rubygems.org/gems/jekyll/versions/2.4.0
[gem-jek-303]: https://rubygems.org/gems/jekyll/versions/3.0.3
[gh-jek-3]: https://github.com/blog/2100-github-pages-now-faster-and-simpler-with-jekyll-3-0
[safe]: https://help.github.com/articles/setting-up-your-pages-site-locally-with-jekyll/#installing-the-github-pages-gem

[issue-paginator]: https://talk.jekyllrb.com/t/jekyll-3-x-with-github-pages/1832/12
[issue-gist]: https://github.com/jekyll/jekyll-gist/issues/30

[blog-issue-tracker]: https://github.com/VirtuaCreative/blog/issues
[blog-gitlab-pages]: https://about.gitlab.com/2016/04/07/gitlab-pages-setup/
[Bundler]: http://bundler.io
[carte-noire]: https://gitlab.com/jekyll-themes/carte-noire
[carte-noire-ci]: https://gitlab.com/jekyll-themes/carte-noire/blob/master/.gitlab-ci.yml
[carte-noire-site]: https://jekyll-themes.gitlab.io/carte-noire/
[gist-virtua]: https://gist.github.com/VirtuaCreative/ef47c25b7f8933dd78fcb0f848464dde
[GFM]: https://help.github.com/articles/about-writing-and-formatting-on-github/
[GitHub]: {{ site.data.url.git.home }}
[GitHub Pages]: {{ site.data.url.git.pages }}
[GitLab]: https://about.gitlab.com
[gitlab-sign-up]: https://gitlab.com/users/sign_in
[GitLab Pages]: https://pages.gitlab.io
[gitlab-pages-docs]: http://doc.gitlab.com/ee/pages/README.html
[kramdown]: http://kramdown.gettalong.org/
[kramdown-syntax]: http://kramdown.gettalong.org/quickref.html
[Python]: {{ site.data.url.environments.python }}
[Rouge]: https://github.com/jneen/rouge
[rouge-lang]: {{ site.data.url.markdown.rouge_lang }}
[Ruby]: {{ site.data.url.environments.ruby }}
[Travis CI]: https://travis-ci.org/

[Twitter]: {{ site.data.url.virtua.twitter }}
[YouTube Channel]: {{ site.data.url.virtua.youtube }}

[Markdown Tips & Tricks]: http://blog.virtuacreative.com.br/markdown-tips-and-tricks.html
