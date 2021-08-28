---
layout: page
title: "Use-Case Specification: Edit profile"
notInNav: true
---


# 1. Edit profile

## 1.1 Brief Description

Once an account was created the user is able to change his username and password.

## 1.2 Mockup
tdb

## 1.3 Screenshot
![profile view](/assets/images/usecases/profile.png)
![profile edit view](/assets/images/usecases/editProfile.png)


## 1.4 Interactive Demo
<iframe src="https://storybook.filefighter.de/iframe.html?id=profile--default&viewMode=story" style="width:100%;height:700px;border:none"></iframe>


# 2. Flow of Events

## 2.1 Basic Flow

### Activity Diagram
<figure>
  <img src="/assets/diagrams/activity/changeProfile.svg" style="filter:invert(1);width:100%" alt="Activity Diagram" />
</figure>

### .feature File
[GitHub](https://github.com/FileFighter/RestApi/blob/master/src/test/resources/UserEditInformation.feature)
<script src="https://gist-it.appspot.com/https://github.com/FileFighter/RestApi/blob/master/src/test/resources/UserEditInformation.feature"></script>



## 2.2 Alternative Flows
tbd

# 3. Special Requirements
The user need an account.

# 4. Preconditions
1. The user has visited the frontend.
2. The user has logged in successfully.
3. The user navigates to the 'profile' page and clicks on the edit button.

# 5. Postconditions
The updated information are stored in the database and updated in the frontend.
# 6. Function Points
tbd

