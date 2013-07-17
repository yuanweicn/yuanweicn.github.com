---
layout: post
title: "Hello world!"
date: 2013-07-08 21:30
comments: true
categories: [Octopress]
--- 
**My Very First Octopress Blog**

How to blog with Octopress:

1. Generate a new post:
{% codeblock %}
rake new_post["Hello world"]
# create source/_post/2013-07-08-Hello-world.markdown
{% endcodeblock %}

2. Edit the new post with your favorite editor, i.e. vim.

3. Generate the page, preview and deploy to github:
{% codeblock %}
rake generate
rake preview
rake deploy
{% endcodeblock %}

4. commit the source:
{% codeblock %}
git add .
git commit -m 'update message'
git push origin source
{% endcodeblock %}

Some tips:

###CodeBlock
`Codeblock` will plug formatted codes into your blog.
Syntex

	<% codeblock [title] [lang:language] [url] [link text] %>
	code snippet
	<% endcodeblock %>
