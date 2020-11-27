---
layout: page
title: Software Architecture Document
permalink: /wiki/arch
notInNav: true
---

{% include wiki-nav.html %}

# Table of Contents
- [Introduction](#1-introduction)
    - [Purpose](#11-purpose)
    - [Scope](#12-scope)
    - [Definitions, Acronyms and Abbreviations](#13-definitions-acronyms-and-abbreviations)
    - [References](#14-references)
    - [Overview](#15-overview)
- [Architectural Representation](#2-architectural-representation)
- [Architectural Goals and Constraints](#3-architectural-goals-and-constraints)
- [Use-Case View](#4-use-case-view)
    - [Use-Case Realizations](#41-use-case-realizations)
- [Logical View](#5-logical-view)
    - [Overview](#51-overview)
    - [Architecturally Significant Design Packages](#52-architecturally-significant-design-packages)
- [Process View](#6-process-view)
- [Deployment View](#7-deployment-view)
- [Implementation View](#8-implementation-view)
    - [Overview](#81-overview)
    - [Layers](#82-layers)
- [Data View](#9-data-view)
- [Size and Performance](#10-size-and-performance)
- [Quality](#11-quality)

## 1. Introduction

### 1.1 Purpose
This document provides an overview of our software architecture. With several architectural views it depicts different aspects of the system. It is intended to capture and convey the significant architectural decisions which have been made for the system.

### 1.2 Scope
This document describes the architecture of the FileFighter project.

### 1.3 Definitions, Acronyms and Abbreviations

{% include abbreviations.md %}

### 1.4 References

{% include references.md %}


### 1.5 Overview
This document contains the architectural representation, goals and constraints as well as the logical, deployment, implementation and data views.

## 2. Architectural Representation
This project uses the MVC Pattern for the back end (Spring Boot). So the model (data model, domain specific classes), the view (user interface), and the controller (controls the Application) are separated. The MVC Pattern can be seen in the next picture:

<img src="/assets/images/arch-doc/mvc.svg" style="filter:invert(1)">
<small> source: [Wikimedia Commons](https://en.wikipedia.org/wiki/File:MVC-Process.svg)</small>

## 3. Architectural Goals and Constraints

Our architecture is based on microservices. Microservices are defined as independent small applications, that serve a special purpose. This gives us the ability to develop each service independently and even with different technologies.  
To be able to setup and deploy the whole application we will be using [Docker](https://www.docker.com/){:target="_blank"}. That way we can manage CI/CD, pipelines, and different versions of the services independently. The main reason for using Docker is how easy it is to use as a Client. The dependencies needed to host the whole application are reduced to only docker. Furthermore, all the typical advantages of Docker apply here.   
We will develop three microservices.  

Our frontend where all the interaction with the normal user will take place, will be developed with the JavaScript library [React](https://reactjs.org/). It will be hosted in a container and provide a web user interface.

The second service is a RESTful Web service that will handle the users and abstract a filesystem. The information about the individual users and all their files will be stored in a [MongoDB](https://www.mongodb.com/){:target="_blank"} database. The web interface will provide the frontend with all the needed information about folders and their content for authenticated users, but not the actual files.

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
The client will then just need to build and start the containers. All this will be done automatically by a script we will provide in our [ClientSetup](https://github.com/FileFighter/ClientSetup){:target="_blank"} repository. The script will initialize all necessary services, start the FileFighter nas and also periodical check for new versions of the services.

The deployment process is also displayed [here](#7-deployment-view).

### MVC
As mentioned already, our back end is written in Java. As an addition we are using the framework [spring](https://spring.io){:target="_blank"} as well as the library [Spring Boot](https://spring.io/projects/spring-boot){:target="_blank"}. One advantage of this usage is that Spring Boot and Spring are implementing the MCV software architecture by themself. As a database we use [MongoDB](https://www.mongodb.com/){:target="_blank"}. 
The Server offers multiple REST APIs which are accessed by our front end. 
MVC: 
* Model: domain specific classes
* View: domain specific classes serialized to JSON format.
* Controller: Multiple Controllers for different Use Cases

## 4. Use-Case View

<figure>
  <img src="/assets/diagrams/usecases.svg"  alt=""/>
</figure>

### 4.1 Use-Case Realizations
n/a

## 5. Logical View

### 5.1 Overview
Our application contains multiple services. Our front end consumes the views provided by our SpringBoot Backend and transforms them into a valid user interface.
The front end application handles all the user interaction and independently handles the view coordination thus fulfilling the roles of view and dispatcher alike. However view and dispatcher do not interact with the client independently instead the dispatcher has been substituted by the ViewModel which connects the view and the model as described above as well as forming the connection to the controller.

<figure>
  <img src="/assets/images/arch-doc/spring_boot_logical_view.png"  alt=""/>
</figure>

More specifically we are using a slightly more detailed logic that can be seen here:

<figure>
  <img src="/assets/images/arch-doc/custommvc.png"  alt=""/>
</figure>

The main difference is that we use View-Models and Data-Models. View-Models, often called "DataTransferObjects" (DTOs), are instances of classes that are made for the customer / user of the endpoints. The Data-Models, often called "entities", are a representation of the data that is stored in the database. Entites are never leaked to the consumer and thus are never directly manipulated. Our business logic is transforming the entities to DTOs and visa versa, to be able to encapsulate certain information like passwords.
In our specific case the views, provided by the back end, consist of the information stored in the DTOs formatted with the JavaScriptObjectNotation(JSON). 
However, the frontend does not interact with the model itself. Model classes are duplicated into the fronted for consistency reasons but are only used to populate the corresponding views.
Any actual manipulation of the view model is handled by the backend.


To populate the corresponding views the frontend will store the data using [Redux](https://redux.js.org/){:target="_blank"}.
 After requesting data from the backend the frontend will dispatch action with the data. 
 Those actions will then be processed by reducers and written to the JSON store. 
 The views will then take the data from this store. 

<figure>
  <img src="/assets/images/arch-doc/fe-mvc.png"  alt=""/>
</figure>


### 5.2 Architecturally Significant Design Packages
On this section you can find our class diagrams for the backend. We have clearly marked which parts fulfill the model, the view and the controller tasks.

The different domains contain a view model often called DTO, "Data-Transfer-Object", as well as the models, called "Entities", that are persisted in the database. We highlighted the DTOs, Entities, and the controller parts. Below you can see one of our class diagrams for the back end. In this case it's the class diagram for the domain "user". 
For visibility reasons we removed, test-, builder- and exception- / exception handler classes.

<figure>
  <img src="/assets/images/arch-doc/user_class_diagram.png" alt=""/>
</figure>


The full class diagram is displayed here. Click on the image to enlarge it.

<a href="/assets/images/arch-doc/RestApplication.png">
  <img src="/assets/images/arch-doc/RestApplication.png" alt=""/>
</a>

## 6. Process View
n/a

## 7. Deployment View
Here you can see our deployment view diagram:

<figure>
  <img src="/assets/images/arch-doc/deployment.svg" style="filter:invert(1)" alt=""/>
</figure>

And here the flow of realising new versions.

<figure>
  <img src="/assets/diagrams/deployment.svg" style="filter:invert(1)" alt=""/>
</figure>


## 8. Implementation View
n/a
### 8.1 Overview
n/a
### 8.2 Layers
n/a

## 9. Data View
Database ER-Diagram:

<figure>
  <img src="/assets/diagrams/filefighter.png" alt=""/>
</figure>

## 10. Size and Performance
n/a

## 11. Quality/Metrics
The application is being measured in terms of complexity, coupling and cohesion. Due to the MVC Pattern the backend is unproblematic regarding any of these metrics. The web application makes it more difficult to achieve similarly good metrics for the frontend. Handling the UI elements requires many method calls from framework classes, contexts and views have to be handled and passed which increases all the above mentioned metrics. However, we have committed to still avoid high ratings in these categories even though we could not prevent several classes to be rated medium-high.  
Our Code in front and back end is constantly check by our own instance of [SonarQube](http://filefighter.ddns.net:9000/){:target="_blank"}. The back end is also providing a "health" endpoint, that is displaying status information about data integrity, uptime, user count, used storage and more. This way the customers can see this information via the endpoint or via the metrics provided by our front end.
