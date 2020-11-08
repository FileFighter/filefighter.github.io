---
layout: post
title: "Our scrummy Project Managing"
author: valentin
categories: pm
issuelink: https://github.com/FileFighter/filefighter.github.io/issues/ # TODO
---

This blogpost will be about project management and how you can set up a nice workflow.


Using a project management tool like youtrack in your browser can work quite well. You just need to switch applications everytime you want to do something in it. This could become annoying over time. If you are coding a lot you are in you IDE most of the time. Integration your project management tool sounds like a perfect solution.

With Intellij IDEA you can install the Youtrack plugin and do almost everything directly from there.

<img src="/assets/images/blog-6/yt-in-ide.png"/>

Sadly at the moment I was taking this screenshot the youtrack server of the DH was not working correctly, so I could not select a project.


As an alternative to this plugin I also searched for a CLI (command-line interface) for youtrack. [The one I found](https://github.com/shanehofstetter/youtrack-cli){:target="_blank"} works for the basic needs. If you are a terminal crack this will be the way to go.

<img src="/assets/images/blog-6/yt-cli.png">

<img src="/assets/images/blog-6/yt-cli-work.png">


An other nice feature of Intellij is the graphical git interface. We are not using [GITx](http://gitx.frim.nl/){:target="_blank"} as this seems to only work on macOS. But for me personally nothing beats the git cli.   


<img src="/assets/images/blog-6/git-in-ide.png">


To always keep track of how much time you are spending for the different task you can enable time tracking in the IDE as described [here](https://www.jetbrains.com/help/youtrack/standalone/Time-Tracking-IDE-Integration.html){:target="_blank"}.


<img src="/assets/images/blog-6/enable-tt.png">

<img src="/assets/images/blog-6/time.png">

Our project overview can be found [here](https://dhbw-karlsruhe.myjetbrains.com/youtrack/dashboard?id=005597cb-b220-44de-826c-c318c2d86655){:target="_blank"} and our agile board [here](https://dhbw-karlsruhe.myjetbrains.com/youtrack/agiles/108-41/109-389){:target="_blank"}. 

Maybe you need to login first.




#### Blogging tip of the Day [1]!

Have you ever had a broken link on your website? This really sucks and can happen for various reasons. 
With the Python tool [Hydra](https://github.com/victoriadrake/hydra-link-checker){:target="_blank"} you can check for dead link for any given url manually.
To automate this you can use GitHub Actions with the Action [Link Snitch](https://github.com/victoriadrake/link-snitch){:target="_blank"}. Because we are hosting our blog with GitHub pages our page gets checked for broken links everytime we public something on it. What a perfect combination.
