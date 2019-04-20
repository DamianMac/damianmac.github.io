---
title: Introducing Hammock Core
description: Hammock Core is an open source client library for CouchDB and .NET Core
modified: 2019-04-19
category: blog
---

The TL;DR; of it, is I've just released an open source .NET Core Client for [CouchDB](http://couchdb.apache.org/) called [Hammock](https://github.com/DamianMac/Hammock). It's on Nuget as `Hammock.Core` and ready for your relaxing document storage needs.

The longer story....

Many years ago I was playing with a lot of NoSQL database options for a couple of projects, and the one that suited my needs best at the time was [CouchDB](http://couchdb.apache.org/).

There was a great client library called Hammock (or [relax-net](https://code.google.com/archive/p/relax-net/)) by Nick Nystrom that, while looking somewhat abandoned, did the job really well. 

With Google Code going into mothballs, I grabbed a copy of the source just in case and put it onto [GitHub](https://github.com/DamianMac/Hammock).

Recently I needed to port one of the services I use CouchDB with to .NET Core and realised the dependency I had on Hammock. Given there aren't any other good Couch .NET Core clients around, I figured it would be a fun exercise to port the library and publish it.

Porting the code was simple, there are a few method overloads that crossed into `System.Web` territory which I've ommitted. But that process was pretty smooth.

Porting tests took a little longer, because I ported from NUnit to XUnit at the same time. There's a little bit of cleanup left there to do in the Assertion syntax, but it works.

The next thing I needed was to create a build pipeline. I'm pretty committed to Docker for all things build and deployment these days so there was a bit of work to do there. Mainly because all the tests require a CouchDB instance to run against. 

Docker is perfect for that as I can spin one up as part of the build process. Getting it all to work was a little fiddly though, and something I'll probably write another post about. There really doesn't seem to be much published about building, testing, and publishing .NET / Nuget packages in Docker.

As for the project itself, with Nick's blessing I am now the official maintainer of it. I need to write a little bit more documentation for it and there are a few small things I'd like to change. Honestly I'm not sure how much of a market there is for CouchDB in .NET, but it was an interesting exercise and I figured I'd put it out there and see what happens.

If running CouchDB with .NET Core is something that's interesting to you, please get in touch, I'd love to have a chat.

