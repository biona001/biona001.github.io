---
title: "Second evalutation!"
date: 2018-07-09
permalink: /posts/2018/07/second-eval
---

Hi there. 

Several major events and exchange of ideas rolled around the corner. As a consequence, I made one significant change to my original project proposal, briefly summarized below.


![](https://github.com/biona001/biona001.github.io/tree/master/images/change_plans.jpg)


1. To keep up with the frontier of big-data genomics, I will be investigating how to stream binary files via *memory-mapping* as my second major deliverable. Douglas Bates very coincidentally initiated [BEDFiles.jl](https://github.com/dmbates/BEDFiles.jl) just a week ago, which became the final straw to push me through with this drastic change of plans. I will possibly be spending all my time before JuliaCon 2018 on this part of the project.\
\
2. My original second deliverable - *prior weighting of SNPs* - have been passed down as a 6-weeks long summer project for 2 students participating in the [BIG summer program](https://qcb.ucla.edu/big-summer/). I will be overseeing these summer interns as opposed to being the main contributor for this part of the IHT project. 

## Summary of progress so far

I completed my first proposed milestone - to merge IHT with SnpArrays (see merged pull request [here](https://github.com/klkeys/IHT.jl/commit/16026ce14886f785c233d7c046e0cce2f5980c81)), followed by a series of constructive criticism from my mentor. According to my preliminary benchmark on a dataset of $2200$ people with $10000$ SNPs, IHT using `SnpArrays` as backend runs in about 2.5 seconds and uses around 1.22 GB of memory. Compared to the original implementation which runs in $\sim$ 2 seconds and uses 23 MB of memory, there is definitely room for memory improvement. In my opinion, this is acceptable as a preliminary implementation to get things working, but we definitely need dramatic memory **and** speed improvement to scale up to datasets such as the UK biobank. Hopefully my (new) proposed second goal will prove meaningful with respect to this obsticle. 


Until next time,\
ben
