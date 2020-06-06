---
title: Online experiments involving surveys
author: ''
date: '2013-08-09'
slug: online-experiments-involving-surveys
categories:
  - HCI
tags: [HCI]
subtitle: ''
summary: ''
authors: []
lastmod: '2020-06-05T18:03:26-04:00'
featured: no
image:
  caption: ''
  focal_point: ''
  preview_only: no
projects: []
---

I've spent the last couple of months working on an experiment design framework in follow-up to [an initial study](/pdf/HCII13-DNT.pdf) concerning pragmatic understanding of UI designs.

Though I discovered a few frameworks out there for constructing online experiments. I'm working on several experiments involving hundreds of submissions and requiring:

* **Subject anonymity** - In at least one experiment, questions are sensitive and anonymity will be essential
* **Relatively, browser neutral** - I don't want to exclude people on the basis that they don't have the most current browser technology
* **Extensible** - I want to be able to easily re-use code across experiments
* **Deployable to Amazon Mechanical Turk** - I should be able to deploy an online experiment across multiple venues, but especially via AMT.
* **In a programming language I am comfortable extending** - I should be able to easily extend the framework using skills I already have such as JavaScript/HTML/CSS and R. I considered Python (such as in the [[psiTurk](https://github.com/NYUCCL/psiTurk) framework, but I would still have to integrate custom JavaScript and a full survey -- and I wasn't sure how much effort integrating with psiTurk would entail.)
* **Secure, reliable, ...** - It's a lot of work to ensure all layers of your software stack is resilient on the open Internet.

I started down the path of writing my own JS front-end built on top of node.js server and mongoDB. I learned early on that I could avoid back-end development by using services from [firebase.com](http://www.firebase.com). But I spent quite a time spinning up on the [angular.js](http://angularjs.org) front-end framework because it was something I started to use for other purposes. Both Firebase and angular.js are spectacular new technologies and I wish I had more time to go down this route!

However -- time is flying and progress has still been slow. Following my schedule, I set aside front-end development and  moved on to learning about how to integrate with mechanical turk. And... I quickly discovered an alternative development option.

I discovered [Qualtrics](http://www.qualtrics.com) research suite software which allows researchers to create  surveys with branching display logic and with a JavaScript API that makes it easy to embed custom JavaScript and interact with AMT. Even more lucky - my University has an account and, that by logging in with my.edu credentials, I have full access to this capability.

{{< figure library="true" src="branchlogic.png" title="qualtrics survey flow" lightbox="true" >}} 

Hopefully, I will have a new blog post in a few weeks detailing useful information on how to extend Qualtrics for design of behavioral UI experiments. Thus far, everything seems doable. Qualtrics uses Prototype.js and has made it incredibly easy to interact with their [Question API](http://ut1.qualtrics.com/WRAPI/QuestionAPI/classes/Qualtrics%20JavaScript%20Question%20API.html).
