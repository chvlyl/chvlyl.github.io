---
layout: post
title: "Learn QIIME for microbiome data analysis"
date: 2015-03-24
---

I start to learn QIIME for microbiome 16S rRNA data analysis. I follow this [tutorial](http://www.wernerlab.org/teaching/qiime/) 
and the [tutorial]() from QIIME website. 

Step 1: install QIIME.  
  1. I use MacBook Pro so I download the MacQIIME [here](http://www.wernerlab.org/software/macqiime). Install MacQIIME.    
  2. Make a copy of the tutorial data set to the home folder by:  
     ```cp -R /macqiime/QIIME/qiime_tutorial ~/qiime_tutorial```  
  3. Type ```macqiime``` to source QIIME environment variables. It is the same as a normal terminal shell, except the default 
  python is /macqiime/bin/python and there are other new QIIME-related things in system PATH. Type ```exit``` to go back to 
  the normal shell.

Step 2: install BLAST.  
  1. Download [BLAST](ftp://ftp.ncbi.nlm.nih.gov/blast/executables/release/2.2.22/blast-2.2.22-universal-macosx.tar.gz).  
  2. Unzip it by:  
  ``` tar -xvf blast-2.2.22-universal-macosx.tar.gz ```  
  3. Move it to somewhere permanent such as home directory:  
  ``` mv blast-2.2.22 ~/```  
  4. Add the ~/blast-2.2.22/bin folder to the PATH by editing `~/.bash_profile`. Add following line (replace YourName with the actual username):  
  ```export PATH=/Users/YourName/blast-2.2.22/bin:${PATH}```  
  5. Type `blastall` to see if you can run it.  
  6. Make a `~/.ncbirc` file that points to the BLAST data directory with following content (remember to replace YourName):  
  `[NCBI]`  
   `Data=/Users/YourName/blast-2.2.22/data/`  

Step 3: obtain the data.
mappling fiile.
#SampleID  BarcodeSequence LinkerPrimerSequence    Treatment DOB   Description   
#Example mapping file for the QIIME analysis package. These 9 samples are from a study of the effects of   
#exercise and diet on mouse cardiac physiology (Crawford, et al, PNAS, 2009).  
PC.354 AGCACGAGCCTA    YATGCTGCCTCCCGTAGGAGT   Control 20061218    Control_mouse__I.D._354  
PC.355 AACTCGTCGATG    YATGCTGCCTCCCGTAGGAGT   Control 20061218    Control_mouse__I.D._355  
PC.356 ACAGACCACTCA    YATGCTGCCTCCCGTAGGAGT   Control 20061126    Control_mouse__I.D._356  


- Multiple sequence alignment in QIIME:  
1. You can choose from three multiple sequence alignment methods: PyNAST(Caporaso et al., 2009), MUSCLE(Edgar, 2004) and INFERNAL (Nawrocki, Kolbe, & Eddy, 2009).  
2. PyNAST: need to provide a template of sequences for alignment.  
3. MUSCLE: slower than PyNAST when sequence number is large.
4. INFERNAL: use RNA secondary structure annotation for multiple alignments. 

- Alignment filter:
1. To remove positions where gaps are in every sequence.


