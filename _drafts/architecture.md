---
layout: post
title: "Architecture of our Application"
author: valentin
categories: tech
issuelink: https://github.com/FileFighter/filefighter.github.io/issues/ #TODO
---



In this blog post we want to give you some insight about the architecture we want to use for our application. Understanding this will be important to follow the ongoing development, as you will know the features of the different programs and how they play together.
First we will cover the whole architecture and then briefly talk about authentication and follow up with how the end user will deploy our software.


Our architecture is based on microservices. This gives us the ability to develop each service independently and even with different technologies.
To be able to easily setup the whole application we will be using [Docker](https://www.docker.com/). 

Our frontend where all the interaction with the normal user will take place will be developed with the JavaScript library [React](https://reactjs.org/). It will be hosted in an container and provide a web user interface.

The second service is a RESTful Web service that will handle the users and abstract a filesystem. The information about the individual users and all their files will be stored in a [MongoDB](https://www.mongodb.com/) database. The web interface will provide the frontend with all the needed information about folders and their content for authenticated users, but not the actual files.

The actual files will be handled by the "DataHandler Service". This service will provide a interface to store and receive files. The files will be stored on disks. When the users tries to download or upload a file the "DataHandler Service" will also communicate with the RESTful Web service to guarantee authentication.



<figure>
  <img src="/assets/diagrams/architecture-large-text.svg" style="filter:invert(1)"/>
  <figcaption>Fig.1 - The basic architecture</figcaption>
</figure>



<img src="/assets/diagrams/auth-large-text.svg" style="filter:invert(1)"/>

<img src="/assets/diagrams/deployment.svg" style="filter:invert(1)"/>


