---
layout: post  
title: "Refactoring. Again. (And Again ...)"  
author: qvalentin  
categories: tech
---

Hi there,

this week we got an interesting task to train our refactoring skills. This task was taken from the first chapter of [Martin Fowlers](https://martinfowler.com/){:target="_blank"} book '[Refactoring](https://bookshop.org/books/refactoring-improving-the-design-of-existing-code/9780134757599){:target="_blank"}.' Starting
from [this code](https://github.com/gnilkreb/Fowler/tree/c0e1c7a21a5335d7e475c2c795ed77deec37b776){:target="_blank"} the task is to enhance the code by following the individual steps described by Fowler.

You can observe the results of our three team members in the repos below:

* [Gimleux](https://github.com/ExperimentsByFileFighter/Gimleux-Refactoring_Task/){:target="_blank"}
* [qValentin](https://github.com/ExperimentsByFileFighter/qFowler){:target="_blank"}
* [open-schnick](https://github.com/ExperimentsByFileFighter/Open-Fowler){:target="_blank"}

Many refactoring steps that are described in the book can actually be done by your IDE instead of performing them manually. Following, we will demonstrate you some of them in IntelliJ IDEA:

The rename action can even suggest some sane names for variables to you, pretty cool.
<figure>
<img src="/assets/images/blog-16/rename.png"/>
</figure>
With move instance method you can move a method to another class, when it is more suited to be part of that class.
<figure>
<img src="/assets/images/blog-16/move.png"/>
</figure>
The action inline variable allows you to remove a temporary variable and instead compute the values everytime the variable was used.
<figure>
<img src="/assets/images/blog-16/inlineVar.png"/>
</figure>
Safe delete represents an effective IDE action because it can search in the entire project for usages and even in comments and strings, making sure you don't delete anything that you eventually still needed.
<figure>
<img src="/assets/images/blog-16/delete.png"/>
</figure>
Type migration allows you to modify the type of variables, but most of the time you probably have to clean up after performing this.
<figure>
<img src="/assets/images/blog-16/TypeMigration.png"/>
</figure> 



That's it for this blogpost, have a nice day!
