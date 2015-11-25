---
layout: post
title: "Python character encoding"
date: 2015-11-11
---

1. There are three most common encoding in Python:  
- **ASCII**: use 1 byte (8 bits) for each character. It can only encode limitted characters.  
- **Unicode**: use 2 bytes for common characters and 4 bytes for uncommon ones. It includes characters from non-English languages. But it wastes a lot of storage space.  
- **UTF-8**: use 1 byte for common English characters, 3 bytes for less common ones (Chinese characters are usually encoded in 3 bytes) and 4-6 bytes for uncommon ones. Save some storage space.     

2. Characters in the memory are all encoded in Unicode. It can be translated into UTF-8 when we want to save them into disk.  

3. Python supports Unicode and use u'...' syntax.

4. When the Python script contains some Unicode characters (for example, non-English characters), one must use # -*- coding: utf-8 -*- at the begnning of the Python script. This is to tell Python interpreter to use UTF-8 encoding.