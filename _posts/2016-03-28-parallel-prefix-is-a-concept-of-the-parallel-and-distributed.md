---
datePublished: '2016-08-20T23:23:35.954Z'
sourcePath: >-
  _posts/2016-03-28-parallel-prefix-is-a-concept-of-the-parallel-and-distributed.md
inFeed: true
authors: []
hasPage: true
keywords: []
author: []
dateModified: '2016-08-20T23:23:35.573Z'
title: ''
publisher: {}
description: >-
  Parallel prefix is a concept of the parallel and distributed computing world
  but can be seen, like most computer science concepts, as a real world process.
  To explain it, let’s go through an illustrated story.
inLanguage: null
inNav: false
via: {}
starred: true
url: parallel-prefix-is-a-concept-of-the-parallel-and-distributed/index.html
_type: Article

---
_Parallel prefix _is a concept of the parallel and distributed computing world but can be seen, like most computer science concepts, as a real world process. To explain it, let's go through an illustrated story.

The Pizza Story

Giovani is a rising Italian Chef. As a marketing move, he decides to participate in a pizza competition. The competition is a bit special: you have to make the best pizza of them all, and you also have to make pizzas that represent all the steps of the cooking process. In other words, for a simple Margarita made with dough, tomato and mozzarella cheese, he has to make 3 pizzas:

* **Pizza 1: **Dough
* **Pizza 2: **Dough + tomato
* **Margarita: **Dough + tomato + mozzarella

And, of course, he has to make it as quickly as possible.

Thinking back on the rules, Giovani realizes that nothing prevents him from getting some other cooks to make the pizzas in parallel.

However, one more constraint gets added: one cook only has room for one ingredients at his table and can only mix it to one other thing during each step of the competition. Concretely, that means that if a cook has Dough on his table, then in one step he make dough with one thing on it (tomato, for example). He can't add mushrooms and tomato in the same step.

This restriction prevents Giovani from giving each cook a sequential recipe to make each pizza, since the margarita cook can't have all the ingredients at his disposal at the same time (3 ingredients) and make the pizza.

So the cooks will have to communicate and cooperate.

After thinking hard about it, he is able to come up with a plan to make all the required pizzas in roughly the same time it would take to make one.

For the competition, Giovani is going to make his speciality, a pizza with 8 ingredients.

The plan as he imagined it is presented below:

In each step, each cook combines ingredients that are handed over to him depending on the pattern defined in the above drawing.

This is what _parallel prefix _is.

The Computer Story

So now you might wonder how that applies to computing.

Well, each cook is a processing unit. The limit in the ingredient space is the memory limit on each processing unit. The cooking process is a combination of operating operations like x or /. And the ingredients are the different pieces of data you want the operation to be applied on.

Let's take the \* operation with a list of integers \[1,2,3,4\] as the data. Then your complete pizza in that setting is 1 \* 2 \* 3 \* 4\. And all the pizzas are:

* 1
* 1 \* 2
* 1 \* 2 \* 3
* 1 \* 2 \* 3 \* 4

And all those results were computed with having only one piece of the data on each processor, in roughly the same amount of time it would take to only compute the last result.