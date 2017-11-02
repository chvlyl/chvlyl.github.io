---
layout: post
title: "GitHub personal website setup"
comments: true
date: 2015-03-09
---

Step 1: setup an account in GitHub:  
  1. Go to [GitHub](https://github.com/).  
  2. Create an account in GitHub.  
  3. Create a repository username.github.io, replacing username with your GitHub username.  
  4. I used the website templates from [Jonathan Mcglone](http://jmcglone.com/guides/github-pages/) and [Yihui Xie](http://yihui.name/).  
  5. Copy the template into your github repository. You have to learn some github basics about how to push a file into the respository.   


Step 2: setup the custom domain with GoDaddy:  
  1. Go to [GoDaddy](www.godaddy.com) and buy your own domain name (mine is statchen.com).  
  2. Go to GoDaddy **Zone File Editor**:  
  3. At **A(Host)** section add `Host:@ Points to: 192.30.252.153`  and `Host:@ Points to: 192.30.252.154`  
  4. At **CNAME (Alias)** section add `Host:www to: chvlyl.github.io`  
  5. Go to GitHub, add a file called CNAME with content `statchen.com`  
  6. I set the link in the layout to my GiHub website link chvlyl.github.io and this caused some problems. I changed the link to statchen.com and then problem was solved.     


Step 3: modify the index.md files from the template (this is the main website):  
  1. In the YAML header of the .md file, there must be a space after semicolon.  
  Wrong:  
   `layout:default`  
  Correct:  
   `layout: default`   
  2. Create a new line: just type two or more spaces after the line.  
  3. Math equation support:  use \\ begin\{equation\} and \\end\{equation\}


Step 4: update changes: 
git add README.md
git commit -m 'Add README.md'
git push -u origin master

 
Step 5: run Jekyll:  
Run `jekyll serve --detach` in the website home folder to setup the local server. You can use `http://127.0.0.1:4000/` to access the website on the local web browser.

Step 6: add new pages on the main website:  
In the `_layouts` folder, edit the layout html file you use, for example `default.html`. 

Step 7: allow comments to the blog posts
1. Go to [Disqus](https://disqus.com/) and create an account. After signup, click settings->Add Disqus to a site and flollow the instructions to add your website. You only need to create a site name, which will show up above the comments area. Disqus will tell you the usename. You don't need to copy the code from the website. Instead, do the following steps.
2. In the _layouts/default.html add 
{% highlight python %}
{% raw %}
{% include comments.html %}
{% endraw %}
{% endhighlight %}
 

3. Then create a file _includes/comments.html and following code to the file. Remember to change ```<USERNAME>``` in the above code to your Disqus username.

{% highlight html %}

{% if page.comments %}
<!-- Add Disqus comments. -->
<div id="disqus_thread"></div>
<script type="text/javascript">
  
  var disqus_shortname = '<USERNAME>'; 
  var disqus_identifier = "{{ site.disqusid }}{{ page.url | replace:'index.html','' }}";

  (function() {
    var dsq = document.createElement('script'); dsq.type = 'text/javascript'; dsq.async = true;
    dsq.src = '//' + disqus_shortname + '.disqus.com/embed.js';
    (document.getElementsByTagName('head')[0] || document.getElementsByTagName('body')[0]).appendChild(dsq);
  })();
</script>
<noscript>Please enable JavaScript to view the <a href="http://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>
<a href="http://disqus.com" class="dsq-brlink">comments powered by <span class="logo-disqus">Disqus</span></a>
{% endif %}

{% endhighlight %}



4. Add ```comments: true``` to the YAML header of the post that you want to include the comments.


## Reference
1. [Joshua Lande's post about github blog setup](http://joshualande.com/jekyll-github-pages-poole/)
2. [Jonthan Mcglone's post about github website setup](http://jmcglone.com/guides/github-pages/)


