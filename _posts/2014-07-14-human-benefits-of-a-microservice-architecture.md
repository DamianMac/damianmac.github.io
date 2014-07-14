---
layout: post
title: The human benefits of a microservice architecture
description: "It's easy to be agile with a small codebase, it becomes much harder with a large one. The more time I spend around software development teams implementing a microservice architecture, the more I see just how agile an approach it can be because rather than one big codebase, we have many smaller ones."
modified: 2014-07-14
category: articles
tags: [agile], [microservices], [speed-of-innovation]
---



Without going into a full blown definition, because there are already several competing ones out there, a [microservice architecture](http://martinfowler.com/articles/microservices.html) is one made up of many small, discrete services which communicate with each other usually in an asynchronous way (via a message bus or RESTful endpoints).

It's a style brought into popularity by the bigger internet companies with large scaling needs, [Netflix](https://www.netflix.com/) is a popularly cited example. A microservice architecture allows applications to scale without a need for a single, locking database. It also means individual pieces can be scaled and load balanced in a granular way, data can be stored in many places in formats and structures optimised for fast querying and it can be all kept (eventually consistent) by way of background processses acting on events raised throughout the system.

However it's the more human benfits of microservices which I want to discuss in this post.


## Agile Spaghetti ##

A common failing of teams practicing agile, particularly less experienced teams, is that their code just gets into a mess. In my travels a story I've heard many times is a project that started out using Scrum and went really really fast, at first. Then they started to slow down as the shortcuts taken in the code and the decisions of "we'll come back and change that later" are not followed up. The team starts to be cripled by code that is a bit of a mess, hard to change and buggy. This is known as "Technical Debt" and lots has been written on that.



> Some companies try to mitigate this by spending more time up front on architecture, however this usually causes them to lose sight of what they are actually bulding and the result is the worst of overengineering and [framework building](http://damianm.com/articles/frameworks-just-say-no).


As an app grows, any given module is likely to integrate with more modules inside the application. So a change to a module is going to have more side effects. If you manage developers, or if you are a developer you have most likely heard or uttered the words "The change is easy, I'm just not sure what it's going to break". This terrifying scenario is mitigated by a suite of automated tests but these tests become another thing to change. 


More experienced teams take a bit more care to keep their house in order by refactoring code as they go and don't suffer from this as much but the key point remains that a small codebase is faster and easier to change than a large one. So in light of this, a team with a smaller app can move quicker than a team with a big one. 

## So what about Microservices ? ##

So if we have an architecture that is many small apps rather than one large one, it stands to reason that any one of those applications can be modified more quickly, with fewer side effects than one big one. That's because we can now make smaller changes to smaller components with fewer side effects. Architected correctly an individual service will manage a business process and publish out signifigant events to the rest of the ecosystem, for example an event of "We just sold 10 Widgets at $5 each to John Smith" would be heard by a service which generated an invoice and sent it, as well as by the logistics service which would create a packing slip for the fulfillment team. This frees up the team working on the ecommerce site from managing all these responsibilities and allows them to focus on the online experience.


An approach like this allows us to scale our development in a really effective way. 

## Parallel teams, solving Brooks law ? ##

Firstly we can easily have multiple teams, an web team, the invoice team, a logistics team for example, all working in parallel with an effectiveness we wouldn't get with a 30 person development team all tripping over eachother. Or worse still, the framework team, the design team, the front end team and the DBA team so common in horribly disfunctional enterprise software companies. 
If we base our team around smaller services, each team owns a small, independent component and has autonomy about how that piece works and the communication channels are through fine grained, published message contracts.

[Amazon](http://www.amazon.com/) are known for this approach, they were famous for the "two pizza team" where a team that couldn't be fed with two pizzas was too big. This allows Amazon to scale to the giant they are, giving small teams total autonomy and measuring them based on customer data. This autonomy of course led to the need to self provision infrastructure which is what we have to thank for a lot of the "cloud" services we have today. 


> Can you imagine Amazon growing to the company they are today if they were run like most "enterprise" development shops ? 5000 developers reporting in to a project manager in a 10 hour daily standup and waiting 8 weeks to get a virtual machine provisioned ? It just wouldn't have happened.

## Emergent Design ##

Secondly, even if we don't require the scale of multiple teams, microservices allow a system to evolve and grow with the business changing needs. If we need to integrate with another third party, or add an extra step in a business process, we can add another small service which reacts to business wide events and often not need to change code in any of the other services. This gives us an environment where we can respond to business needs and opportunities in a very agile way. Our application evolves without disrupting any of our "business as usual" activities.  

## Team ramp up ##

Thirdly and finally, it also allows teams to bring new members up to speed very quickly. To quote my colleage [David Dickson](https://twitter.com/davidkdickson), with a small service the domain and code structure "fits in your head". This means it's easy to bring a new person up to speed very quickly. We often bring a new member on to a team and have them productive and shipping code to production on their first day, because the problem they are solving is broken down to a small chunk. 

## What do we get ? ##
 
So in my experience, an architecture which is broken up into small, nicely structured and autonomous services allows development teams to make changes very quickly to existing functionality, allows the organisation to be very responsive to change in a safe and non-destructive way and allows bigger companies to scale very quickly while remaining agile. 

Microservices are not really a new concept, some people argue that they are simply "SOA done right" before SOA was hijacked by Enterprise Service Bus vendors which sold expensive middleware that promised agility but in reality usually eventuates in the exact opposite. 

However we're curently seeing the rise of this style of architecture in companies using it very successfully to grow and adapt quickly and succeed in the marketplace. Your company may not have the scaling needs of Amazon, Netflix or Spotify, but the same principles can be adopted and can be used to give you an edge in the market.
