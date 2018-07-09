---
title: "First 2 week update"
date: 2018-06-09
permalink: /posts/2018/06/second-update
---

First of all, I would like to thank Julia Computing for sponsoring my trip to [Juliacon](http://juliacon.org/2018/) in London! I feel like I don't deserve this, because in some sense, they are paying for my trip before I give them any results. Better really step up my game now and make my project work, so I can get the most out of this experience. 

![](https://github.com/biona001/biona001.github.io/tree/master/images/juliacon.png)

## Project description & progress

My project is to add a few more functions to [IHT.jl](https://github.com/klkeys/IHT.jl), which performs Iterative Hard Thresholding to numeric and genetic data. 

This past weeks I have been trying to build a new data handling routine by replacing PLINK.jl with [SnpArrays.jl](https://openmendel.github.io/SnpArrays.jl/latest/). This is done because modern genetic analysis softwares are very hetergeneous in terms of data handling. As statistical genetics become increasingly popular (thanks to sequencing technology), so too do we increasingly need a centralized platform that provides a streamlined analysis environment. The [Open Mendel](https://openmendel.github.io/) umbrella program is attempting to fill this gap. It currently enables 9 genetic analysis options and provides 4 utility functions (including SnpArrays), while 3 additional analysis options are underway. By replacing PLINK.jl with SnpArrays.jl, we merge IHT.jl with the OpenMendel program, thus promoting data compatibility and streamlining reproducible research. 

My mentor Kevin Keys have been super helpful over the past few weeks, both in terms of providing technical details and for understanding my academic situation. To keep it subtle, next week is the first round of evalutions for google summer of code, but also it's the finals week of UCLA. Yeah, coding and school don't really belong together. I guess I was partly to blame for telling Google I will somehow parallelize school and coding, but I can't help to wonder why there couldn't be a more flexible start/end date to accommodate those who are on quarter systems. Because you know, a lot of schools are on quarter systems.... and they want to code too....

**tl;dr**
I am a bit behind schedule, but it's probably ok. 