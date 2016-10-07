---
layout:     post
title: "Make bundler super fast"
subtitle:   "In category Performance for RoR developers"
date:       2015-05-11 12:00:00
author:     "Barbu Bujor"
header-img: "img/post-bg-06.jpg"
---

<h2>Parallel gem installs </h2>
 In our work as developers, we encounter situations where the software runs too slow.
 We don't want our productivity to decrease - as we dont't want to enter into rabit holes which can delay us even further.
 <br> A clear and simple solution for you :

<b> Bundler 1.4.0</b> adds support for parallel installation. You can pass in --jobs SIZE as a parameter to bundle config1. I recommend setting the size to one less the number of CPU cores on your machine.

<b>Benchmark</b>. <br>
Before:

{% highlight ruby %}
$ rvm gemset use j1 --create
Using ruby-2.0.0-p247 with gemset j1
$ time bundle install
# ... snip ...
bundle install  5.75s user 1.76s system 24% cpu 30.679 total
{% endhighlight %}

After:

{% highlight ruby %}
$ rvm gemset use j8 --create
Using ruby-2.0.0-p247 with gemset j8
$ bundle config --global --jobs 8
$ time bundle install
# ... snip ...
bundle install  7.48s user 2.59s system 86% cpu 11.681 total
{% endhighlight %}

Obtained a 62% improvement using 8 CPU cores

Awesome right ? To use this now we Just install a prerelease version of Bundler, and we'll be good to go:

{% highlight ruby %}
gem install bundler --pre
{% endhighlight %}

Then, configure Bundler to parallelize on your machine globally:

{% highlight ruby %}
bundle config --global jobs 7
{% endhighlight %}


Tried to set the size to be equal to the number of your CPU cores. However, it turned out that setting the number to be N-1 will yield a better result.

<blockquote>The dreams of yesterday are the hopes of today and the reality of tomorrow. Science has not yet mastered prophecy. We predict too much for the next year and yet far too little for the next ten.</blockquote>
