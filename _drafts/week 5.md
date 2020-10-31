---
layout: post
title: "Cucumber Testing"
author: valentin
categories: tech
issuelink: https://github.com/FileFighter/filefighter.github.io/issues/ # TODO
---

#### Cucumber
This week we stated using behavior-driven development by implementing feature file that describe how our application should behave and then can be used to test if the application behaves they way we want.
For now, we just want to do this for our Springboot backend and test the  rest api.

To get started it was first important to be clear about what exactly you want to test. In our case this was the rest api and for example not the frontend. 
With the nice tutorial from [Cucumber](https://cucumber.io/docs/guides/10-minute-tutorial/){:target="_blank"} the syntax for .feature files got pretty clear. We used "Scenario Outline" and also "Background" at some places, to reduce redundancy. Once the scenario for successful interaction (or the 80% case) was done it was pretty easy to add more scenarios that simulate what could go wrong. It is important though to pick good datatypes for   
the parameters of the step functions and also to reuse the steps where ever it is possible. This avoids having to write several step functions that do almost the same.

So see the step functions go to the UC documentations:  
 [permissions use case](/wiki/usecases/crudPermissions.html) and [view folder contents](/wiki/usecases/viewFolderContents.html)

With IntelliJ IDEA Ultimate (free with [GitHub Student Developer Pack](https://education.github.com/pack){:target="_blank"}) you also get good language support for feature files, as seen in this image.


<img src="/assets/images/cucumberTests/IDEsupport.png">


We are already able to execute the test locally and with GitHub Actions (see the workflows [here](https://github.com/FileFighter/RestApi/actions){:target="_blank"}).

<img src="/assets/images/cucumberTests/runningTestsLocal.png">
<img src="/assets/images/cucumberTests/runningTestsGHActions.png">

#### Blogging tip of the Day [0]!
Do you want to embed a piece of code directly into your blog? Well with [gist-it](https://gist-it.appspot.com/){:target="_blank"} you easily can. It is as simple as pasting a link into your html. The content will be taken directly from your GitHub repo and will update as you change it! And it also looks really cool with proper syntax highlighting.

