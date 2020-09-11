---
layout: post
title: Reusable iframe Widget
author: Paige
tags: [service portal, widget]
---

I know, I don’t recommend this method at all.  But on occasion we all must do things we don’t like.  I’ve seen this come up a few times in the community and decided to throw together a simple how to.  Adding an iframe to the portal is easy.  Below I walk you through creating a simple widget that allows you to set the URL of the iframe in the instance options.

## Create a Widget

## Add a little code

Throw some html to load the iframe.  Note that I am pointing it at “{{options.url}}”.  This is important as it is what allows you to set the url that the iframe is pointing at in the widget instance options, making the widget reusable. 

```HTML
<iframe src="{{::c.options.url}}"></iframe>
```
