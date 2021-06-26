---
layout: page
title: "Use-Case Specification: View folder contents"
notInNav: true
issuelink: https://github.com/FileFighter/filefighter.github.io/issues/17
---
# 1. View folder contents

## 1.1 Brief Description
The users will see all the files and subfolders he can access. He will also be able to navigate the folder structure.


## 1.2 Mockup
<figure>
  <img src="/assets/mockups/UC-Show_Content.png" style="width:100%" alt="Mockup: View folder contents" />
</figure>

## 1.3 Screenshot


![ View folder contents](/assets/images/usecases/viewFolderContent.png)


## 1.4 Interactive Demo
<iframe src="https://storybook.filefighter.de/iframe.html?id=filesystem--default&viewMode=story" style="width:100%;height:700px;border:none"></iframe>


# 2. Flow of Events

## 2.1 Basic Flow

### Activity Diagram
<figure>
  <img src="/assets/diagrams/activity/viewFolderContents.svg" style="filter:invert(1);width:100%" alt="Activity Diagram" />
</figure>

### .feature File

<script src="https://gist-it.appspot.com/https://github.com/FileFighter/RestApi/blob/master/src/test/resources/ViewFolderContents.feature"></script>


## 2.2 Alternative Flows
tbd

# 3. Special Requirements
The user exists.


# 4. Preconditions
1. The user has visited the frontend.
2. The user has logged in successfully.
3. The users navigate to the 'files' page (if the url indicates a file location this will happen automatically).

# 5. Postconditions
The user can now perform multiple file actions.

# 6. Function Points

165 (89 hours)

