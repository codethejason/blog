+++
Categories = ['other gci projects']
Tags = ['NodeJS', 'javascript', 'server side', 'first', 'framework']
date = "2016-01-12T16:43:16-05:00"
title = "Using NodeJS for the First Time"

+++

[NodeJS](https://nodejs.org) is an asyncronous event driven Javascript framework. The main feature that separates NodeJS from other systems is is its non reliance on threads and blocking code. NodeJS does not require that a certain process finishes before starting another one. This allows the application to move on instead of being stuck on long processes.  

![non blocking](http://docs.oracle.com/cd/A87860_01/doc/appdev.817/a76975/oci02ba5.gif)

##### My Opinions on NodeJS
NodeJS was a load of fun to work with, and I really did enjoy using it. Since it is based on Javascript, the learning curve for me wasn't that bad and I picked it up fast. It felt very familiar even though I haven't worked with the framework. Setup on both Windows and Linux were easy for the most part, but on Ubuntu 14.04 x64 LTS, I was confused why my Node app was not running for a while before discovering that Ubuntu's package manager had another package called *node* unrelated to the package *nodejs*).  

I will be honest: I did not enjoy the non-blocking feeature of NodeJS at first because it requires me to do a copious amount of callbacks. I will be trying out something different next time so I do not get code that is described on [this page](callbackhell.com).  

Although I was very familiar with Javascript, I still felt weird using it on the server side. I am used to the idea that Javscript is a client side language designed to provide and modify visual elements. Right now I still feel a lot more comfortable with PHP for server side code, but I will try using NodeJS on my next back end application.  

##### Some Code I Wrote
I wrote a simple [script](https://gist.github.com/codethejason/c2b2d71814752eb10d4d) to check for membership of a user in FOSSASIA's GCI Students organization on Github. This was the first NodeJS code I ever wrote, and roonyh (Aruna Herath) encouraged me to try out other tasks. I then created a [GitHub OAuth Application](https://github.com/codethejason/GithubOAuth) which logs in the user using a GitHub OAuth token. I used *httpdispatcher* to route my application and *requests* to get data from GitHub's API. I spent a lot of time on the second application, but it was all worth it considering I now have a lot more knowledge about NodeJS than I had when I started out :). I will definitely be using NodeJS in the future.  

![NODEJS](http://dab1nmslvvntp.cloudfront.net/wp-content/uploads/2015/07/1436439824nodejs-logo.png)  
