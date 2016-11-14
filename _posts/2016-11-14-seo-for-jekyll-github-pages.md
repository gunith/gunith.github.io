---
layout: post
title: How to do Search Engine Optimizations for Jekyll generated GitHub page
published: true
categories:
- HTML
- Jekyll
tags:
- programming
- code
- SEO
- Facebook
- Twitter
- LinkedIn
- GitHub Pages
- Jekyll
---
When I started working on this website, which uses GitHub Pages with Jekyll, I based it on [this awesome template](https://github.com/barryclark/jekyll-now). However, one downside was that the site wasn't optimized for Search Engines. So I started looking for solutions in Jekyll.

## Using [Jekyll SEO Tag](https://github.com/jekyll/jekyll-seo-tag)

For a site which has nothing, this is a good starting point. As instructed in the [site](https://github.com/jekyll/jekyll-seo-tag), I added some optimizations. As a result my header generation looked like this, which is pretty impressive. 

```html
<!-- Begin Jekyll SEO tag v2.1.0 -->
<meta property="og:title" content="How to setup ElasticSearch and Kibana using Docker" />
<meta name="description" content="So I was trying to learn elasticsearch for work. So I was looking for some tutorials and I came across this official tutorial. I was going to setup elasticsearch and kibana for it and I thought it’s better to do this in Docker, since it’s easy to use. The issue with Elasticsearch and Kibana is, the two should be linked and that has to be defined by Docker. I had some problems with it and I even posted it on StackOverflow. As per the accepted answer by Andreas Jägle, there are two solutions." />
<meta property="og:description" content="So I was trying to learn elasticsearch for work. So I was looking for some tutorials and I came across this official tutorial. I was going to setup elasticsearch and kibana for it and I thought it’s better to do this in Docker, since it’s easy to use. The issue with Elasticsearch and Kibana is, the two should be linked and that has to be defined by Docker. I had some problems with it and I even posted it on StackOverflow. As per the accepted answer by Andreas Jägle, there are two solutions." />
<link rel="canonical" href="http://gunith.github.io/docker-kibana-elasticsearch/" />
<meta property="og:url" content="http://gunith.github.io/docker-kibana-elasticsearch/" />
<meta property="og:site_name" content="Coder’s Block" />
<meta property="og:type" content="article" />
<meta property="article:published_time" content="2016-11-01T00:00:00+00:00" />
<script type="application/ld+json">
{"@context": "http://schema.org",
"@type": "BlogPosting",
"headline": "How to setup ElasticSearch and Kibana using Docker",
"datePublished": "2016-11-01T00:00:00+00:00",
"description": "So I was trying to learn elasticsearch for work. So I was looking for some tutorials and I came across this official tutorial. I was going to setup elasticsearch and kibana for it and I thought it’s better to do this in Docker, since it’s easy to use. The issue with Elasticsearch and Kibana is, the two should be linked and that has to be defined by Docker. I had some problems with it and I even posted it on StackOverflow. As per the accepted answer by Andreas Jägle, there are two solutions.",
"publisher": {"@type": "Organization",
"logo": {"@type": "ImageObject",
"url": "https://avatars3.githubusercontent.com/u/1032108?v=3&amp;s=466"}},
"url": "http://gunith.github.io/docker-kibana-elasticsearch/"}</script>
<!-- End Jekyll SEO tag -->
```

As you can see it took a lot from `_config.yml` and also dates. Also, it added a lot of Facebook related meta tags which is pretty cool.

However, I noticed that some of the useful SEO could be improved. 

# Keywords Meta tag

For instance, I used to have a hosted Wordpress as my former blog. So I (thankfully) have a lot of articles [exported (thankfully and really nicely)](http://import.jekyllrb.com/docs/wordpress/). It has nicely retained the tags that I used in Wordpress. 

So, I wrote a small script that I include in my `_includes/meta.html`, which is included in the header of my HTML page. It goes like this:

```markdown
{% raw %}{% if page.tags %}<meta name="keywords" content="{% for tag in page.tags %}{{ tag }}, {% endfor %}"/>{% endif %}{% endraw %}
```

The output looks like this,

```html
<meta name="keywords" content="programming, code, javascript, coding, validation, single quotes, double quotes, character codes, "/>
```

Voila!
