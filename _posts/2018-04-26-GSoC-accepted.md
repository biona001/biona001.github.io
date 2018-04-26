---
title: 'GSoC-accepted'
date: 2018-04-26
permalink: /posts/2018/04/GSoC-accepted
---
Hi everyone, first ever blog post!

I am Benjamin Chu, 2nd year Ph.D student from biomathematics department at UCLA. I'm a first time GSoC student, my mentor is [Kevin Keys](https://sites.google.com/view/klkeys/). 

I???m working on a package that does iterative hard-thresholding [IHT.jl](https://github.com/klkeys/IHT.jl). This algorithm is fast enough (avoids hessian matrices!) that we can run a standard biology dataset today of size ~10000 x 1,000,000 on a personal computer and finish within an hour or so. It???s an idea that has been around for maybe 10~20 years(?), but I guess new enough that it still doesn???t have a wiki page.

I???m planning to add 3 features to the current IHT package for analyzing GWAS (i.e. genetics) data. Some of these are more or less grind throughs, such as learning to manipulate binary datafiles, but others such as grouping predictors are quite non-trivial for me in terms of how to actually do it. But I live by the principle that I try my best and life will figure out a way (most of the time), so I???ll probably be okay.

tl;dr
I work on genetics data, and I???m good at math!