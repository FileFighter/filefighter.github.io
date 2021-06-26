---
layout: page
title: "Use-Case Specification: Search for files"
notInNav: true
---
# 1. Search for files

## 1.1 Brief Description
The users will be able to search for files and folders by their name.
He will be able to interact with the results and go to the folder the files are located in.

## 1.2 Mockup
tdb
## 1.3 Screenshot
![search view](/assets/images/usecases/search.png)


## 1.4 Interactive Demo
<iframe src="https://storybook.filefighter.de/iframe.html?id=filesystem--searchmodal&viewMode=story" style="width:100%;height:700px;border:none"></iframe>


# 2. Flow of Events

## 2.1 Basic Flow

### Activity Diagram
tdb
### .feature Files

<script src="https://gist-it.appspot.com/https://github.com/FileFighter/RestApi/blob/master/src/test/resources/SearchFiles.feature"></script>


## 2.2 Alternative Flows
tbd

# 3. Special Requirements
The user exists and is allowed to view the files he is searching for.


# 4. Preconditions
1. The user has visited the frontend.
2. The user has logged in successfully.
3. The user navigates to the 'files' page
4. The user clicks on the search button.


# 5. Postconditions
The folder was changed to the one containing the selected result.



