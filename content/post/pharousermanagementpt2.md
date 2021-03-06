+++
Categories = ['smalltalk']
Tags = ['pharo', 'smalltalk', 'user management', 'image']
date = "2016-01-15T01:03:00-05:00"
title = "Further Extend a User Management Application in Pharo"

+++

My task was to add a few more fields to the existing ConstantManager package and implement some type of checking mechanism to ensure the password fields match. I accomplished this by adding the instance variables and adding a few methods.  

![screenshot](http://puu.sh/mwja3/6cb60041a4.png)  

I added a small check using if statements to check that the two passwords match. If the passwords do not match, an alert generated by `UIManager` pops up to warn the user.  

![screenshot](http://puu.sh/mwjxG/55f91bae81.png)  

You can see my current code [here](http://www.smalltalkhub.com/#!/~codethejason/usermanagementapp/).  


After this task, I would like to modify the code so an additional confirmPassword entry does not have to be created in the Contact database. Also, I would like to implement eMBee's suggestions of hiding the password (best solution found so far is *PasswordDialogBox*, but I would prefer it to be in the same form as the other fields) and making the role field into a list of strings instead of one long string with different roles. I am excited to continue working with Pharo smalltalk and will be taking on some more challenges!  