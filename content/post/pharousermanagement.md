+++
Categories = ['smalltalk']
Tags = ['pharo', 'smalltalk', 'user management', 'image']
date = "2015-12-29T10:02:57-05:00"
title = "Extend a User Management Application in Pharo"

+++

My task was to extend an address book located on this blog: http://magaloma.blogspot.de/2011/01/pharo-gui-with-polymorph.html. It featured adding, editing, and deleting a contact and only had two fields: first name and last name. I extended the applicatino by adding an email field after loading the program in Pharo 4.0.

```
Gofer it
 squeaksource: 'Pharocasts';
 package: 'ContactManager';
 load.
 
 ```
 
 **First**, in the contact class, I added an instance variable called email. After that, I could add methods in the *accessing* protocol that returns the email and also add the email to be printed in the printOn method in the *printing* protocol. Last, I amended `ContactListEditor>>#contacts` to include actually printing out the email address.  
 
 ![email](http://puu.sh/mcywp/bea6834b21.png)
 
Smalltalk is a reflective language and was designed for constructionist learning, a method designed to reconstruct a learner's knowledge rather to transmit new knowledge. In my short experience using Pharo Smalltalk, I found it quite different primarily due to the enivironment it is being run in but also due to the syntax. I never coded in any language that needed to be run in its own image and found it to be quite odd. Pharo smalltalk's syntax also seems very different from the syntax I am used to seeing. I hope to continue doing smalltalk tasks for Google Code-in and explore smalltalk further even after GCI.  