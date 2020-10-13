---
layout: page
title: Wiki
permalink: /wiki/
---

WIP

## Table of contents
- [Table of contents](#table-of-contents)
- [Introduction](#1-introduction)
    - [Purpose](#11-purpose)
    - [Scope](#12-scope)
    - [Definitions, Acronyms and Abbreviations](#13-definitions-acronyms-and-abbreviations)
    - [References](#14-references)
    - [Overview](#15-overview)
- [Overall Description](#2-overall-description)
    - [Vision](#21-vision)
    - [Use Case Diagram](#22-use-case-diagram)
	- [Technology Stack](#23-technology-stack)
- [Specific Requirements](#3-specific-requirements)
    - [Functionality](#31-functionality)
    - [Usability](#32-usability)
    - [Reliability](#33-reliability)
    - [Performance](#34-performance)
    - [Supportability](#35-supportability)
    - [Design Constraints](#36-design-constraints)
    - [Online User Documentation and Help System Requirements](#37-on-line-user-documentation-and-help-system-requirements)
    - [Purchased Components](#purchased-components)
    - [Interfaces](#39-interfaces)
    - [Licensing Requirements](#310-licensing-requirements)
    - [Legal, Copyright And Other Notices](#311-legal-copyright-and-other-notices)
    - [Applicable Standards](#312-applicable-standards)
- [Supporting Information](#4-supporting-information)

## 1. Introduction

### 1.1 Purpose
This Software Requirements Specification (SRS) describes all specifications for the application "FileFighter". It includes an overview about this project and its vision, detailed information about the planned features and boundary conditions of the development process.


### 1.2 Scope
The project is going to be realized as an webapp and backend services, that each user can setup with one single script for themself.  
  
Actors of this App can be have different roles like user and administrator.  
  
Planned Subsystems are: 
* Account System:  
Each users will have an account to indentify and get access to files.
* Files System:
Users will be able to store files (upload and download).
* Permissions System:
For each file/folder the owner will be able to authorize other users to see or modify files.

### 1.3 Definitions, Acronyms and Abbreviations
| Abbrevation | Explanation                            |
| ----------- | -------------------------------------- |
| SRS         | Software Requirements Specification    |
| UC          | Use Case                               |
| n/a         | not applicable                         |
| tbd         | to be determined                       |
| UCD         | overall Use Case Diagram               |
| FAQ         | Frequently asked Questions             |

### 1.4 References

| Title                                                              | Date       | Publishing organization   |
| -------------------------------------------------------------------|:----------:| ------------------------- |
| [FileFighter Blog](https://filefighter.github.io/)          | 13.10.2020 | FileFighter   |
| [GitHub](https://github.com/FileFighter)              | 18.10.2018 | FileFighter    |


### 1.5 Overview
The following chapter provides an overview of this project with vision and Overall Use Case Diagram. The third chapter (Requirements Specification) delivers more details about the specific requirements in terms of functionality, usability and design parameters. Finally there is a chapter with supporting information. 
    
## 2. Overall Description

### 2.1 Vision
Inspired by carpool coordination services like ‘BlaBlaCar’ or ‘Mitfahrzentrale’ we want to build an application to coordinate game sessions. We plan to create a platform for people who are looking for other people to play games with. Covering online multiplayer games, tabletop, pen and paper or regular board games we want to provide a kind of bulletin board where people can state what they want to play, when and where they want to do it and how many people they are looking for. Others can then react to the postings and virtually join the play session to be connected by us so everyone can coordinate the actual play session together on a Common Playground.

### 2.2 Use Case Diagram

{% include usecases.html %}

- Green: Planned till end of december
- Yellow: Planned till end of june

### 2.3 Technology Stack
The technology we use is:

- RestApi:
    - Maven and Springboot
    - MongoDB Database

- Frontend:
    - Android with Java and XML

- IDE:
    - IntelliJ and Android Studio

- Project Management:
    - YouTrack
    - GitHub
    - Discord
    - CryptPad

- Deployment:
    - Github Actions 
    - Docker
    
- Testing:
    - Mockito
    - JUnit
    - [CodeCov.io](https://codecov.io/)
    - Jacoco

## 3. Specific Requirements

### 3.1 Functionality


### 3.2 Usability


### 3.3 Reliability

#### 3.3.1 Availability

### 3.4 Perfomance

### 3.5 Supportability

### 3.6 Design Constraints

### 3.7 On-line User Documentation and Help System Requirements

### 3.8 Purchased Components

### 3.9 Interfaces

#### 3.9.1 User Interfaces

#### 3.9.2 Hardware Interfaces

#### 3.9.3 Software Interfaces

#### 3.9.4 Communication Interfaces

### 3.10 Licensing Requirements

### 3.11 Legal, Copyright, and Other Notices

### 3.12 Applicable Standards

## 4. Supporting Information
