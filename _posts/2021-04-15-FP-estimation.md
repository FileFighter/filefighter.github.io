---
layout: post  
title: "Function Points Estimation"  
author: valentin  
categories: pm
---


Welcome to our newest blogpost,

this week we used function points to be able to estimate the effort of our upcoming Use Cases by comparing the time we needed for our completed Use Cases with their complexity.

The complexity of a Use Case can be calculated by its Record Element Type (RET), Data Element Type (DET) and File Type Reference (FTR) values that define how complex the data, the possible
interactions and the user interface are (also described in the image below). We got these values by looking at our database model and also the mockups for the Use Cases. Together with those
values we used a lookup table to get the complexity for Data Functionality and Transaction Functionality.


<figure>
  <img src="/assets/images/blog-15/det.png" />
</figure>


Then we used a tool from [TinyTools](http://groups.umd.umich.edu/cis/course.des/cis525/js/f00/harvey/FP_Calc.html?tCountVal=0#FPCalc) to calculate the Function Point value for each Use Case.

With those values we created a graph that shows the connection between function points and time spend for a Use Case.
To be able to tell what time we will need for the upcoming Use Cases we calculated a trendline that is a linear function approaching the values of our Use Cases.
With the equation we can easily calculate the time we need to estimate for the upcoming Use Cases.

<figure>
  <img src="/assets/images/blog-15/fp.png" />
<figcaption>Time spend for Use Cases compared with their estimated function points</figcaption>
</figure>

With this function we calculated the estimated time for the upcoming Use Cases:

* Edit Files  (90 h)
* Upload  (104 h)
* Download (45 h)
* CRUD permission (104 h) 

This makes up a total time of 266 hours we have left according to the estimation.

Since we only have about 200 hours for development (taken from the time we spent in the first semester) it might be not realistic that we will be able to finish all Use Cases.
The permissions use case would be the last use case we implement, so we will have to see if we can finish it.



You can find the calculation in the sheet below or at [this page](https://pads.c3w.at/sheet/#/2/sheet/view/OGi1SLOKNq5sRnSgFC2CYU1Dd+lIA2-Icntko7nNSz4/embed/){:target="_blank"}.

<iframe src="https://pads.c3w.at/sheet/#/2/sheet/view/OGi1SLOKNq5sRnSgFC2CYU1Dd+lIA2-Icntko7nNSz4/embed/" style="width:100%;height:700px;border:none"></iframe>


Thanks for reading!
