---
layout: page
title: "Use-Case Specification: Create, edit and find User (Users CRUD)"
notInNav: true
---


# 1. Create, edit and find User 

## 1.1 Brief Description
To register an account the administrator will have to create one. The administrator will be able to choose a name and a group of the new account.
To give another user permissions for a file, you first need to find this user by the username.

## 1.2 Mockup
tdb

## 1.3 Screenshot
![register view](/assets/images/blog-8/register.png)

# 2. Flow of Events

## 2.1 Basic Flow

### Activity Diagram
<figure>
  <img src="/assets/diagrams/activity/register.svg" style="filter:invert(1);width:100%" alt="Activity Diagram" />
</figure>

### .feature Files

<script src="https://gist-it.appspot.com/https://github.com/FileFighter/RestApi/blob/master/src/test/resources/FindUser.feature"></script>

<script src="https://gist-it.appspot.com/https://github.com/FileFighter/RestApi/blob/master/src/test/resources/UserRegistration.feature"></script>


## 2.2 Alternative Flows
tbd

# 3. Special Requirements
The current user need to be an administrator.

# 4. Preconditions
1. The user has visited the frontend.
2. The user has logged in successfully and is an administrator.
3. The users navigates to the 'create users' page and clicks.

# 5. Postconditions
The new created user must be stored in the database.

# 6. Function Points
tbd

