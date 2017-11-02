---
layout: home
title: Eric Z Chen
---

### ZIBR: zero-inflated beta regression with random effects [[R package on Github](https://github.com/chvlyl/ZIBR)][[Paper](https://doi.org/10.1093/bioinformatics/btw308)]

The human microbial communities are associated with many human diseases such as obesity, diabetes and inflammatory bowel disease. High-throughput sequencing technology has been widely used to quantify the microbial composition in order to understand its impacts on human health. Longitudinal measurements of microbial communities are commonly obtained in many microbiome studies. A key question in such microbiome studies is to identify the microbes that are associated with clinical outcomes or environmental factors. However, microbiome compositional data are highly skewed, bounded in [0,1), and often sparse with many zeros. In addition, the observations from repeated measures in longitudinal studies are correlated. A method that takes into account these features is needed for association analysis in longitudinal microbiome data. In this paper, we propose a two-part zero-inflated Beta regression model with random effects (ZIBR) for testing the association between microbial abundance and clinical covariates for longitudinal microbiome data. The model includes a logistic regression component to model presence/absence of a microbe in the samples and a Beta regression component to model non-zero microbial abundance, where each component includes a random effect to account for the correlations among the repeated measurements on the same subject. Both simulation studies and the application to real microbiome data have shown that ZIBR model outperformed the previously used methods. The method provides a useful tool for identifying the relevant taxa based on longitudinal or repeated measures in microbiome research.

### MMDA: Multi-sample Poission model for microbiome data analysis (R)

### For my old research projects, check [my publications](https://scholar.google.com/citations?hl=en&user=7mrZzpYAAAAJ&view_op=list_works&sortby=pubdate)


{::comment}
Add papers to Papers and export as reference list (use BMC Bioinformatics style and plain text)
{:/comment}

