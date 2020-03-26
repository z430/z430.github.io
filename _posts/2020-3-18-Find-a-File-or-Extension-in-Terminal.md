---
layout: post
title: Find Files or Extension in Terminal (Ubuntu/Mac*) and Do Something
---

When you don't have time to `ls` through all unix folder to find some file extention, use this.

[<img src="https://www.howtogeek.com/wp-content/uploads/2012/03/ls.png" style="width: 400px;"/>]({{ site.baseurl }}/)

## Find Extensions or Files or Whatever

<pre><code>
find [directory] -name '*[file/extenstion]'
</code></pre>
<!--excerpt-->
## Do Some Action with Find

<pre><code>
find [directory] -name '*[file/extenstion]' -exec [linux command(sorry windows :( )] '{}' ';'
</code></pre>

Just That XD