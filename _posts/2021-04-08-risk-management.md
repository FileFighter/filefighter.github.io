---
layout: post
title: "Risk Management"
author: valentin, 
categories: pm
---

Welcome to this blogpost,

today we will talk about risk management, a very important aspect of project management and give a short update about our development progress.

To be able to deal with the risk that our project could face, we first need to understand them and then also be able to prioritize them.
For this we are using a list to collect all possible risks and classify them by their 'Probability of Occurrence', and their 'Impact' on the success of our project. 
With those two numeric values with a range of 0-10 we can calculate the factor for each risk (Probability of Occurrence * Impact), by which we prioritize the risks.
We also collected some mitigation tactics to deal with the risk already and decided a person that is responsible for each risk.
We plan to take a look at this list at every meeting, so we can quickly identify if one of the risks turns into an actual threat for our project or if our mitigation tactics are working.

You can find our list of risks below (needs third-party cookies) or at [this page](https://pads.c3w.at/sheet/#/2/sheet/view/WQl5RoIRthhIVsrqElHTvHQ0tZpOSxqCpSboLWiXDYc/embed/).

<iframe src="https://pads.c3w.at/sheet/#/2/sheet/view/WQl5RoIRthhIVsrqElHTvHQ0tZpOSxqCpSboLWiXDYc/embed/" style="width:100%;height:700px;border:none"></iframe>


Regarding our development progress we had to do some major refactoring on our REST backend service because our concept for sharing files was not scaling very well.
We had to rewrite parts of the existing logic, but in return the complexity was reduced, making the upcoming development easier.
The other services were not affected by this. But we realized that the upload UC is complexer that we thought.
The frontend for example has to implement a UI for deciding if files should be overwritten or not. 

#### Blogging tip of the Day [4]!
This time we just have a small recommendation for an alternative to google docs.
[Cryptad](https://github.com/xwiki-labs/cryptpad) is an 'Zero Knowledge realtime collaborative editor' that you can host yourself or use an instance provided by an organisation like the CCC [pads.c3w.at](https://pads.c3w.at/).  
This way you won't be tracked by google just because you need to collaborate.
We are using it all the time and are also really enjoying the markdown functionality.
For this blogpost we used the Sheet functionality for the first time and also embedded the document into our blog as seen above.

Thanks for reading and have a nice day!
