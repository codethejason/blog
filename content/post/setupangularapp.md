+++
Categories = ['miscellaneous']
Tags = ['setup', 'commit', 'gh-pages', 'github']
date = "2015-12-28T12:38:47-05:00"
title = "Setup Angular User App with Github Pages"

+++

Today, our task is to setup https://github.com/aidarbek/angular so that it runs with Github Pages. Luckily, AngularJS is easy to setup for Github Pages, so this task only takes a few steps.

**First**, fork the repository and save it to your account.  

**Next**, clone the fork you just created by typing this command in Git Shell:  

```
git clone https://github.com/<your github username>/angular.git
``` 

**Then**, make a branch called github pages and switch to it.  

```
cd angular/
git branch gh-pages
git checkout gh-pages
```

**Last but not least**, push the new branch to Github by setting a new upstream.  

```
git push --set-upstream origin gh-pages
```

You're done! You can see your result at `http://<your github username>.github.io/angular`.  

![result](http://puu.sh/mbviC/6ef77603cf.png)  