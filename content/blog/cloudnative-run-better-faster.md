
---
title: "Cloud Native - Run better, faster"
date: 2018-04-06
featured: true
categories:
- developer
tags:
- Cloud
- SAP
---
![Cloud with Thor](/img/cloud_native_thor.jpg)
[DJ Adams](https://people.sap.com/dj.adams#overview) started the [conversation](https://blogs.sap.com/2018/03/26/monday-morning-thoughts-cloud-native/) about cloud native on his recent post. Having seen the journey of SAP Cloud Platform from [JPaaS](http://www.eclipsecon.org/europe2012/category/tags/jpaas.html) days to present I have certainly been close to the principles and patterns that are now called “Cloud Native” I started commenting on DJ Adams blog and it got so long that I thought of writing it as a post in itself so here we go.

Before delving in to details of “Cloud native” let’s setup some context on why it is important at all for businesses. Marc Andreessen, co-founder of Netscape and now highly respected venture capitalist at a16z made a rallying call when he wrote [“Why Software is eating the world”](https://a16z.com/2016/08/20/why-software-is-eating-the-world/) One of the main argument he made was that all businesses will become software businesses. You can see manifestations of that all around - more and more things has software in them, larger chunk companies are driving a significant growth in their revenues enabled by software. There are countless examples of impact of software in various industries. One really good thread on this on twitter is by @SuB8u. This entire thread as well as this [search](https://twitter.com/search?q=software%20from%3Asub8u&src=typd) is filled with software disruptions 

>Tech is impacting every industry. The smarter incumbents adapt, the lazier ones fall behind.http://t.co/mWFYQ0FU3P pic.twitter.com/CjltaxQq2L
>
>— Subrahmanyam KVJ (@SuB8u) July 18, 2015

Stated this way software has become an existential fact for organizations and it would be very important for businesses to be effective at software processes i.e. my title run better, faster. To understand this let us consider a modern development workflow based on DevOps toolchain - 

![Dev Ops Loop](/img/devops.png)

Plan - code - build - test - release - deploy - observe - maintain


This toolchain is based on the expectations from software in today’s ever connected world where people, things and businesses use software for everything. This could be from ordering lunch, booking a place to stay, checking supplier inventory to performing automated repairs etc. Apart from basic requirements of being always there (availability, graceful fallback) and not break (resiliency) there is also the added expectation of faster response to customer demands (meaning newer functionality and not the latency, though smaller latency is also good). In this context let’s look at two of the most important ideas from where the cloud native principles have emerged

1. Need for speed and Shorter Feedback Cycles for the win (faster..)
If you want to get from idea to market the fastest way you better have very short cycle of delivery baked with continuous feedback cycles. You may have a grand idea but do you want to deliver it in a meaningful incremental way (MVP anyone) or you want to do one big grand delivery with a high chance of not understanding customer requirements or they have changed since you started. The shorter feedback and deployment cycles also help in reducing risk. To do software with shorter delivery and feedback cycles you would need some concepts/patterns like



On demand and preferably code driven self service for the services and resources (compute, storage, databases etc.) needed for your solution. It won’t be fun if you are still waiting for the PO to be approved or have logistics problems with the delivery of servers or the data center power has not been provisioned correctly.  
Your software solution inhouse developed or bought has its own code/binaries/artifacts along with a lot of prerequisites/dependencies. It would be really nice if we had a standard way to package all of this in some format that would run everywhere (almost). Containers are here to help and their image definitions provide such a solution. There are a lot of other benefits as well but that’s a topic for another post.
Continuous Integration and Continuous Deployment pipelines that would build, test and feed these artifacts to the applicable runtimes.


2. Operationally Efficient (run better..)
We want to run our solutions the most efficient and economical way. These efficiencies could be from the infrastructure side which is easy to procure/operate/deprecate/upgrade or on the human side i.e. doesn’t require a lot of grooming from humans, has a lot of resiliency or at least graceful degradation built into it so as to avoid 2am calls. There are three concepts we should consider here -


Evolution of Acitivies - I was first introduced to these by Simon Wardley, concept itself is based on his own research and built on [Difffusion of Innovation](https://en.wikipedia.org/wiki/Diffusion_of_innovations) by Everett Rogers ([Crossing the Chasm](https://en.wikipedia.org/wiki/Crossing_the_Chasm) by Geoffrey Moore is also based on this). Idea is that most of the technology goes thru an evolution curve from relatively unknown genesis to ubiquitous utitlity as shown below

![Evolution Curve by Simon Wardley](/img/evolution_curve-simon-wardley.png)


You can see this in from batteries to electricity, Telegraph to hundreds of ways to communicate today and finally computing from Z3 https://en.wikipedia.org/wiki/Z3_(computer) to cloud today. Other components needed in software solutions like databases, application servers are also going thru similar evolution and are being offered as services or utility. At any point of time it is best (mostly) to use latest in evolution. For example should I get electricity from utility (Solar is challenging this) or produce my own, should I setup my own datacenter or buy from cloud etc. 

Standardization - As anything moves from left to right on the evolution curve to be more efficient you start seeing standardization of various components. This is the context in which containers fit. You have one standard way to package and deploy software with all the dependencies baked it.


Orchestration - We already covered Building, testing and packaging (CI/CD, containers) the software so that it can be run as efficiently as possible. This task of running efficiently falls under a concept called orchestrator. This orchestrator takes our software packaged as a container and runs it and makes sure that it keeps running. This keep it running is a big part and consists of monitoring, making sure the response time is good, based on the creterions defined by the operators scale up or down the application, provide health checks etc.


There are quite a few other related concepts that I can talk about like microservices, observability, API first etc. but I think we have a covered a lot of ground with talking about need for speed and how to operate in this faster changes + shorter feedback context. Let’s try to tie in all these for a TL:DR version.

All businesses are becoming software businesses while needing to respond faster to customer demands and operate efficiently to grow and compete. This resulted in changes in how to code/build/test/package software (12factor apps, CI/CD, containers) and how best to operate software (orchestration, observability) with the benefits of scalability, resilience and with shorter feedback cycle. Cloud native approach incorporates all of these to plan, build and operate software which is easier to change, resilient and graceful to unexpected situations.

I hope this was useful to you. Please do share your feedback in the comments. I hope to write in more details about some of the concepts individually.

_Cross Posted at [SAP Community](https://blogs.sap.com/2018/04/06/cloud-native-run-better-and-faster/)_

References

[Cloud Native Attitude](http://container-solutions.com/ebook-the-cloud-native-attitude) ebook by Anne Currie
12 Factor Apps - [https://12factor.net/](https://12factor.net/)
[Cloud Native Trail Map](https://raw.githubusercontent.com/cncf/landscape/master/trail_map/CNCF_TrailMap_latest.png) from cncf.io - This is a really useful map and covers all the important concepts for your cloud native journey

Photo Credits
Thor Photoby [JD Hancock](http://photos.jdhancock.com/)
[Evolution Activities](http://blog.gardeviance.org/2013/01/evolution.html) curve by Simon Wardley