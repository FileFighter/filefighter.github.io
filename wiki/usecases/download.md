---
layout: page
title: "Use-Case Specification: Download"
notInNav: true
---
# 1. View folder contents

## 1.1 Brief Description
The users will be able to download files and folders.
Folders or multiple files will be archived before they are downloaded.

## 1.2 Mockup
tdb
## 1.3 Screenshot
![Download](/assets/images/usecases/download.png)


## 1.4 Interactive Demo
<iframe src="https://storybook.filefighter.de/iframe.html?id=filesystem--filesystemcontextmenu&viewMode=story" style="width:100%;height:300px;border:none"></iframe>


# 2. Flow of Events

## 2.1 Basic Flow

### Activity Diagram
tdb
### .feature Files

<script src="https://gist-it.appspot.com/https://github.com/FileFighter/RestApi/blob/master/src/test/resources/Download.feature"></script>


## 2.2 Alternative Flows
n/a

# 3. Special Requirements
The user exists and is allowed to see the files/folders he wants to download.


# 4. Preconditions
1. The user has visited the frontend.
2. The user has logged in successfully.
3. The user navigates to the 'files' page
4. The user selects (multiple) files/folders


# 5. Postconditions
The file is downloaded to the local computer.

# 6. Function Points

119 (45 hours)

