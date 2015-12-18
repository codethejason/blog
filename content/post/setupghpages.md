+++
Categories = ['hugo']
Tags = ['setup', 'commit', 'gh-pages', 'hugo', 'github']
date = "2015-12-17T23:12:09-05:00"
title = "Setup Hugo on Github Pages"

+++

At this point, you might be wondering how users can easily see your blog content without downloading the repository and doing all the steps you had to take to view your posts. This is done by publishing on [Github Pages](https://pages.github.com/), a free service offered by Github that hosts static webpages. We can create a static website by publishing all our posts. I will be using lots of content from the [Hugo site](https://gohugo.io/tutorials/github-pages-blog/), so this tutorial is very similar.  

##### Step 1: Modify config.toml file
We must first append some lines to the configuration file to tell Hugo that we want to publish the site. Append the following lines to your existing file from the last tutorial:  

```
contentdir = "content/post"
layoutdir = "layouts"
publishdir = "public"
canonifyurls = true
```

##### Step 2: Setup Git to Work
I borrowed this part from the official Hugo site. It is extremely comprehensive and not much more can be added. Make sure to perform these commands in order in [Git Bash](https://git-scm.com/downloads).
```
# Create a new orphand branch (no commit history) named gh-pages
git checkout --orphan gh-pages

# Unstage all files
git rm --cached $(git ls-files)

# Grab one file from the master branch so we can make a commit
git checkout master README.md

# Add and commit that file
git add .
git commit -m "INIT: initial commit on gh-pages branch"

# Push to remote gh-pages branch
git push origin gh-pages

# Return to master branch
git checkout master

# Remove the public folder to make room for the gh-pages subtree
rm -rf public

# Add the gh-pages branch of the repository. It will look like a folder named public
git subtree add --prefix=public https://github.com/[github username]/blog.git gh-pages --squash

# Pull down the file we just committed. This helps avoid merge conflicts
git subtree pull --prefix=public https://github.com/[github username]/blog.git gh-pages

# Run hugo. Generated site will be placed in public directory
hugo


# Add everything
git add -A

# Commit and push to master
git commit -m "Updating site" && git push origin master

# Push the public subtree to the gh-pages branch
git subtree push --prefix=public https://github.com/[github username]/blog.git gh-pages
```

Be sure to be signed in to avoid any authentication problems.

##### Step 3: Create deploy.sh file
This deploy.sh file will make deploying blog posts a lot easier in the future. Since Windows does not support shell scripts, we must run the script in Git Bash. The usage of this script is `bash deploy.sh "<my commit msg>"`.

```
#!/bin/bash

echo -e "\033[0;32mDeploying updates to GitHub...\033[0m"

# Build the project.
hugo

# Add changes to git.
git add -A

# Commit changes.
msg="rebuilding site `date`"
if [ $# -eq 1 ]
  then msg="$1"
fi
git commit -m "$msg"

# Push source and build repos.
git push origin master
git subtree push --prefix=public https://github.com/[github username]/blog.git gh-pages
```

That's it! Enjoy your new blog that's secure and easy to use.