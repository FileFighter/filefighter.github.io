---
layout: page
title: Wiki
permalink: /wiki/
---

WIP

#TOC

## 1. Introduction

### 1.1 Purpose
This Software Requirements Specification (SRS) describes all specifications for the application "FileFighter". It includes an overview about this project and its vision, detailed information about the planned features and boundary conditions of the development process.


### 1.2 Scope
The project is going to be realized as a webapp and backend services, that each user can set up with one single script for them self.  
  
Actors of this App can have different roles like user and administrator.  
  
Planned Subsystems are: 
* Account System:  
Each user will have an account to identify and get access to files.
* Files System:
Users will be able to store files (upload and download).
* Permissions System:
For each file/folder the owner will be able to authorize other users to see or modify files.

### 1.3 Definitions, Acronyms and Abbreviations

| Abbreviation | Explanation                            |
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
| [FileFighter Blog](https://filefighter.github.io/)                 | 13.10.2020 | FileFighter               |
| [GitHub](https://github.com/FileFighter)                           | 13.10.2020 | FileFighter               |


### 1.5 Overview
The following chapter provides an overview of this project with vision and Overall Use Case Diagram. The third chapter (Requirements Specification) delivers more details about the specific requirements in terms of functionality, usability and design parameters. Finally, there is a chapter with supporting information. 
    
## 2. Overall Description

### 2.1 Vision
FileFighter is an easy to use and even easier to set up home NAS.  
"NAS" stands for "Network-Attached-Storage", commonly known NAS are applications like [Dropbox](https://www.dropbox.com/){:target="_blank"} and [Nextcloud](https://nextcloud.com/){:target="_blank"}. We want to provide a stable storage solution for each house hold.  
Our solution is developed with families in mind, which want to use their own NAS, but are afraid of technical as well as security issues.

We are upset about Dropbrox / Google Drive and all other large free services logging all our Data. Therefore, we will create our own.
Luckily you don't have to do the same. You can easily use our software and set up your own instance of the FileFighter-Cloud! 
Because out application will be open source only, you can checkout our code. You will see that we removed all kinds of data-collecting or spying software from dependencies and of course our own code.
We will guarantee that no data will collected by us or other companies. You can enjoy the absolute control about your files as you choose where the servers will be running, and where the files will be stored. You could even run everything on a [Raspberry Pi](https://www.raspberrypi.org/){:target="_blank"} in your local network.
Talking about security, all of your files will be only accessible with a password.

### 2.2 Use Case Diagram



<figure>
  <img src="usecases.svg" />
</figure>

<!-- 
We separated the use cases in the ones facing the normal user and the ones only important for the admin.
The admin will be responsible for creating all user accounts, the users them self will then be able to change some of their information like password and username. 



For file interaction we have the basic use cases of viewing folder contents and be able to rename or delete files. The (technical) more advanced use cases are uploading, downloading and searching for files. One potential feature would be support for different media types like videos and music.

To organize the permissions for files the users will be able to set view or editing permission for user or groups of users.

 -->


### 2.3 Technology Stack
The technologies we use are:

- RestApi:
    - Maven and Springboot
    - MongoDB Database

- Frontend:
    - React JS webapp

- IDE:
    - IntelliJ and VS Code

- Project Management:
    - YouTrack
    - GitHub
    - Discord
    - CryptPad

- Deployment:
    - Github Actions 
    - Docker
    - Shell scripts
    
- Testing:
    - Mockito
    - JUnit
    - [CodeCov.io](https://codecov.io/)
    - Jacoco

## 3. Specific Requirements

### 3.1 Functionality
This section will explain the different use cases, you could see in the Use Case Diagram, and their functionality.
Until December, we plan to implement:
 * 3.1.1 Login
 * 3.1.2 Create user accounts
 * 3.1.3 View folder contents
 * 3.1.4 Edit (rename/delete) files
 * 3.1.5 Edit permission (viewing or editing) of files for users or groups
 * 3.1.6 Sort folder contents

Until June, we want to implement:
 * 3.1.7 Show own profile
 * 3.1.8 Edit profile information (change password etc.)
 * 3.1.9 Download files
 * 3.1.10 Upload files
 * 3.1.11 Search for files


Use cases that are out of scope:
 * 3.1.12 View media files like audio or video files
 * 3.1.13 Share links to not logged in users


#### 3.1.1 Login

Each user will haven an account they can use to access their files. Therefore, they will need to login when using the application. This will be done with username and password. The login will also be cached in the browser, so you don't have to login every time when using the same browser. You will also be able to log out.

#### 3.1.2 Create user accounts

To register an account the administrator will have to create one. The administrator will be able to choose a name and a group of the new account.


#### 3.1.3 View folder contents

The users will see all the files and subfolders he can access. He will also be able to navigate the folder structure.




#### 3.1.4 Edit (rename/delete) files

The user will then be able to rename or delete the files he is seeing, if he also has edit rights for them.

#### 3.1.5 Edit permission (viewing or editing) of files for users or groups

The owner of a file (the person who uploaded the file) will be able to permit other users to see and edit his files. This will be managed for folders and their content or individual files. He can permit it to single users or a certain group of users (administrators/internal users/external users).


#### 3.1.6 Sort folder contents

To easily find files you will also be able to sort the files in the current folder by different values like filename or last edited.

#### 3.1.7 Show own profile

This will be site where the logged in user will be able to see his profile information, like his username, and the groups he is in.

#### 3.1.8 Edit profile information (change password etc.)

Once an account was created the user should change his password. He will also be able to change his username.


#### 3.1.9 Download files

This is one of the most important use cases of the application. You will be able to download files you are allowed to see with your browser.



#### 3.1.10 Upload files

The same way you can download files you will also be able to upload files in places you are allowed to. This way you can also overwrite files.

#### 3.1.11 Search for files

You will be able to search for files with a specific name within all the files you are allowed to view.


### 3.2 Usability

We want our application to be easy to set up and easy to use. The user interface should be intuitive and self-explanatory. It should be close to different filesystem browsers you can find on operation systems.
Setting up the application should be easy for everyone who has some experience with computers and servers. The installation will be done by a single shell script and require docker.




### 3.3 Reliability

The provided software should be as stable as possible, so the users don't encounter problems. During the development process we will always provide two versions, one should be stable and one that already includes the latest features.



#### 3.3.1 Availability

Each user will be responsible for the availability of their own instance, but we should make sure there is always a stable version available for them to install.  

#### 3.3.2 Data loss

We shall provide options to back up all the data stored by our application. 


### 3.4 Performance

Performance is important for all parts of our software and will always be considered during the development process.


#### 3.4.1 App performance

By using react we can provide a single-page application, that will make using the website faster than regular websites even with slightly slower internet speeds.

#### 3.4.2 Storage

As computer storage has become very cheap we will rather prefer an easy installation process than low storage usage. With docker the whole application will only have a single dependency, but will need more storage.

#### 3.4.3 Scalability

Our application will focus on private usage with a smaller set of users. By using docker we will still be able to scale some of our services to provide better performance if needed.


### 3.5 Supportability

#### 3.5.1 Coding Standards
WIP
We are going to write the code by using common clean code standards. For example, we will name our variables and methods by their functionalities. This will keep the code easy to read by everyone and make further development much easier.

#### 3.5.2 Testing Strategy
WIP
The application will have a high test coverage and all important functionalities and edge cases should be tested. Further, mistakes in the implementation will be discovered instantly, and it will be easy to locate the error.

### 3.6 Design Constraints

To provide a modern architecture for our application we want to use microservices. Microservices are defined as independent small applications, that serve a special purpose. This gives us the ability to develop each service independently and even with different technologies.

The backend will run on all devices that can install docker and act as a server.

Because the application will be used by multiple users, it should be usable on all kind of devices. To achieve this we will build a web app that should run on all devices with a browser. This means the UI should be responsive and look good on all screen sizes, even smartphones.

Supported browsers will be:
* recent versions of Chrome
* recent versions of Firefox
* recent versions of Safari


### 3.7 On-line User Documentation and Help System Requirements
WIP
The usage of the app should be as intuitive as possible, so it won't need any further documentation. If the user needs some help we will implement a "Help"-Button in the App which includes a FAQ.


### 3.8 Purchased Components

We don't plan to use any paid software as we want to publish the source code under an open-source license. 


### 3.9 Interfaces

#### 3.9.1 User Interfaces

WIP

#### 3.9.2 Hardware Interfaces

The user of our application will have to provide a server where his instance of our software will be hosted.


#### 3.9.3 Software Interfaces

The backend can be run a server, with any operation system that is supporting docker containers.



#### 3.9.4 Communication Interfaces

HTTP will be used as a communication protocol, if the users provides a certificate he will also be able to use HTTPS for secure communication.

### 3.10 Licensing Requirements

We plan to publish the source code under an open-source license. 

### 3.11 Legal, Copyright, and Other Notices

See [credits](/credits).

### 3.12 Applicable Standards
WIP
The development will follow the common clean code standards and naming conventions. Also we will create a definition of d which will be added here as soon as its complete.


## 4. Supporting Information
For any further information you can contact the FileFighter Team.