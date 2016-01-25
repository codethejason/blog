+++
Categories = ['smalltalk']
Tags = ['smalltalk', 'pharo', 'teapot', 'squeak', 'rest', 'api', 'zinc']
date = "2016-01-24T23:05:17-05:00"
title = "REST API with Teapot"

+++

Today, my task was to write a REST API in Pharo using the Teapot framework. Teapot is a packaged designed to make making REST APIs with Pharo A LOT easier than writing a REST API from scratch in Zinc. For example, to output *Hello World* when a user navigates to `/hello`, this is all the code that is needed:  

```
Teapot on
    GET: '/welcome' -> 'Hello World!';
    start.
```

I wrote a package named `UserAPI` on [SmallTalkHub](http://www.smalltalkhub.com/#!/~codethejason/UserAPI/) that relies on the `ContactManager` package [here](http://www.smalltalkhub.com/#!/~codethejason/usermanagementapp/) to retrieve a list of users and display it as JSON in the browser after a user navigates to `/users`. I took some inspiration from [this blog](https://skrishnamachari.wordpress.com/2014/08/28/teapot-pharo-web-rest-framework-it-aint-micro/). To set it up, load the packages into your Pharo image. After that, run this command in Playground to start up the app: 

```
teapot := Teapot configure: {
#defaultOutput -> #json. 
#port -> 8080. 
#debugMode -> true 
}.
teapotInstance := TeapotRequestHandler new.
teapotInstance runApp: teapot.
```

For production, you can set the debugMode to false. To stop the server, stop all instances of Teapot:  
```
Teapot stopAll.
```

That's it! In my very simple app, I really only have two methods: `#handleGetRequest:` and `#runApp:`. The `runApp` method starts Teapot and defines the path Teapot should "activate" in its API. The `handleGetRequest` method handles the request when the `/users` page is hit. It calls the Contact class which returns an ordered collection. The app uses NeoJSON to parse the ordered collection to JSON suitable for a RESTful API. 



