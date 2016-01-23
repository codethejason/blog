+++
Categories = ['smalltalk']
Tags = ['pharo', 'smalltalk', 'zinc', 'webserver']
date = "2016-01-21T19:06:06-05:00"
title = "Creating a Web App with Zinc"

+++

Working with Zinc on Pharo Smalltalk to create a small web application was extremely different than creating a Web App with PHP, NodeJS, or even Python. Zinc is a framework in smalltalk that deals with the HTTP networking protocol using the reference platform of Pharo. I have followed [this](http://zn.stfx.eu/zn/build-and-deploy-1st-webapp/) tutorial to develop a web app which allows the user to change the picture.  I have to say that the process was a lot more complicated than I thought.

##### Serving a Page
All the instructions are in the tutorial, so I will be summarizing what I did. I first worked on serving up the HTML page which took a lot more steps than I thought. Normally, I can just create an HTML file on my system and open it in a web browser. I need to handle the request of the user from Zinc to be able to serve it. Then, I added the functionality for Pharo to download the image and serve it to the user on the */image* directory of the website. I then added the ability to upload images from the user and ensured the data was a valid image by performing a few checks. 

![scrn](http://puu.sh/mETNa/638ea56322.jpg)  

##### Adding Tests
I added some tests to ensure that the web application was running as expected. Each tests references the `withServerDo` method which controls the server to make sure it starts and stops properly. The first test checks to make sure there is HTML on the */image* path. The second test ensures that the default raw image was being outputted correctly by asserting the equality of the served image and the image in the app object. The third test makes sure that the uploaded image changed to what was expected by using a sample image.  

![scrn](http://puu.sh/mETKh/fc23c96713.jpg)

##### Final Thoughts
The process of serving a simple web application was quite complex. Although the application flow makes sense, I probably would not use Zinc to serve up web applications in production. The code has a few methods I don't understand the point of. For example, `#value` does not seem to need to exist when `#handleRequest:` could be called. Keeping in mind that Pharo was designed for learning and understanding code deeply and intuitively, I think it certainly did its job in that area :).


##### Run My Code
Just want to see the final result? Get the `MyFirstWebApp` package from [here](http://www.smalltalkhub.com/#!/~codethejason/WebApp/).  
To start the server, run   

```
ZnServer startDefaultOn: 8080.
ZnServer default delegate map: #image to: MyFirstWebApp new.
```

Open the server at [http://localhost:8080/image](http://localhost:8080/image).  

To stop the server, run   

```
ZnServer stopDefault.
```
