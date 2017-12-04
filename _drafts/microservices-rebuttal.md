---
layout: post
title: Lessons learned teaching microservices architecture to a room full of smart people
description: 
modified: 2017-12-04
category: articles
tags: [microservices, architecture]
---


Microservices

Bad architecture is bad

Strawman
    Microservices introduce fault tolerance

    Fault tolerance
        you pay this anyway

    "If you can't build a monolith, what makes you think you can build Microservices"

    You are not google


What problems are you trying to solve

    Scaling vs availablity
    breaking system into right components
    Independent deployment
        Unable to deploy without breaking other parts of the system - not Independent
        protecting yourself against upstrea change - * good software engineering
    Test components Independently
    It fits with conways law

The DRY obsession
    prematurely generalisation
    * "package all the things" is the new framework
    
    premature packaging story
        * This is the TP story
        "We did this stupid thing and now nobody should do things"

Hype - we focus on technology rather than customer
    * Sure, but that doesn't make an approach bad

Build what you know you need first * well yes, no shit

Build to your team culture

Good / Fast / Cheap
    if you need to integrate late into the piece
    * total strawman, in an agile environment you'd integrate early and often


Summary - Software development in a non-agile environment with bad engineering is bad

a better Approach of migrating systems
    write tests to understand boundary and domain so you can refactor
    Avoid premature generalisation - rule of 3

    "avoid any internal service boundaries like the plague" - wtf

    apply devops / automation / deloyment disciples - * well duh


Understand that your prime goal is to delivery business value - * well duh
know the problem - dont solve problems you don't have yet

