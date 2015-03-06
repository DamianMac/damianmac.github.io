---
layout: post
title: A DevOps bedtime story
description: "A cautionary tale of human error, overblown process and some lessons you can take from it."
modified: 2015-03-06
category: articles
tags: [devops]
---


A few years ago I was consulting inside a government department, I won't say who or why, but I had the opportunity to witness the following take place.

This department had a very typical government process. Big releases were done quarterly, everything was released in one big hit because all the dependencies were intertwined. A release committee was needed to decide what would end up in the release and what wouldn't. Source code was branched en-masse. The development team handed a "release" to an operations team who would deploy it into a test environment with the help of a large Word document. The test team would test it and generally there was a bit of back and forth over what was and wasn't a high severity defect.

Eventually the ops team would deploy to production. These deployments were a big deal of course, involving out of hours work, documented mitigation and rollback plans and lots of signoff.

It was pretty standard for government, everybody there thought they were doing a great job, they believed they ticked all the [ITIL](http://en.wikipedia.org/wiki/Information_Technology_Infrastructure_Library) boxes so the management were happy. Nobody worried about the little details like the fact that what was delivered never really worked well. That was put down to poor requirements specification by the "customer" and everybody ignored the fact that the time frame between being asked for something and the time it was delivered was many many months.

I was labelled a dangerous heretic in that place because I suggested that way too much time was being spent either manually doing things, or waiting for another team to pick things up and understand them after they were thrown over the wall. 

<blockquote>"We are doing important stuff here, we need PEOPLE to check this at every point. Developers can't be trusted to deploy things, we have deployment EXPERTS over here to MAKE SURE it's all perfect and documented" etc etc.</blockquote>

You've probably heard the arguments before. 

## The day that it all went wrong ##


<div style="float: right; margin: 30px; margin-top: 0;" >
	<img src="/images/disaster-deployments.jpg" />
</div>


So one day, there was a BIG RELEASE going into the test environment. At about 9:30, all hell broke loose. Managers were running around in circles, phones were ringing and fingers were being pointed. **Production had gone down**!

It turned out that a database schema migration script, dutifully zipped up with the release and outlined as a step in the 30 page Word Document that had been SIGNED OFF by the management, had been copied by the database deployment expert and pasted into the query window of the SQL Server Management Studio.......

**Which happened to be connected to the Production Database Server.**

Despite all the process, documentation, meetings, and expert checking, this perfect system could be easily brought down by an authorised person running code in the wrong window.

## What happened next will shock you! ##

The development team actually figured out what had happened pretty quickly, and a few people huddled around a computer for 15 minutes after which they had come up with a SQL script which would back out the change and fix everything up.

The script was sent over to the deployment team so that they could get the production system back online (it was a pretty important system). However there was a problem, a couple of phone calls and a management meeting later it was announced:

<blockquote>
 "We can't deploy this to production, you need to make the appropriate change request documentation and have it signed off".
</blockquote>

**Seriously.**

The system in question was offline until about 4pm that day, because although "the process" couldn't protect it from human error, "the process" was still trusted as the only safeguard they had.

## Do you have a point ? ##

I've done a lot of consulting and speaking about DevOps, automation and agile. Fairly often I'll get some management type derisively tell me that all my ideas are all well and good in the fantasy world I live in. But THEY have process, and regulation, and ITIL!

It's an argument I can usually win.

**I ask:** "What is a better reflection of what is going to happen, a Word Document or an automation script or workflow ?".

The Word Document has all the steps that were remembered at the time it was last updated. The Word Document likely misses the bit of knowledge known only to the Prod Web engineer who would tell you "oh yeah,  when you do this in prod you have to change this setting here as well". 

An automation script or tool will show you exactly what is going to happen, and it won't accidentally forget something, accidentally run something in the wrong place and it won't add extra things without telling you.

**I ask:** "What is a safer release. One that's been done by a script many times exactly the same way in a lower environment, or one that's been carried out by different humans, often for the first time ?".

**I ask:** "What is a better reflection of what actually happened, an email to say 'yes we followed the instructions', or an audit log that documents every single step, when it happened, where it happened, and who triggered it ?".

**Finally, I ask:** "What is the goal of your processes ? To have more paperwork, or to have a repeatable, audited set of steps that are tested many times ?".

## My gift to you ##

If you find yourself having to fight the good fight introducing automation as part of your work, I hope this gives you a couple of talking points you can use. I'd love to hear if it helps!





