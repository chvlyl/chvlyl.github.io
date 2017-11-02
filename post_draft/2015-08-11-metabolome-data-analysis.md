---
layout: post
title: "Metabolome Data Analysis"
date: 2015-08-11
---

#### LC-MS
1. Liquid chromatography-mass spectrometry: detect the mass-to-charge raio (m/z) and the retention time
2. Chromatography is used to separate organic and inorganic compoundns. Liquid chromatography (LC) and gas chromatography (GC) 
are two common chromatography approaches.

#### Retention time
The time that a compound elutes out of the column in chromatography is called retention time. The eluted compounds are then injected
into the mass spectrometer.

#### Mass spectrometer
1. Ion source: converts eletrically neural compounds into charged molecules. It is often to analyze the biological samples in 
both +ve(positive) and -ve(negative) ionization modes to cover more metabolites.
2. Mass analyzer: separates ions according to the m/z values. Usually, more than one mass analyzer are used in tandem mass spectrometry.
3. Detector: converts the abundances of the ions into the electrical signals. 

#### LC-MS raw data
Since samples are separated by liquid chromatography and mass spectrometry, the LC-MS raw data is three dimentional 
(retention time, mass-to-charge ratio, intensity)
1. Retention time: the time that the metabolite elutes from the liquid chromatography.
2. Mass-to-charge raio (m/z): measurement of the molecular weight.
3. Intensity: quantification of the metabolite abundance.

#### LC-MS/MS
The parent ions are broken into smaller fragments. The MS/MS spectrum (tandem MS) can provide the information about 
both product ions and the remaining parent ion. Therefore, metabolites with the same mass but different structures can be identified.

#### LC-MS data preprocessing
Remove outliers, detect peaks orrepsongding to metabolites and align peaks across multimple samples.

#### Install RStudio  
1. Install RStudio from [here](http://www.rstudio.com/products/rstudio/download/).  
2. You also need to install some R packages for R package development, such as "devtools" and "roxygen2".  

#### Create a GitHub account  
1. Go to [GitHub website](https://github.com/) and create an account.  
2. Create a repo for the R package on GitHub.  

#### Install Git
Install Git from [here](http://git-scm.com/downloads), not GitHub!  

#### Generate SSH key 
