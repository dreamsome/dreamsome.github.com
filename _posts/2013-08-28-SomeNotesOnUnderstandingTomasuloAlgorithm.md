---
layout: post
title: "Some Notes on \"Understanding Tomasulo Algorithm\""
tags : [arch]
---



**1.Textbook is just one of the references of knowledge, but not all of them.**

As what Thomas S. Kuhn said in *[The Structure of Scientific Revolutions](http://www.amazon.com/Structure-Scientific-Revolutions-Thomas-Kuhn/dp/0226458083)*, textbooks are misleading for the lack of details. Textbook hides away almost many important things behind an idea for conciseness, like the critical history, the original intention and the 'dead' competitors. Instead, it tells you the **outcome** directly. As a result, you get a whole picture of A, B, plus C, plus D... but don't know why they *have to* be there. 

<!--more-->

Other sources I think are also useful when understand a thing.

* Original paper
* Thoughts from an experienced person(especially when they are making conclusions)
* Some webpages(Tanks to Google)

**2.Register renaming is not like what its name suggests.**

The common register renaming scheme is providing more physical registers than the ISA needs. In this case, before an instruction is fed to the instruction queue, the name of its architectual register(e.g r5) has been modified to a physical one(e.g. p19). However the Tomasulo algorithm uses another approach. In this approach, the register of an instruction is actually "renamed" to the No. of a functional unit (it can be a single slot in [reservation station](https://en.wikipedia.org/wiki/Reservation_stations) or a register).

**3.Abstraction is a powerful weapon.**

The producer-consumer model simplifies the relationship between two instructions. With this model, the role of CDB is self-evident: Producers throw their outputs to *somewhere* where consumers can find their inputs distinguished by tags.


**4.Tomasulo Algorithm has nothing to do with reorder buffer.**

,though they often appear together in the modern microprocessors. The purpose of Tomasulo Algorithms is to enable out-of-order execution while the motivation of reorder buffer is to implement [precise interrupt]().


