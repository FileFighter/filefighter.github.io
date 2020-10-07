---
layout: post
title: "Architecture of our Application"
author: valentin, open-schnick
categories: tech
issuelink: https://github.com/FileFighter/filefighter.github.io/issues/ #TODO
---

In this blog post we want to give you some insight about the architecture we will be using for our application. Understanding this will be important for you to follow the ongoing development, as you will know the features of the different applications/services and how they play together.
First we will cover the whole architecture and then talk briefly about authentication and follow up with how the end user will deploy our software.


Our architecture is based on microservices. Microservices are defined as independent small applications, that serve a special purpose. This gives us the ability to develop each service independently and even with different technologies.
To be able to setup and deploy the whole application we will be using [Docker](https://www.docker.com/). That way we can manage CI/CD, piplines, and different versions of the services independently. The main reason for using Docker is how easy it is to use as a Client. The dependencies needed to host the whole application are reduced to only docker. Furthermore all the typical advantages of Docker apply here.   
We will develop three microservices.  

Our frontend where all the interaction with the normal user will take place, will be developed with the JavaScript library [React](https://reactjs.org/). It will be hosted in an container and provide a web user interface.

The second service is a RESTful Web service that will handle the users and abstract a filesystem. The information about the individual users and all their files will be stored in a [MongoDB](https://www.mongodb.com/) database. The web interface will provide the frontend with all the needed information about folders and their content for authenticated users, but not the actual files.

The actual files will be handled by the "DataHandler Service". This service will provide a interface to store and receive files. The files will be stored on disks. When the users tries to download or upload a file the "DataHandler Service" will also communicate with the RESTful Web service to guarantee authentication.

In the end we combine all those images and build container for the client in our [ClientSetup](https://github.com/FileFighter/ClientSetup) Repository. The Client has to run only one script, to initialize all necessary services, and start the FileFighter nas. The script will also periodical check for new versions of the services.

<figure>
  <img src="/assets/diagrams/architecture-large-text.svg" style="filter:invert(1)"/>
  <figcaption>Fig.1 - The basic architecture</figcaption>
</figure>



<img src="/assets/diagrams/auth-large-text.svg" style="filter:invert(1)"/>

<img src="/assets/diagrams/deployment.svg" style="filter:invert(1)"/>


