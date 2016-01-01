+++
Categories = ['miscellaneous']
Tags = ['docker', 'virtual machine', 'linux', 'containers']
date = "2016-01-01T17:16:25-05:00"
title = "Exploring Docker"

+++

I have always seen Docker being talked about in the Linux community and have seen it as one of the DigitalOcean quick app install options. I had no idea what it was and did not realize it's function. [Docker](https://www.docker.com/what-docker) is actually a container technology designed to improve efficiency. Traditional virtual machines house their own guest operating system and libraries to run an application. As one can see, if there is a large number of virtual machines running their own operating system, the workflow is inefficient. Docker combines the operating systems and other shared parts, so a low spec server could be running hundreds of containers without a hitch. Docker also makes collaboration and publishing easier since it creates a common framework for people to work together and scales easily.  

Docker has a few tools in its Toolbox to help with development. [Docker Compose](https://www.docker.com/docker-compose) is a tool used for running small parts of application on different containers while treating it as a single application. There is no need to manage each and every separate container. [Docker Machine](https://docs.docker.com/machine/) makes host creation easier by automatically configuring Docker on the hosts. [Docker Swarm](https://www.docker.com/docker-swarm) is exactly what it sounds like; it provides clustering capabilities to manage a whole swarm of Docker Engines in a since Docker Engine.  

I found [installation](https://docs.docker.com/engine/installation/) to be a little bit frustrating because I could not get Docker to work on one of my Windows computers. When I tried to ask for help, there was virtually nobody active on the IRC. I proceeded to install Docker on another computer without a problem. I made a 3rd tier application (talks to database) that connects to MySQL [here](https://github.com/codethejason/gcismallprojects2015/tree/master/simpleDockerApp) and ran it on a Docker container.  

By the way, Happy New Year!  

![hny](http://4.bp.blogspot.com/-dZ7-CqEkHhU/VJ6dGmIHCHI/AAAAAAAAH28/eYAWdPY_XM0/w350/Happy-New-Year.png)