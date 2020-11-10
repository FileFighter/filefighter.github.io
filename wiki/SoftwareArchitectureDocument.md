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
tdb @open-schnick
The back end is also written in Java. As MVC tool we use Spring Boot. For the account system Spring security is used. As a database we use [MongoDB](https://www.mongodb.com/). 
The Server offers multiple REST APIs which are accessed by our front end. 
MVC: 
* Model: domain specific classes
* View: no view available
* Controller: RestController

## 4. Use-Case View

<figure>
  <img src="/assets/diagrams/usecases.svg" />
</figure>

### 4.1 Use-Case Realizations
n/a

## 5. Logical View
tbd

### 5.1 Overview
tdb @open-schnick
The logical view for our application follows the Spring Boot architecture and looks like:

In our specific case the view however is not part of spring but provided separately as an webapp front end.


### 5.2 Architecturally Significant Design Packages
On this section you can find our class diagrams for the backend. We have clearly marked which parts fulfill the model, the view and the controller tasks.

Here is the class diagram for the back end. As the backend has no view part we only highlighted the model and the controller parts.



## 6. Process View
n/a

## 7. Deployment View
Here you can see our deployment view diagram:

<figure>
  <img src="/assets/diagrams/deployment.svg" style="filter:invert(1)"/>
  <figcaption>Fig.3 - deployment of the software for the client</figcaption>
</figure>


## 8. Implementation View
n/a
### 8.1 Overview
n/a
### 8.2 Layers
n/a

## 9. Data View
Database ER-Diagram:


## 10. Size and Performance
n/a

## 11. Quality/Metrics

