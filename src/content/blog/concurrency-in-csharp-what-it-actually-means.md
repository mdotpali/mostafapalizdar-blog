---
title: "Concurrency in C#: What It Actually Means"
description: "Concurrency is not one thing. A quick breakdown of the four models in .NET and what separates them."
pubDate: 2026-04-03
---

I've been reading Stephen Cleary's *Concurrency in C# Cookbook* and the first chapter alone cleared up confusion I didn't know I had.

Concurrency means doing more than one thing at a time. But that's really four different things in .NET, and mixing them up leads to bad decisions.

**Multithreading** is the most obvious one. Multiple threads running code at the same time. Good for CPU-bound work. Expensive, hard to get right, and easy to reach for when you don't actually need it.

**Parallel processing** is multithreading with a specific purpose: splitting a large computation across cores to finish faster. The Task Parallel Library and PLINQ are the tools here. It only helps if the work can actually be split up independently.

**Async programming** is the one most .NET developers use daily but often misunderstand. It's not about more threads. It's about not wasting the threads you have. When you're waiting on a database or an HTTP call, a synchronous approach blocks a thread for the entire wait. Async frees that thread. In .NET this is `async`/`await`, and it's where most of the interesting patterns live.

**Reactive programming** is a different model entirely. You subscribe to streams of events instead of pulling data. `IObservable<T>` and Rx. Powerful for the right problems, but most backend .NET code never needs it.

These aren't competing approaches. They solve different problems. The issue is when developers default to multithreading out of habit, or reach for parallelism when async is the right call.

In the next posts I'll go deeper into async, since that's where most of the day-to-day work is.
