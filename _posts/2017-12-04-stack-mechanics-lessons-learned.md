---
layout: post
title: Lessons learned teaching microservices architecture to a room full of smart people
description: With the first Stack Mechanics course behind us we look at what went well, and what we can learn to make the next ones even better!
modified: 2017-12-04
category: articles
tags: [stackmechanics]
---


[A few months ago](/articles/introducing-stack-mechanics) we announced [Stack Mechanics](https://stackmechanics.com/), a collaboration between three former consulting colleagues to bring deep-dive software architecture training to software developers.

In November, we hit our first milestone, running a three-day workshop in Brisbane.

The concept of Stack Mechanics is something we’ve been sitting on for nearly a year, and something I’ve wanted to do for a couple of years. Once we announced it things came together pretty quickly. So the first lesson we learned is that by announcing it and creating a public commitment it’s much easier to motivate yourself to ship. 

Of course this is something we know, and advice we've given to other people about many times. It’s it funny how hard it is to follow your own advice!

## The Course

Our three-day workshop covered Domain Driven Design, microservices architecture in .NET, messaging patterns and Event Driven Architecture, and devops techniques like CI / CD pipelines and Structured Logging.

That's a lot to cover in three days with a room full of people. but by the end of it we had everybody building features on top of a new stack with new concepts. 

We've had great feedback and everybody went away with new knowledge and techniques they could apply in their work.

<img src="/postimages/stackmechanics/coding.jpg" alt="Recommendations Engine Team at Work" width="500" />

## The Venue

We decided early on that we wanted to be different from other training organisations. We didn't want to use the standard training venues and facilities, with boring rooms and hard fluorescent lighting. We wanted a venue that was cool, one that would take people out of their usual workplace and into a different mental zone.

[Brisbane Powerhouse](https://brisbanepowerhouse.org/) ticked the boxes for us, with its imposing size, funky theatre vibe, graffiti, and awesome river views. The Rooftop Terrace is a great room for something like this, with its open space, and huge balcony for breakout conversations.

<img src="/postimages/stackmechanics/bph.jpg" alt="Brisbane Powerhouse" width="500" />

Somewhat unfortunately we had a few days of miserable weather and cold winds, so we couldn't use the outside space as much as we'd anticipated.

Some lessons on this one: while the venue was cool and gave us the vibe we wanted, a concrete room echoes a whole lot and made some of the conversations hard. 

We also learned that choosing catering options for a range of people is super difficult, but you should always avoid pumpkin and polenta muffins!

<img src="/postimages/stackmechanics/brainfunk.jpg" alt="Funky Venue" width="500" />

## Getting There

With our experience in the software industry, we know that writing code is only part of the job. The other parts like getting an application ready to ship, deploying it, monitoring it, managing infrastructure, marketing and sales (to name a few) are all just as important.

With the course we were reminded that turning up and talking about code is only a small part of the job, and that we have a renewed respect for event managers (having played this role ourselves). 

If you're doing something like this, as well as finding and booking venues, venue runsheets and requrements, there is also work organising ticket sales, talking to people about dietary requirements and booking catering, buying workshop supplies, and a whole list of other small activities.

<img src="/postimages/stackmechanics/foyer.jpg" alt="It's all happening!" width="500" />

## Course Structure

We had an agenda planned with plenty of content options and a number of contingency plans in place. Tthis served us well, as at end of the first day we did adopted one of those contingency plans. We'd gone in with too much background tutorial content. The initial idea was that we'd introduce concepts and then build on them. While this was fine for most of our participants, we missed the mark a little for others.

On day two we covered less tutorial than we'd originally planned, but broke out into a couple of groups discussing from a voted list of "parking lot" topics and had the groups report back what they'd learned through discussion or experiment. I think this worked well, but felt a little disorganised. Part of that was inevitable given that, at one time, we were running three different streams of content based on interest, but we could have made it a little easier for ourselves nonetheless.

<img src="/postimages/stackmechanics/pitching.jpg" alt="Pitching ideas" width="500" />

Day three was the most fun, where we had people "pitch" ideas they wanted to see running on our microservice architecture, then group up on those features and built them during the day. We finished up the day with a showcase of what they'd built.

Seeing people have an idea in the morning, and ship it in a day is always a great thing! Having a pre-prepared CI/CD pipeline available to everyone was invaluable in this space as getting to production was literally a matter of `git push` and an entire environment was spun up and deployed.

<img src="/postimages/stackmechanics/presenting.jpg" alt="Presenting a new microservice" width="500" />

I think the biggest lesson for us here is that we'd get people building code earlier, and dive deep on some of the theory as needed, rather than setting up the foundations first. It's always a fine balance and one we'll tweak, as the foundations are arguably less interesting but much more important.

## Next step - taking it on the road

We had a great time teaching this. It was amazing to spend three days in a room with smart, motivated people who arrived ready to learn and build things. The feedback has been great and we're using these lessons to make the course better and then take it on the road.

Next year we're planning to take this to to other cities and possibly overseas. If you'd like it to come to your city, please let us know, and also sign up to our [mailing list](https://stackmechanics.com/).

We're particularly interested in talking to companies who might want to send a group along. If we can get guarantees of numbers to make it viable to put the course on then we can work together on the timing and details.
