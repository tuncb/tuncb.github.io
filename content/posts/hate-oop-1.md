+++
author = "Tunç Bahçecioğlu"
title = "Why I hate Object oriented programming"
date = "2024-06-24"
description = "Why I hate Object oriented programming"
tags = [
    "programming",
    "oop",
]
categories = [
    "programming",
]
series = ["programming"]
aliases = ["oop-hate-1"]
+++

I hate object oriented programming...
<!--more-->

Object oriented programming is sold as a programming paradigm but actually it is a domain design paradigm.

**I hate object oriented programming because it is a scam.**

Programming is about solving problems by utilizing computers to transform input data to output data.
It is about transforming the input state to output state.
Programming is about data structures and algorithms.
But OOP is not about programming, it is about designing universes where the solution might be constructed.

**I hate OOP because it distracts you from solving your problem.**

In OOP you start creating your universe by creating entities. These entities will be kind of related to the starting point of your solution.
They contain some part of your input, some part of your output and some part of your algorithm.

As you continue your solution you create more of these entities and of course the new ones have to be connected and managed with the old ones so you probably need some more entities to manage them.
You name them something similar to AbstractClassFactoryManager. But one day you realize, the later stages of your solution does not actually fit with the entities that were designed at the beginning so you need more entities, more connections and more Manager entities to manage them.
You now have something, which someone might call a design but in reality it is a monster.

**I hate OOP because it gives you the tools to create evil.**

But you have to go on, so you continue your solution by creating even more monsters and now these monsters have to talk to each other to do anything useful but don't worry, because people wrote books about this.

![Book about living with monsters](/design_book.jpg)

You connect your monsters with the new cool techniques you learned, they lead to even more entities but at this point you don't care.
And if you are lucky you end up with something that solves some problem that is worth solving.

You solved your problem but there are always more problems to solve and the new problem you are trying to solve has slightly different inputs, outputs and logic to fit your universe.
So you need to change your domain a bit but since OOP spreads your inputs, outputs and logic all over the place even the slightest adjustment requires you to change a bunch of places and now you realize all you do is to add/remove/edit boilerplate and you are not really doing any actual coding.

**I hate OOP because it is anti coding.**

Maybe you can solve your new problem now, but your domain is so complicated and so inter-connected that it cannot be described as a monster.
It can only be described as the thing.
The thing acts and behaves like real code but I assure you it is not.
The thing is actually a state machine.
Every member of every entity you created at least doubles the number of states that this thing can hold, so the number of states is approaching infinity.
This is why no human being can comprehend the thing.
It is so interconnected even the slightest change ends with a number of regressions that no human being can anticipate.
You still have to adjust it now and then but every adjustment requires precise changes only a single person in your company knows about.

At this point you secretly know what you have to do.
You have to kill the thing.

**I hate OOP because it leads to violence.**

But the thing is so enormous and so many people depend on it you cannot just kill it.
You start denying that the thing is bad at all,
If people criticize the thing you get angry but deep inside you know.
You get depressed.
At the end you accept.

**I hate OOP because it leads to accepting poor software engineering.**
