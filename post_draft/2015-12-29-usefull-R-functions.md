---
layout: post
title: "R tips"
date: 2015-12-29
---


## setNames  
setNames(object = nm, nm)


##
<div style = "float: right"> 
  ```{r Code Chunk}
  df <- diamonds[sample(1:nrow(diamonds), size = 2000),]

  plot_ly(df, x = x, y = price, mode = "markers", color = cut, size = z) %>%
  layout(title = "Diamonds")
  ``` 
</div>



