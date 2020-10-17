---
layout: post
title: "Architecture of our Application & Project Roles"
author: valentin, open-schnick, Gimleux
categories: tech
date: 2020-10-10 11:37:00 +0200
issuelink: https://github.com/FileFighter/filefighter.github.io/issues/7
---

In this blog post we want to give you some insight about the architecture we will be using for our application. Understanding this will be important for you to follow the ongoing development, as you will know the features of the different applications/services and how they play together.  
First we will cover the whole architecture and then talk briefly about authentication and follow up with how the end user will deploy our software.  
Afterwards, we will also present the distribution of roles in our team.

## Architecture of our Application

Our architecture is based on microservices. Microservices are defined as independent small applications, that serve a special purpose. This gives us the ability to develop each service independently and even with different technologies.  
To be able to setup and deploy the whole application we will be using [Docker](https://www.docker.com/). That way we can manage CI/CD, pipelines, and different versions of the services independently. The main reason for using Docker is how easy it is to use as a Client. The dependencies needed to host the whole application are reduced to only docker. Furthermore, all the typical advantages of Docker apply here.   
We will develop three microservices.  

Our frontend where all the interaction with the normal user will take place, will be developed with the JavaScript library [React](https://reactjs.org/). It will be hosted in a container and provide a web user interface.

The second service is a RESTful Web service that will handle the users and abstract a filesystem. The information about the individual users and all their files will be stored in a [MongoDB](https://www.mongodb.com/) database. The web interface will provide the frontend with all the needed information about folders and their content for authenticated users, but not the actual files.

The actual files will be handled by the "DataHandler Service". This service will provide a interface to store and receive files. The files will be stored on disks. When the users tries to download or upload a file the "DataHandler Service" will also communicate with the RESTful Web service to guarantee authentication. 

The whole architecture is also outlined in figure 1 for an easier overview.

<figure>
  <img src="/assets/diagrams/architecture-large-text.svg" style="filter:invert(1)"/>
  <figcaption>Fig.1 - The basic architecture</figcaption>
</figure>


For the authentication we will be using two kind of tokens. One with an longer active time an one with an shorter one. When the user logs in with his username and password he will get a Refresh token, which has s longer active time an can be saved in the browser (with cookies for example). With this Refresh token he then will be able to request Access Token, those only last a short amount of time, but are necessary for all the Api requests involving the sensitive data. The backend will connect each Access Token with the correspondent user and make sure the user only has rights to access what he is supposed to be able to access. This process is also outlined in figure 2.



<figure>
  <img src="/assets/diagrams/auth-large-text.svg" style="filter:invert(1)"/>
  <figcaption>Fig.2 - authentication workflow</figcaption>
</figure>

In order for our client to easily install our application we will provide docker images for all our services.  
Those images will automatically be build for every release using GitHub Actions and published on a container registry.  
The client will then just need to build and start the containers. All this will be done automatically by a script we will provide in our [ClientSetup](https://github.com/FileFighter/ClientSetup) repository. The script will initialize all necessary services, start the FileFighter nas and also periodical check for new versions of the services.

The deployment process is also displayed in figure 3.



<figure>
  <img src="/assets/diagrams/deployment.svg" style="filter:invert(1)"/>
  <figcaption>Fig.3 - deployment of the software for the client</figcaption>
</figure>


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
|Project Manager|Open-Schnick|
|Configuration Manager of test env|Valentin|
|UX Design|Gimleux|



Thats it for today. Thanks for reading!



