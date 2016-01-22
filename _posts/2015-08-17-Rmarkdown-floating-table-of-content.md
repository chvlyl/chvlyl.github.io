---
layout: post
title: "Rmarkdown: floating table of content"
date: 2015-08-17
---

### Floating table of content  
I'd like to add a floating table of content to my HTML output generated by Rmarkdown. First, create a css file called "style.css" with following cotent 
and put it under the same folder as Rmd file.  
```
#TOC {
  position: fixed;
  left: 0;
  top: 0;
  width: 400px;
  height: 100%;
  overflow:auto;
}
```
In Rmd YAML header, add css: style.css, for example  
```
---
title: "Untitled"
author: "Eric Z Chen"
date: "August 17, 2015"
output: 
  html_document: 
    css: style.css
    highlight: kate
    number_sections: yes
    theme: spacelab
    toc: yes
---
```


### Change the width of the HTML output  
I have some a wide matrix output in my HTML output and I'd like to put it in one row. Add the following content to the style.css file  
```
body .main-container {
  max-width: 1280px;
}
```
Also, change the main body width  
```
body {
  max-width: 1200px;
  margin: auto;
  margin-left:410px;
  line-height: 20px;
}
```
Change the Rmd YAML to include the css if you didn't do so.  