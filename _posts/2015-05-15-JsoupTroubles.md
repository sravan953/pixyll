---
layout:     post
title:      Jsoup Troubles
date:       2015-05-15
summary:
categories: android java
---

Of late, I’ve been working on a project that scrapes content off a webpage. To elaborate on what I’ve been working on: it’s an [Android app](https://github.com/sravan953/Fast-VTU-Results) that fetches university results from my university’s webpage.

Naturally, I turned to Jsoup. While it’s an amazing library for HTML scraping, its limitations quickly become a barrier to the bigger things you might have planned on doing with it, because it’s next to impossible to find any useful data on a static webpage.

# 1 - JavaScript content

If the page you’re scraping data from has dynamically loaded content, courtesy JavaScript, then you’ve hit a dead end. Jsoup is a HTML scraper, you’re better off working with Selenium or HTMLUnit. Just in case you’d like to try your luck, you could try faking the user agent:

{% highlight ruby %}
Document doc = Jsoup.connect(URL).userAgent("Chrome/41.0.2228.0").get();
{% end highlight %}

# 2 - Memory issues

More often than not, Jsoup never downloaded the complete source code of the webpage I wanted to scrap data from. Even using the `maxBodySize` method made no difference:

{% highlight ruby %}
Document doc = Jsoup.connect(URL).userAgent("Chrome/41.0.2228.0").maxBodySize(Integer.MAX_VALUE).get();
{% end highight %}

Hoping to find fixes!
