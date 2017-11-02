---
layout: post
title: "Copy files with rsync"
date: 2015-08-20
---

### Use rsync to copy files between servers  
```
rsync -avzhe ssh --progress  localfolder  username@remote:/home/username/
```

