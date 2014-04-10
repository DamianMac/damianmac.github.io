---
layout: post
title: Frameworks. Just say NO!
description: "Some of the most dangerous words I hear in my consulting travels are 'we're building a framework'. It's a compelling idea but it never works out well. Reuse of components is good, but you need them to be useful before they can be reused"
modified: 2014-04-10
category: articles
tags: [agile]
---

If you're a development manager, or a "product owner" or someone else in charge of a software development team there's a conversation you've either heard, or are going to hear soon.

It goes something like this.

"What I want to do is build a framework. It will let us reuse all the common things we need to do, plus when 'the business' change requirements it will be easy for us to plug in those new rules and have the application cope".

![](/postimages/itsatrap.jpg)

*The admiral has it right!*

> As an aside, there's another, far more insidious motivation that happens in environments where contract developers are common. That is "if we abstract all the hard stuff, then we can hire lower quality devs and still deliver applications". I'm sure this sounds like a good idea to somebody.

How it unfolds after that is that the developer(s) responsible have permission to "go dark" for 6 months while working on their wonderful framework that will solve all the companies problems and have all sorts of wonderful ROI.

Of course when The Framework (and they always have grand names like "The Framework" or "The Platform") finally does get finished, usually many months later than it was meant to, and you try to implement the first features on top of it, it doesn't work. The shape of the first problem you hit never ever fits the shape of the framework.

At this point though we're not prepared to give up on the idea, so we (incorrectly) assume that this is a one off anomaly and maybe take a teeny, tiny, just-this-one-time-and-I'll-fix-it-later shortcut (aka hack) around it.

Of course you know where [it goes from there](http://en.wikipedia.org/wiki/Broken_windows_theory).

These frameworks never survive "first contact with the enemy" s because they were developed in isolation and in blissful ignorance of what the end user or customer needs. They weren't built with the features in mind. They were built with the developers interests in mind, with the developer as a customer.

Now, this actually makes a lot of sense to me (and I'd be lying if I said I'd not fallen into the same trap myself earlier in my career). It's because we all like to have certainty and control of our own environment. 
If your environment is one where the people building the software have no direct contact with the end customers because it requires "people skills", and we've given the job to Business Analysts, and those "requirements" are taking forever to be "signed off", abstracting all the grunt work and building something that can accept "business rules" at some later time and make them easy has a great appeal.

The problem is it just doesn't work.

It doesn't work because good software isn't easy and if there were a cookie cutter, template approach to building it, then that would have been done years ago by some tool vendor and we'd all be out of jobs. So it's somewhat egotistical to think that your "senior developer" is going to be the one to crack the problem. 

So when we have our framework and it actually has to deliver on some of the features we actually want to see, it's not a pleasant or smooth experience and compromises are made. The problem with these frameworks is that they are designed from the developers perpsective, rather than their real world use. Inside out rather from the outside in. 

Which is not to say that I don't believe in reusing common components across your applications.

Far from it! 


Reuse is great, things just need to be useful first. Reusable components evolve from observing common patterns your applicaton actually has, encapsulating those patterns and spinning them out into components and libraries. 

Good software frameworks evolve from good software, not the other way around.

They also typically are smaller units. They are libraries and components that work in a loosely coupled way, the way good software is designed to. They are easy to pull out of an application because of this. With some sort of internal package management system, whether that be NuGet, or Maven or Gem or whatever your flavour is you can make these libraries easy to pull into your apps and version. 

So the next time you hear about a need to build a framework before getting started on a project, you need to look at a couple of other options.

1. Is this being built because your team can't actually get with the job because they can't get near the people whose problem they are trying to solve ? Then fix that.
2. Is this being built because your organisation won't allow software to be deployed and for iteration to happen ? Then fix that.
3. Is this motivation because you think you can find a bunch of cheap devs and expect good software to be built ? Definitely fix that one, it's not going to work.

The framework conversation is likely a symptom of a larger problem in the organisation, if you hear it, you need to look for the reasons that the team can't get on with the job of shipping good software. You never know what you might find.
