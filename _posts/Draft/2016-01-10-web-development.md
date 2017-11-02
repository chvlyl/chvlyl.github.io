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
-. Add your new personal website to search engines such as Google. Check [this website](http://www.w3schools.com/website/web_search.asp) for details.

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
This is to tell the browser that this is a HTML file. It does not have a closing tag.
2. The HTML file includes two parts, which are ```<head>``` and ```<body>```. They are paired tages such as 

~~~
<html>
<head><title></title></head>
<body><div><h></h></div></body>
</html>
~~~
```/tagname``` means closing tag. ```<div>``` is the tag for division of the page and ```<h>``` is the tag for paragraph.

```<head>``` includes all the necessary information for the page but does not show up on the page such as CSS style and page title. All the contents showed on the page are included in ```<body>```.

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

14. Comments
```<!-- comment -->``` 

## Part 4:  CSS

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

Both the class name or tag name can be used as the selector. The following code will add style to tag ```<p>``` with ```class="large"```

~~~
<style type="text/css">
	.large p{
		font-size:300%;
	}
</style>
~~~

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

Note that you have to set ```position:relative``` before setting the position.

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

```margin:auto``` will take the space as much as possible. So if you want to move the element to the far left, then set ```margin-right:auto``` to take the right margin as much as possible. Set both ```margin-left:auto``` and ```margin-right:auto``` will center the element.

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


14. Block
The elements in HTML are treated as boxes by css. Use ```display="block"```or ``` or ```"display=inline"``` to control them. "block" means the elements will be arranged in new lines and "inline" means in the same line. For example, ```"display=inline"``` can be used to put lists in the one line.


<link href="font.css" rel="stylesheet" style="text/css">
<link href="style.css" rel="stylesheet">
The order of the css links does matter. The browser will load them in order and the latter one will change the effect of the previous one.


In the above examples, one has to manually modify the css to get the desired style. It's tedious and requires a lot work. A very useful pacakge called ["]Bootstrap](http://getbootstrap.com/) has defined a lot of beautiful css styles in terms of class. Therefore, one can just use those classes in the HTML file and no need to re-implement the css style. 


## Part 5: Javascript
Javascript can be used to make the website interact with the users. For example, when the users submit something, the browser can use Javascript code to calculate and then return something to the users. This can make the website alive.


### Include Javascript in HTML
1. Internal JavaScript
Use ```<script type="text/javascript"> javascript here </script>```. The scripts can be put either in head or in body. 

2. Save the JavaScript to code.js and then include it in the HTML by ```<script type="taxt/javascript" scr="code.js"></script>```

### Basic syntax
1. Comments
Use ```//``` for comments.

2. Confirm
Use ```confirm("message");``` to pop out a confirmation message page to the user. Use ```alert(message)``` for an alert.

3. Prompt
Use ```prompt("message");``` to ask the user to input something.

4. Print
In Javascript, the ```print``` equivalent syntax is ```console.log(somethingtoprint)```. For example, ```console.log(1+1)``` and ```console.log("Hello")```. However, the printed content will not be displayed on the web. In Chrome, click View -> Developer -> JavaScript Console to see the output.

5. if-else
They are just the same as C style if-else.

6. substring
The string index starts at 0. ```"Hello".substring(0,1);``` will get "H". It is similar to range function in Python.

7. Variable
Use ```var varName = something;``` to define a variable. Similar to Python, no need to define the type of the data. For example

~~~
var varName = 1;
var varName = "Hello";
var varName = true;
var varName = prompt("message");
~~~

8. Equal comparison
```==``` means equal to but ignore the variable type, ```===``` means both equal value and equal type.

9. Funtioin
```var functioinName = function() {};```

10. For loop
```for (var i = 1; i < 6; i++) {}```. This is similar to C style.

11. Array
```var arrayName = [];```. The data type in the array can be mixed types.
```arrayName.push('hello');```` push an element into the array.
```arrayName.splice(1,2);```` remove two elements startig at position 1
```arrayName.splice(1,0,"new");```` add a new element after the first one


### Javascript Object
The object in Javascript is similar to hash. It is some key-value pairs. It can be created as ```var myObject={}``` or ```var myObject = new Object()```.

~~~
// use literal notation
var myObject = {
    key: value,
    key: value
};

// use constructor notation
var myObject = new Object();
~~~

The properties of an object can be access in two ways

~~~
myObject.name;
myObject['name'];
~~~

The element of the object can be created by

~~~
myObject[key] = value;
myObject.key = value;
~~~

Object specific functions can be defined as

~~~
var myObj = {
	key:value,
	functionName: function(){}
	this.functionName = function(){}
};

myObj.functionName = function(){};
~~~

```Object()``` is a default constructor and it will create a class without any properties. The class then can be used to create many objects. We can create a consturctor as

~~~
function myClass(var1,var2) {
  this.var1 = var1;
  this.var2 = var2;
}

var myObj = new myClass(var1,var2) ;
~~~

Use ```this``` to refer to the object that has been called.

```.``` and ```["keyname"]``` can be used to get the properties of an object.

```className.prototype.newMethod = function(){};``` will add new function to all objects in that class


In the class, ```this.var = "value;"``` will be public, ```var varname = "value;"``` will be private.

### Javascript functions
1. document and getElementById
Javascript uses ```document``` to indicate all html file and uses ```document.getElementById("myid")``` to get the tag with id="myid". document.write("Hello World!") to write someting to the HTML file.

2. onclick

3. style.display: change the style of the element.

4. value: get the value of an input tag

5. Math.random: many math functions are in the Math class. 

6. typeof

## Part 6: jQuery
jQuery is JavaScript library. Many useful JavaScript functions are provided in the jQuery. More useful information can be found at [jQuery website](http://learn.jquery.com/)

### Basic usage
1. Include jQuery in HTML
```<script type="text/javascript" src="http://code.jquery.com/jquery-2.2.0.min.js"></script>```

2. Choose an element

Use ```$("name")``` to get a specific element.

```$("div").click(somefunction(){})```
```$("#idname").click(somefunction(){})```
```$(".classname").click(somefunction(){})```
```$("div, p").click(somefunction(){})```

The basic syntax is ```$('.button').someAction(function)```.  ```$()``` is a function that turns the element into a jQuery object. It turns ```document``` into a jQuery object ```$(document)```. Then you can apply methods to the jQuery object.

~~~
$(document).ready(function() {
    some action
});
~~~

The selector can be saved into a variable  ```$p = $('p')```

3. Change content

use html() function to get/set the content. If nothing in html(), this function will get the content, otherwise it will set the content. ```val()``` will get the value of an element, for example, an input box.

~~~
$("#idname").hover(function(){
	$("p").html("new content");
	$("p").val("new content");
	})
~~~

We can use ```append``` or ```after``` to move the elements in the page. Use ```empty``` or ```remove``` to remove the content or elmments. 

~~~
$(document).ready(function(){
	$("body").append("<p>some thing</p>");
    $("#one").after("<p>something</p>");
    $("#two").after($('p'));
    $('p').remove();
 })
 ~~~

3. Change attribute

Use attr(name, content) to get/change the attribute. If the content is not empry, the function will change the attribute with name.

~~~
$("#idname").attr("src","newscr");
$("tagname").addClass("className");
$("tagname").removeClass("className");
$("tagname").toggleClass("className");
~~~


4. Change style

Use css(name, content) to get/change the style. If the content is not empry, the function will change the style with name.
 
~~~
$("#idname").width("20px");
$("#idname").heigth("20px");
$("#idname").css("styleelement","value");
~~~

5. Hide, fadein amd fadeout
```hide()```,```fadeIn()``` and ```fadeOut()```

6. Animation
JavaScript is good choice for animation. Use ```animate``` function. It takes two parameters: the first is what to do and the second is how long.

~~~
$(this).animate({width:"300px",height:"300px",marin:"10px"},1500)
~~~

7. Event and effect
The general workflow of JavaScript is as following: when some event occurs, apply some effect to the element. The event() takes a function as inpout so make sure to put ```function(){}``` in the event().

~~~
$(document).ready(function() {
    $('thingToClick').event(function() {
        $('thingToAffect').effect();
    });
});
~~~

If we want to apply the effect without doing something, we can only keep the code for the effct part.

~~~
$(document).ready(function() {
    $('thingToAffect').effect();
});
~~~


Following are some common events

~~~
$(document).ready(function(){});
$('div').click(function(){});
$('div').hover(function(){},function(){});
$('div').dblclick(function(){});
$('div').focus(function(){});
~~~


8. jQuery UI
jQuery UI a jQuery library. It provides many useful effects. Includes the following code in the HTML to import jQuery UI library and jQuery UI CSS.

~~~
<link rel="stylesheet" href="https://ajax.googleapis.com/ajax/libs/jqueryui/
1.11.3/themes/smoothness/jquery-ui.css" />

<script type="text/javascript" src="http://ajax.googleapis.com/ajax/
libs/jqueryui/1.10.4/jquery-ui.min.js"></script>
~~~


~~~
$(this).effect('explode');
$(this).effect('slide');
$(this).effect('bounce',{times:20},500);
$(this).draggable('');
$(this).resizable('');
$(this).selectable('');
$(this).sortable('');
~~~


7. AJAX
Asyncronous Javascript And XML (AJAX) can load files without refreshing the web page.

~~~
<script>
$.get("file.html",function(data){});
</script>
~~~

The AJAX code will get the content from file.html and save it to data without refresh the page.

~~~
$.ajax({url:"test.html"}).done(function(data){})
~~~

```ajax()``` is similar to ```get()``` function but gives more control over error etc. ```done()``` function saves the content into data.


## Twitter Bootstrap
[Twitter Bootstrap](http://getbootstrap.com/) is a good tool for responsive website desing, that is the website will adapt automatically on different divice window sizes such as computer, tablet and phone.

### Basic syntax
1. Example

~~~
<!DOCTYPE html>
<html>
  <head>
    <title>Bootstrap 101 Template</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- Bootstrap -->
    <link href="css/bootstrap.min.css" rel="stylesheet" media="screen">
  </head>
  <body>
    <h1>Hello, world!</h1>
    <script src="http://code.jquery.com/jquery.js"></script>
    <script src="js/bootstrap.min.js"></script>
  </body>
</html>
~~~



2. Grid system
Four types of screen size provided by Bootstrap. Different css will be applied to different screen sizes. Four break points divide the the window into four different size types.

The width of the screen is measured by 12 columns.

3. Navbars

4. Tables

5. Modal


## Wordpress

## PHP
PHP is the programming language for backend (server-side) development. 

### Basic syntax
1. The basic syntax of PHP is as following:

~~~
<?php
  echo "hello world";
?>
~~~

2. Display error 
Create a php.ini file and add

~~~
display_errors = on
~~~

3. Variable

~~~
$var = "hello";
echo $var;
~~~

4. Array

~~~
$myArr = array(1,2,3);
$myArr = array("1"=>1,"2"=>2);
print_r($myArr);
echo $myArr[1];
~~~

## Ruby

### Basic syntax

1. Print and puts
```puts``` adds a new line to the output and ```print``` just prints without a new line.

~~~
puts "What's up?"
print "Oxnard Montalvo"
~~~

Where To Buy

There are a lot of good options for buying WordPress themes which, unfortunately, doesn’t make deciding any easier. Here a few of my favorite places to look for and buy WordPress themes:

ThemeForest.net –  I buy the majority of themes for clients on Themeforest. They have an excellent selection backed by a strong community of developers. Themes average between $40-50 per theme.
ElegantThemes.com – Their themes are well designed and have the advantage of being all released by the same team. At $69/year for the standard license or $89/year for developer, you get access to all 75+ themes for a great price. Their new Divi 2.0 theme release is particularly worth looking at.
Themes I Recommend

The following are a list of the themes I recommend. Take a look through each. They are all excellent choices:

Divi – A highly flexible, solidly-built, mobile-optimized and well maintained theme by the folks at Elegant Themes. I’ve used it for quite a few client projects. Cost: $69/year+
Scope – A more stylish theme, designed by the same author. Cost: $50. (Note: I wrote a detailed tutorial on customizing Scope)
Responsive – A free WordPress with a clean, mobile optimized design.
(Note: This list is due for an update – Send me an email if you have any theme-specific questions)

https://www.zhihu.com/question/19696149

Plugin I Recommend

The following are a list of the plugin I recommend for common scenarios:

Gravity Forms – My all-around plugin of choice for setting up forms is Gravity Forms. If you’re looking for a basic, free alternative I suggest Ninja Forms.
Stream – Track all activity that takes place within WordPress – a must for sites where you share access with clients. And it’s free!
Yoast SEO – A solid all-around plugin to help writing content and cover the basics of site optimization.
Advanced Custom Fields – A great plugin for adding / managing custom fields.
- See more at: http://jonathanwold.com/wordpress-business/lesson-2-opening-up-shop/#sthash.TgXyyJFf.dpuf


## Reference
1. [Make a Website on Code academy](https://www.codecademy.com/ru/skills/make-a-website)
2. [Jonathan Wold](http://jonathanwold.com/wordpress-business/lesson-2-opening-up-shop/)
