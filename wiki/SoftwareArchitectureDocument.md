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

| Abbrevation | Description                            |
| ----------- | -------------------------------------- |
| API         | Application programming interface      |
| MVC         | Model view controller                  |
| REST        | Representational state transfer        |
| SRS         | Software requirements specification    |
| UC          | Use case                               |
| VCS         | Version control system                 |
| n/a         | not applicable                         |
| tbd         | to be determined                       |

### 1.4 References

| Title                                                              | Date       | Publishing organization   |
| -------------------------------------------------------------------|:----------:| ------------------------- |
| [FileFighter Blog](https://filefighter.github.io/)                 | 13.10.2020 | FileFighter               |
| [GitHub](https://github.com/FileFighter)                           | 13.10.2020 | FileFighter               |


### 1.5 Overview
This document contains the architectural representation, goals and constraints as well as the logical, deployment, implementation and data views.

## 2. Architectural Representation
This project uses the MVC Pattern for the back end (Spring Boot). So the model (data model, domain specific classes), the view (user interface), and the controller (controls the Application) are separated. The MVC Pattern can be seen in the next picture:

<img src="/assets/images/arch-doc/mvc.svg" style="filter:invert(1)">
<small> source: [Wikimedia Commons](https://en.wikipedia.org/wiki/File:MVC-Process.svg)</small>

## 3. Architectural Goals and Constraints

### MVC
As mentioned the backend is using the MVC pattern. This enables a clean software architecture with separate model view and controller.

### Front end
tdb

### Back end
The back end is written in Java. As an addition we are using the framework [spring](https://spring.io) as well as the library [Spring Boot](https://spring.io/projects/spring-boot). One advantage of this usage is that Spring Boot and Spring are implementing the MCV software architecture by themself. As a database we use [MongoDB](https://www.mongodb.com/). 
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
The logical view for our application follows the Spring Boot architecture and looks like:

<figure>
  <img src="/assets/images/arch-doc/spring_boot_logical_view.png"  alt=""/>
</figure>

In our specific case the view however is not part of spring but provided separately as a web application front end.
The front end application handles all the user interaction and independently handles the view coordination thus fulfilling the roles of view and dispatcher alike. However view and dispatcher do not interact with the client independently instead the dispatcher has been substituted by the ViewModel which connects the view and the model as described above as well as forming the connection to the controller.
However the frontend does not interact with the model itself. Model classes are duplicated into the fronted for consistency reasons but are only used to populate the corresponding views.
Any actual manipulation of the model is handled by the backend.

### 5.2 Architecturally Significant Design Packages
On this section you can find our class diagrams for the backend. We have clearly marked which parts fulfill the model, the view and the controller tasks.

The different domains contain a view model often called DTO, "Data-Transfer-Object", as well as the models, called "Entities", that are persisted in the database. We highlighted the DTOs, Entities, and the controller parts. Below you can see one of our class diagram for the back end. In this case it's the class diagram for the domain "user". 

<figure>
  <img src="/assets/diagrams/user_class_diagram.png" alt=""/>
</figure>

## 6. Process View
n/a

## 7. Deployment View
Here you can see our deployment view diagram:

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
Our Code in front and back end is constantly check by [codefactor.io](https://www.codefactor.io/). The back end is also providing a "health" endpoint, that is displaying status information about data integrity, uptime, user count, used storage and more. This way the customers can see the information like a metric about the system. 
