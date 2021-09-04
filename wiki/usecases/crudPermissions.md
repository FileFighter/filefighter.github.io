---
layout: page
title: "Use-Case Specification: Share files and directories (Permissions CRUD)"
notInNav: true
issuelink: https://github.com/FileFighter/filefighter.github.io/issues/17
---

# 1. Share files and directories

## 1.1 Brief Description
The owner of a file (the person who uploaded the file) will be able to permit other users to see and edit his files. This will be managed for folders and their content or individual files. He can permit it to single users or a certain group of users (administrators/internal users/external users).


## 1.2 Mockup
<figure>
  <img src="/assets/mockups/UC-Edit_Permissions.png" style="width:100%" alt="Mockup: Share files and directories"/>
</figure>

## 1.3 Screenshot
tbd

# 2. Flow of Events

## 2.1 Basic Flow

### Activity Diagram
<figure>
  <img src="/assets/diagrams/activity/crudPermissions.svg" style="filter:invert(1);width:100%" alt="Activity Diagram"/>
</figure>

### .feature File
[GitHub](https://github.com/FileFighter/RestApi/blob/master/src/test/resources/crudPermissions.feature)
<script src="https://gist.filefighter.de/https://github.com/FileFighter/RestApi/blob/master/src/test/resources/crudPermissions.feature"></script>


## 2.2 Alternative Flows
tbd

# 3. Special Requirements
The user exists.
The user is owner of the files he wants to change the permissions of.

# 4. Preconditions
1. The user has visited the frontend.
2. The user has logged in successfully.
3. The users navigates to the 'files' page and clicks on the edit permissions button of a file.

# 5. Postconditions
The new permissins for the files or folders are stored in the database.

# 6. Function Points

190 (104 hours)

