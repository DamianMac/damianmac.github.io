---
layout: post
title: Introducing Nimbus - Azure Service Bus made easy
description: "Nimbus is an easy to use API for the Azure Service Bus to make the development of Microservice and distributed applications easy."
modified: 2014-03-08
category: articles
tags: [nimbus]
---


Over the past few years at [Readify](http://readify.net/) we've had a lot of success with Microservice architectures.

Microservice architectures are systems made up of many smaller pieces rather than one big one. I'll go deeper into the what and why of Microservices in a later post because I think they're a very important concept and any organisation can realise a lot of benefits from having them as part of their architectural strategy. For now though, let's call them a good thing.

Once you have your application in many pieces instead of just one, you have the problem of needing to keep all those pieces talking. For that, we use messaging, usually in the form of a Service Bus. Again, Service Bus as a concept isn't the focus of this post, but I'll do that another day.

We've used a number of different implementations of a Service Bus on .NET. We've used [NServiceBus](http://www.particular.net/) on MSMQ on a number of projects. It does the job but MSMQ has it's limitations, the newer licencing model of NServiceBus scares a lot of customers off, and frankly we've been bitten by some bugs in it that I'd rather not face again. We've had successes with [MassTransit](http://masstransit-project.com/) and [RabbitMQ](https://www.rabbitmq.com/), but in the process had to become RabbitMQ clustering experts (not a bad thing, but again, it scares some customers). We've even built a few of our own custom implementations. 

These days we're doing a lot of work using Azure as a cloud platform, so the question came about about what to use in Azure. Building a Rabbit Cluster there seemed a little counter intuitive, especially as Azure now had it's own Service Bus. 

When Azure first rolled out there was a Queue service with a REST based Endpoint,  and a Relay Service for doing On Premise integrations. But like most things Azure, the Service Bus has come a long way in a short time and was now a fully [AMQP](http://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol) compliant message broker.

But what was it like to use ? Nobody seemed to have any stories. 

So we went looking for things built on it. Microsoft has a library called [CloudFX](http://msdn.microsoft.com/en-us/library/windowsazure/jj136818.aspx) but it left a lot of the wiring up of the bus to the developer. NServiceBus had a provider to run on Azure as a transport, MassTransit had a community contributed (but not core) provider for it too, but neither of those options appealed. What we didlike was the way that in the NServiceBus and MassTransit style of architecture, the code to handle a message on the bus was as simple as writing a small class that took the message type as in input and everything else gets taken care of. 

So [Andrew Harcourt](http://uglybugger.org/) and I decided to write our own and [Nimbus](https://github.com/damianmac/nimbus) was born.

Nimbus is an API that sits on top of the [Azure Service Bus](http://www.windowsazure.com/en-us/services/messaging/) or [Windows Service Bus](http://msdn.microsoft.com/en-us/library/windowsazure/dn282142.aspx) (if you want local hosting) and provides the nice development experience of being able to easily send messages and raise events, and write handlers for those messages. All the work of connecting to the bus, managing queues and instantiating your message handlers is taken care of.

If that sounds like the sort of app you or your team need to build, you should head over to the Nimbus site and take a look. We still have some documentation to do but the getting started code is there and there are a few sample apps included in the code. 

Nimbus is already in production use, and we're not going to abandon it so it's safe to use. 

Of course, if you'd like to know more you can always [get in touch](/about/).