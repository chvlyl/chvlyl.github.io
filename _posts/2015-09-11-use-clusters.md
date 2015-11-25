---
layout: post
title: "Use computing clusters for data analysis"
date: 2015-09-10
---

U of Penn has a cluster computing system, called PMACS. Here are some instructions for how to run analysis jobs on clusters. Use PMACS as an example.

### Login 
PMACS has two kinds of servers: one is the computing server, the other is the data transfer server. First, log into the data transfer server to upload any necessary data.
```
ssh username@mercury.pmacs.upenn.edu
```
Or one can use rsync to copy data from other servers.
```
rsync -avzhe ssh --progress localfolder username@mercury.pmacs.upenn.edu:/home/username/
```
After uploading the data, one can log into the computing server 
```
ssh username@consign.pmacs.upenn.edu
```

### Interactive job submission
Normally, the computing server has a front node and this is the node we first log into. Since it is required to run jobs in computing nodes instead of front nodes, we have to log into computing nodes.
```
bsub -Is bash
```
We are now in a computing node.