---
layout: post
title: "Status Update"
author: valentin
categories: tech
issuelink: https://github.com/FileFighter/filefighter.github.io/issues/38
---

Hi there,
this week we just want to give you a quick update about the development status, as we finished the [SAD](https://filefighter.github.io/wiki/arch){:target="_blank"} already last week.  

For our backend we finished 3 use cases, all involving users (login, register and edit profile) and put a lot of effort in writing test, resulting in a coverage of about 60% currently. We also setup sonarqube already, which you can find [here](http://filefighter.ddns.net:9000/dashboard?id=de.filefighter%3Arest){:target="_blank"}. 

For the frontend we implemented the login, and the management of data across different views. We also created the fist views (one is displayed below), but design will come later.  
![register view](/assets/images/blog-8/register.png)

Our deployment solution is almost finished. We wrote a nice unix shell script for installing the application with docker. 
The images are automatically updated via GitHub Actions everytime we push changes on the master branch.
To be able to use different containers for each service we also added a reverse proxy to prevent problems with [CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS){:target="_blank"}.
You can find all code for this [here](https://github.com/FileFighter/ClientSetup){:target="_blank"}. 

Thanks for reading and have a nice day!





