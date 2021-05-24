---
layout: page
title: "Use-Case Specification: Upload"
notInNav: true
---
# 1. View folder contents

## 1.1 Brief Description
The users will be able to upload files and folders.
He will be able to decide if he wants to replace a file when it already exists and if he wants to merge a directory.
The use will be able to create a new folder.

## 1.2 Mockup
tdb
## 1.3 Screenshot
tbd

## 1.4 Interactive Demo
<iframe src="https://storybook.filefighter.de/iframe.html?id=filesystem--uploaddecisionsmodal&viewMode=story" style="width:100%;height:700px;border:none"></iframe>


# 2. Flow of Events

## 2.1 Basic Flow

### Activity Diagram
tdb
### .feature Files

<script src="https://gist-it.appspot.com/https://github.com/FileFighter/RestApi/blob/master/src/test/resources/Upload.feature"></script>
<script src="https://gist-it.appspot.com/https://github.com/FileFighter/RestApi/blob/master/src/test/resources/NewFolder.feature"></script>


## 2.2 Alternative Flows
tbd

# 3. Special Requirements
The user exists and is allowed to upload to the directory.


# 4. Preconditions
1. The user has visited the frontend.
2. The user has logged in successfully.
3. The user navigates to the 'files' page


# 5. Postconditions
The file/folder is now visible and can be used.

# 6. Function Points

190 (104 hours)

