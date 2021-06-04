---
layout: post
title: Installing FileFighter
author: open-schnick
categories: tech
---
Hello again,  
This time we want to go through the installation of FileFighter.  
To install FileFighter you only need [Docker](https://www.docker.com/){:target="_blank"} and hardware to run FileFighter on. The codebase is split into services, that run in different Docker Containers hosted on [DockerHub](https://hub.docker.com/u/filefighter){:target="_blank"}.  
The whole installation guide can be found [here](https://github.com/FileFighter/ClientSetup){:target="_blank"} in our GitHub Repository.

# GNU/Linux and MacOS
Under GNU/Linux this will install a command line interface for you, which you can use to interact with the Docker containers.
Examples:

- Downloading FileFighter

{% highlight shell %}
curl https://raw.githubusercontent.com/FileFighter/ClientSetup/master/Download.sh | bash
{% endhighlight %}
  

<figure>
    <img src="/assets/images/blog-20/ffighter-download.gif" alt=""/>
</figure>

- Display help text

{% highlight shell %}
ffighter
{% endhighlight %}


<figure>
    <img src="/assets/images/blog-20/ffighter-help.png" alt=""/>
</figure>

- Installing FileFighter

{% highlight shell %}
ffighter install
{% endhighlight %}


<figure>
    <img src="/assets/images/blog-20/ffighter-install.gif" alt=""/>
</figure>

- Show Info about FileFighter

{% highlight shell %}
ffighter status
{% endhighlight %}


<figure>
    <img src="/assets/images/blog-20/ffighter-status.gif" alt=""/>
</figure>

# Windows
When using Windows as server for FileFighter the usage of a commandline tool is not very easy and thus currently not implemented.  
For that case we wrote a docker-compose file which can be used with the tool [docker-compose](https://docs.docker.com/compose/){:target="_blank"} to manage the containers.  
This file can be found [here](https://github.com/FileFighter/ClientSetup/blob/master/docker-compose.yml){:target="_blank"}.

That's it for today, be sure to check FileFighter out and give it a chance.  
Have a nice day!