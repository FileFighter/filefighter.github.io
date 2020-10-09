---
layout: post
title: "Architecture of our Application"
author: valentin
categories: tech
issuelink: https://github.com/FileFighter/filefighter.github.io/issues/7 #TODO
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


## Project Roles

One task for this week was to define the rules each member of our team will have during the project.

So we looked at how IBM defines the [RUP Roles](https://www.ibm.com/developerworks/rational/library/apr05/crain/) and selected the roles we think we will need and also added some.

Then we just distributed the roles according to prior knowledge and interests. Those roles should also rather define who is responsible for certain things and not who should do everything related to this role.


| Role       | Person        |
| :------------- | :----------: |
|  Software Architect/Designer |  Open-Schnick   |
| Requirements Specifier   |Gimleux  | 
| Implementer  | everyone|
| Test Manager |Open-Schnick | 
|Deployment Manager |Valentin| 
|Project Manager|everyone?|
|Configuration Manager of test env|Valentin|
|UX Design|Gimleux|



Thats it for today. Thanks for reading!



