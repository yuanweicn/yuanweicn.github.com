---
layout: post
title: "Working with Mathjax"
date: 2013-07-09 22:06
comments: true
categories: [Latex] 

---

$$\prod_{p}\frac{1}{1-\frac{1}{p^{s}}} = \sum_{n=1}^{\infty} \frac{1}{n^{s}}$$

Install Kramdown
{% codeblock %}
gem install kramdown
{% endcodeblock %}

Change settings in _config.yml.
markdown: rdiscount --> markdown: kramdown

Change gem 'ridiscount' to gem 'kramdown' in Gemfile.

Put MathJax CDN and configs in source/_layouts/default.html.

{% codeblock lang:html %}
<!-- mathjax config similar to math.stackexchange -->
<script type="text/x-mathjax-config">
MathJax.Hub.Config({
  jax: ["input/TeX", "output/HTML-CSS"],
  tex2jax: {
    inlineMath: [ ['$', '$'] ],
    displayMath: [ ['$$', '$$']],
    processEscapes: true,
    skipTags: ['script', 'noscript', 'style', 'textarea', 'pre', 'code']
  },
  messageStyle: "none",
  "HTML-CSS": { preferredFont: "TeX", availableFonts: ["STIX","TeX"] }
});
</script>
<script src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML" type="text/javascript"></script>
{% endcodeblock %}

Fix MathJax right-click bug.

When you right-click on a MathJax formula, the browser becomes white.
To fix it, make the following change in sass/base/_theme.scss.

{% codeblock lang:css %}
body {
  > div {
    background: $sidebar-bg $noise-bg;
{% endcodeblock %}

to

{% codeblock lang:css %}
body {
  > div#main {
    background: $sidebar-bg $noise-bg;
{% endcodeblock %}

本文中的方法来自[Felix's blog](http://www.idryman.org/blog/2012/03/10/writing-math-equations-on-octopress)
