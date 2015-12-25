+++
Categories = ['fossasia site']
Tags = ['setup', 'webhook', 'gh-pages', 'server', 'github']
date = "2015-12-25T00:25:35-05:00"
title = "Setting Up a Webhook for Github"

+++

You can set up a webhook for so that each time a contributor opens or reopens a pull request on your repository/fork, a bot may comment a live version of the contributor's site on the pull request.

##### Add webhook

First, you must add a webhook to your repository. To do this:

1) Go to your repository settings and select *Webhooks & Services*.  
2) Click *add webhook*. You can make up a random payload URL for now. Your secret key can be anything (be sure to record this).  
3) Click *let me select individual events* and only check the *pull request* checkbox.  
4) Create the webhook.  

You should see something like this afterwards (with a random link):  

![example](http://puu.sh/m7QnB/804187cbaf.png)  

##### Setting up your bot

You must first create a new github account to host the bot (or you can use your own account if you want it to act as the bot).  Go to your [settings](https://github.com/settings/tokens) to create a new personal access token. Leave it on the default permissions.

1) Clone https://github.com/codethejason/fossasiaprbot to a public area on your server. Something like `http://example.com/fossasiaprbot/webhook.php` will be your webhook URL, so please edit that in the repository settings.  
2) On your server, install php and php5-curl.  
3) Create a `secret.json` in the cloned directory file like the following:  

```
{
  "githubkey": "your secret key you recorded in part 1",
  "token": "your secret access token"
}
```

##### Testing the webhook

You can now test your webhook by creating a pull request on your fork.

Sign into another account and make a file change in the *gh-pages* branch and make a pull request. Test that the bot now posts the link to the live website.
