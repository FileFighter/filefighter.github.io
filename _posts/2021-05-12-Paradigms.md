---
layout: post
title: "Chilling on the couch..."
author: open-schnick
categories: tech
---

Hello there fellow FileFighters,
This week is all about design patterns in code. We are currently refactoring our code base all over the place.
To further improve our code quality we are implementing the design pattern "SOFA", which has nothing to do with the furniture piece but stands for:
* Methods are **S**hort
* Do **O**ne thing
* Have **F**ew arguments
* Single level of **A**bstraction


Currently, many functions of our code base do not fulfill these requirements.
To fix that we want to make our functions smaller with more usage of helper functions. This will lead to shorter functions and improved readability.
How important the usage of design patterns is can be seen in our implementation of the user update function in the [RESTapi](https://github.com/FileFighter/RestApi){:target="_blank"}.
Before, the UserBusinessService looked like that:

<figure>
<img src="/assets/images/blog-17/UserBusinessService.pre.png"/>
</figure>

As you can see there is a function called _updateUser_. This function is currently very long and has alot of abstraction. The implementation can be seen here:

<script src="https://gist-it.appspot.com/https://github.com/FileFighter/RestApi/blob/7281e4594b2998f2276b394b7e1d6021a5a5f61f/src/main/java/de/filefighter/rest/domain/user/business/UserBusinessService.java?slice=153:231"></script>

The function updates the username, password and groups in one call. This is not very good for the readability and also does not embrace the "SOFA" pattern.
To fix that we split the function into four different functions. One function "__updateUser" will call the other three that will update their respective attribute of the user. This makes the code way better to read and to maintain.

The result can be seen in the changed class diagram here:

<figure>
<img src="/assets/images/blog-17/UserBusinessService.after.png"/>
</figure>

Also, the code refactored code is shown below.

<script src="https://gist-it.appspot.com/https://github.com/FileFighter/RestApi/blob/docu/sofa/src/main/java/de/filefighter/rest/domain/user/business/UserBusinessService.java?slice=150:246"></script>

We are also showing where the pattern appears in our overall class diagram in our [SAD](/wiki/arch#52-architecturally-significant-design-packages) document.

Additional we are also using the flux design pattern for redux in our frontend that is described in [this article](https://www.dotnetcurry.com/reactjs/1356/redux-pattern-tutorial).
You can find the code for this [here](https://github.com/FileFighter/WebApp/tree/master/src/background/redux){:target="_blank"}.

In our backend we are using the builder pattern all the time, that is described in [this article](https://www.baeldung.com/java-builder-pattern-freebuilder){:target="_blank"}.
This is useful because you don't have to deal with large constructors anymore.
Below is example, where having to type a constructor would have been pretty difficult.

{% highlight java %}
// create empty folder
FileSystemEntity newFolder = FileSystemEntity.builder()
.fileSystemId(idGenerationService.consumeNext())
.isFile(false)
.visibleForUserIds(latestEntity.getVisibleForUserIds())
.visibleForGroupIds(latestEntity.getVisibleForGroupIds())
.editableFoGroupIds(latestEntity.getEditableFoGroupIds())
.editableForUserIds(latestEntity.getEditableForUserIds())
.ownerId(latestEntity.getOwnerId())
.lastUpdatedBy(authenticatedUser.getUserId())
.typeId(FileSystemType.FOLDER.getId())
.path(currentAbsolutePath)
.name(currentEntityName)
.lastUpdated(fileSystemHelperService.getCurrentTimeStamp())
.build();
{% endhighlight %}

This time we don't have a blogging trick for you but instead we are happy to announce the release of our new stable version _v1.7_. 
Don't let that small number scare you, we did work over 3 months on that release!
So go ahead and try out [FileFighter](https://github.com/FileFighter/ClientSetup){:target="_blank"}!
You are more than welcome to leave feedback, open issues or pull requests.
Thanks for reading have a great day!

That's it for this blogpost, have a nice day!
