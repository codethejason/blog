+++
Categories = ['other gci projects']
Tags = ['Codeigniter', 'PHP', 'MVC', 'framework', 'MySQL', 'Apache']
date = "2015-12-19T23:19:50-05:00"
title = "Developing a Register and Login System with Codeigniter"

+++

[Codeigniter](https://www.codeigniter.com/) is a MVC PHP application framework designed to make developing a web application easier and faster. It has a large and active [community base](http://forum.codeigniter.com/) with a pretty good amount of [documentation](http://www.codeigniter.com/user_guide/). For me, this was my first PHP framework I used. I have always thought using frameworks like Codeigniter or Laravel is bad, but I may have to change my mindset after actually using one. The time it took me from start to end in developing this application is shorter than the time it would take to develop a 'vanilla' PHP application even though this is my first time using Codeigniter. You may see my final app on my [temporary site](http://192.111.152.115:17210/usersystem/). 

### Making the Login/Register Application
I will go over the general gist of what I did. You can see the full code on my [repository](https://github.com/codethejason/usersystem). I basically made a simple login and register system with validation. Once a user registers, he or she can login. After logging in, the user may see an array of all the registered users. He or she then may log out and can login after that. It's a very basic application, but what is important for this task is understanding the basics of Codeigniter.

#### First the Basic Configuration
After downloading Codeigniter 3.0 from [here](https://www.codeigniter.com/download), I set up the directory and apache2.conf on my server (I am  using LAMPP). I pasted this code into the <Directory /var/> in apache to configure mod_rewrite settings for manipulating the URL:
```
#Source: https://gist.github.com/philipptempel/4226750
<IfModule mod_rewrite.c>
  RewriteEngine On
  # !IMPORTANT! Set your RewriteBase here and don't forget trailing and leading
  #  slashes.
  # If your page resides at
  #  http://www.example.com/mypage/test1
  # then use
  # RewriteBase /mypage/test1/
  RewriteBase /
  RewriteCond %{REQUEST_FILENAME} !-f
  RewriteCond %{REQUEST_FILENAME} !-d
  RewriteRule ^(.*)$ index.php?/$1 [L]
</IfModule>
```
I went into the *applications/config* folder to modify the database, autoload, and config files according to my needs. I then created a new controller in *controllers/* named main and set it as default in *config/routes.php*.

#### Making the Login and Register Portion
I then proceeded to create the login method in my *Main.php* and made a login_validation method that took advantage of the form_validation library to check that all the requirements are met (i.e. all fields required, user filled out email, etc. ). I created a view for the login form.  

Then, I created the register portion, which was basically the exact same as the login except for a confirm password field, a db insert method, and additional validation.

#### Finishing the Application
Finally, I was almost done with the application after about five consecutive hours (the Model_users model was a headache to deal with). I made some final changes including printing out the results array from the db->get() query.

It was an interesting experience using a PHP framework for the same time. Sure it took some time to learn, but I think it was well worth as it eased my animosity towards frameworks. Everything just felt so simple -- no creating a validation class, no creating a configuration manager, fewer worries about security, and more. I will most definitely consider using some sort of PHP framework for my next application.