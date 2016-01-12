---
layout: post
title: "Web development"
date: 2016-01-11
---


I'm learning web development and here are my study notes.

## Part 1: How to earn money by making websites?

### Brand Yourself
-. Match your personal expertise to your website so that your website can be useful to other people. Your website will be more than a website.
-. Build your online reputation by advertising yourself and your website on Twitter, Facebook, LinkedIn , personal website and email.

### Use Freelance Websites
-. www.freelancer.com/
-. https://www.upwork.com
-. https://www.peopleperhour.com/
-. https://www.elance.com/
-. http://www.guru.com/
-. http://www.gofreelance.com/
-. https://fbooks.wpengine.com/blog/freelance-jobs/
1. At the beginning, focus on gainning good reviews rather than earning money. Therefore it is necessary to start with small project and bid with lower rate.
2. Use your real identity to create the profile and put your personal website, LinkedIn profile and Twitter to you. 
3. Bid for small project and finish it.


### Use Wordpress to build attractive website
1. Get familiar with the templates and themes at http://themeforest.net/
2. Build your own website with those website templates and themes. Use your website as the showcase.
3. Create websites for friends and other people. You can also go to whatever forums to make websites for people over there. Use these websites as your showcase.
4. Find some poorly designed pages for some local small business and redo them. Send the design to them. Add these websites to your showcase too.
5. After gain enough showcase, bid on those website development jobs on the freelance site.


### Make the profitable website
1. If you have spent time looking for something and you didn't find it, then someone else may have done the same thing. Or if you feel something you have just done can be done more easily, then probably someone else also has the same feeling. This is a good start point to make your profitable website. The needs of majority people are satified my mainstream product but there are always some specific needs from a small group people. You should target those people.
2. Build a preliminary website to make your idea work. Add google analytics to your website to monitor your website traffic.
3. Find out what are the core features that people are willing to pay for. Choose a small subset of people to try out and ask them for feedback. Improve your website until you get a great number of people who are willing to pay for it. Keep doing this.
4. Put relevant ads on your website.

## Part 2: Basic web development

### Buy a domain name and hosting server

## Part 3:  HTML

### A usefull website for code debug
1. Use www.jsbin.com for HTML code visualization.

### General structure of HTML page
1. The first line is: ```<!doctype html>```   
This is to tell the browser that this is a HTML file.
2. The HTML file includes paired tages such as 

~~~
<html>
<head><title></title></head>
<body><div><h></h></div></body>
</html>
~~~
```/tagname``` means closing tag. ```<div>``` is the tag for division of the page and ```<h>``` is the tag for paragraph.

3. Header tag 
```<h1>``` is the biggest and ```<h6>``` is the smallest. ```<h7>``` will go back to the normal text size.

4. Paragraph tag
HTML files ignore line break and multiple spaces. Therefore text should be put into <p> tag. There is padding space between paragraphs. If you want a line break in the paragraph, use the <br /> tag, which is a self-closing tag. Use <hr /> to add a horizontal line.

5. Text formatting tag
-. ```<strong>``` is for bold text. Do not use ```<b>```  
-. ```<italics>``` is for italic text  
-. ```<u>``` for underline text  
-. ```<strike>``` for strikethrough text  

6. Unordered list tag
```<ul><li></li></ul>```: ```<li>``` is for each item

7. Ordered list tag
```<ol><li></li></ol>```

8. Image
```<img src="figure location" width="200" height="500" />```. This is also a self-closing tag. The width and height is measured in pixel

9. Forms

~~~
<form>
<input type="text" value="example" placeholder="disappear automatically" /> 
<input type="radio" name="color"/> 
<input type="checkbox"/> 
<textarea></textarea>
<select><option></option></select>
<input type="submit" value="Click here"/> 
</form>
~~~

-. ```<input>``` is self-closing. 
-. ```<textarea>``` is bigger than ```<input>```. 
-. ```<select>``` and ```<option>``` are for drop-down list.
-. ```<input type="radio" />``` is for button selection. Use "name" to group the options so that only one button can be selected.
-. ```<input type="radio" />``` is for multiple selections.
-. ```<input type="submit">``` is for submitting the form. This will gererate a string. Use "name" to give the variable in the form a name. Need PHP or JavaScript to process the form. 

10. Links
```<a href="link">text</a>``` for hyperlink reference.  
```<a name="anchor"/>``` is for anchor in the page.  ```<a href="#anchor">text</a>``` will go to that anchor.

11. Tables

~~~
<Table>
<tr>><th></th><tr>
<tr><td></td><tr>
</Table>
~~~

```<tr>``` is for a new table row. ```<th>``` and ```<td>``` are for table header and table data respectively.

12. HTML entities
``&alt:``` is for "less than" sign <. Check [http://www.w3schools.com](http://www.w3schools.com/html/html_entities.asp) for more.

13. Embed another page
```<iframe src="youtubelink"><iframe>```


## Part 3:  CSS

CSS is the style of the website

### Inline CSS
1. Inline CSS is not recommonded. 
```<p style="color:blue;font-size:200%">```

### Internal CSS

1. Internal CSS

~~~
<head>
<style type="text/css">
	p{
	color:green;
	}
</style>
</head>
~~~

The ```p{}``` in ```<style>``` will add style to the text in <p>

2. Class
If you want to add style to a specific text but not all text with the same tag, you can use class. Define a class in the body such as ```<p class="underline large"></p>```. Then in the CSS style define:

~~~
<style type="text/css">
	.large{
		font-size:300%;
	}
	.underline{
		text-decoration:underline;
	}
</style>
~~~

Use ```.``` to refer to the class. In this way, the CSS style will only be added to the ```<p>``` tag with ```large``` class. Multiple classes can be added to one tag.

3. Id
Use ```class``` for multiple elements (the class will be used multiple times) and ```id``` for just one element (the id will be used only once). In CSS style, use ```#``` to refer to the id.

~~~
<style type="text/css">
	#large{
		font-size:300%;
	}
</style>
~~~

4. Div
A division of the page. In the body, you can divide the page into different sections. Use class to define different divs.

~~~
<div class="bluebox">
</div>
~~~

Then define the properties of each section:

~~~
<style type="text/css">
	.bluebox{
		background-color:blue;
		width:100px;
		height:300px;
	}
</style>
~~~

5. Color
Use [HTML color code](http://html-color-codes.info/) for color code information. Remeber to put ```#``` before the code.

~~~
<style type="text/css">
	.bluebox{
		background-color:#FFFFFF;
		width:100px;
		height:300px;
	}
</style>
~~~

6. Floating

~~~
<style type="text/css">
	.bluebox{
		float:left;
	}
</style>
~~~

Add an empty div between the floating figures and text t separate them.

~~~
<body>
<div class="clear"></div>
</body>
~~~

~~~
<style type="text/css">
	.clear{
		clear:both;
	}
</style>
~~~

7. Positioning
Use ```left:100px``` Move to the right 100px because it add 100px margin to the left and move it to the right. Use ```z-index``` to set which figure is on the top of the other. ```position:fixed``` will fix the figure in the browser.

~~~
<style type="text/css">
	.bluebox{
		position:relative
		left:100px
		z-index:1
	}
</style>
~~~

8. Margin
Add margin to the top, right, bottom, left (closewise order).

~~~
<style type="text/css">
	.bluebox{
		margin:10px 20px 30px 40px;
		margin-left:10px;
	}
</style>
~~~

9. Padding
Padding is the space between the text and background box. 

~~~
<style type="text/css">
	.bluebox{
		padding:10px 20px 30px 40px;
	}
</style>
~~~

Some of the tags such as ```<p>``` has it own buit-in padding and margin settings. Setting the padding will add extra space to the default padding space. Also, adding padding will add to the width and height of the div setting.

10. Borders
Use ```border: width color type``` to set the width, color and type. Use ```border-radius``` to make the round corner.

~~~
<style type="text/css">
	.bluebox{
		border:5px balck solid;
		border-radius:10px;
	}
</style>
~~~

11. Fonts

Check [CSS Font](http://www.w3schools.com/css/css_font.asp) for more information. In the font-family, the latter options is the backup for the previous options so that if the browser can not the find the previous font, it will use the latter one.

~~~
<style type="text/css">
	p {
		font-family: "Times New Roman", Times, serif;
		font-weight:bold;
		font-style:italic;
		color:green;
		font-size:200%;
		text-align:center;
	}
</style>
~~~


12. Links

Change the color of the visited link and the size of the link.

~~~
<style type="text/css">
	a:visited{
		color:green;
	}
	a:hover{
		font-size:50px;
	}
</style>
~~~


13. Container
Put the whole page in the container so that the style of whole page can be controlled.

~~~
<body>
<div id="container">
</div>
</body>
~~~
