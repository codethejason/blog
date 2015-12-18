+++
date = "2015-12-16T22:26:09-05:00"
title = "Setup a Blog using Hugo on Windows"

+++

Today, I created a blog with the Hugo static website generator, an engine very similar to Jekyll. Hugo allows a user to easily setup a secure and customizable blog in a short period of time. It is open source and constantly updated to ensure the latest features and bug fixes.  

Setting up Hugo is a piece of cake, even on Windows. First, I recommend watch the [quickstart guide](http://gohugo.io/overview/quickstart/). It is extremely informative and got me setup in less than ten minutes.  

##### Step 1: Install Hugo
To install Hugo and access it from the command prompt, first scroll down to the bottom of the [releases](https://github.com/spf13/hugo/releases) and download the appropriate executable. After unzipping the file, rename the file name to **hugo.exe**. Navigate to your *AppData\Roaming* (access it by typing in *%appdata%* in the *Windows + R* dialog) in Windows Explorer and create a new folder called **hugo**, and copy the binary inside the folder. In the run dialog, type in `rundll32 sysdm.cpl,EditEnvironmentVariables` to access the system variables. Under the user variables, edit the variable that says *PATH* by appending a semicolon and the location of the hugo folder in appdata. After saving, you are now ready to run hugo on the command line.

##### Step 2: Configure Hugo
Create a folder in a location of your choice. Type in the following commands in order:
```
cd C:\<Your file location>
mkdir hugo
cd hugo
hugo new site
hugo new firstpost.md
git clone --depth 1 --recursive https://github.com/pdevty/material-design themes/material-design
```
If you want to install other themes, feel free to [check them out](https://github.com/spf13/hugoThemes).

Edit the *config.toml* file to say this:
```
baseURL ="Your URL"
languageCode = "en-us"
title = "Your Name's Blog"
theme = "material-design"
```

###### Step 3: Run Hugo
Now, you can add any content below the plus signs to your new markdown file located at *content/posts/firstpost.md* in your favorite text editor. The formatting is markdown, which you can read about on [Github](https://help.github.com/articles/markdown-basics/). Remove the `draft = true` statement on top of the page and run `hugo server` to generate your content. Your content will be available on **localhost:1313** in your browser.

<img src="http://puu.sh/lYxNn/a7dbbbe8c3.jpg" width="300" alt="Final Result">

