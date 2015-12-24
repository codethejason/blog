+++
Categories = ['open-event']
Tags = ['orga-server', 'github', 'setup', 'virtual machine', 'windows']
date = "2015-12-23T19:18:08-05:00"
title = "Setup FOSSASIA's Orga Server"

+++

Today, I will be teaching you how to locally setup the [open event orga server](https://github.com/fossasia/open-event-orga-server) which manages all the data of an event. I will let you know the exact process I went through.

##### Step 1: Fork and clone the repository
Make sure you clone the repository from [Github](https://github.com/fossasia/open-event-orga-server) into your default folder. You should also fork the repository if you are thinking of contributing to it. At first I tried to install Vagrant by myself and clone the repository later, but cloning the repository first is much easier since there is a preset vagrant file.

![clone repository](blogimages/clonerepo.png)

##### Step 2: Install Vagrant and VirtualBox
At this point, go to [Vagrant](http://vagrantup.com) and install the latest version. Afterwards, navigate to [VirtualBox](https://www.virtualbox.org/wiki/Downloads) to install VirtualBox 5 for Windows. Restart your computer after the installation.

##### Step 3: Set up Box and connect to it
Go to your command prompt and type in `vagrant up` to initialize the setup process. The default operating system is Ubuntu 14.04 LTS. You should see this after running the command:  
![clone repository](blogimages/vagrantup.png)
After waiting three to ten minutes, your virtual machine will be ready. Go into an ssh client (for example [PuTTy](http://www.putty.org/)) and login to the server using the following credentials:

```
host: localhost or 127.0.0.1
port: 2222
username: vagrant
password: vagrant
```

Navigate to */vagrant* by typing in `cd /vagrant`. You should see something like this:

![window](blogimages/consolewindow.png)

##### Step 4: Install Open Orga Server
To avoid confusion, exit out of any command prompts. At any point, if you want to shut down the VM, type `vagrant halt` in the open orga server directory.  
Now, create the python database given in the *create_db.py* file and start the Nginx server by running these commands:

```
python create_db.py
python manage.py runserver -h 0.0.0.0 -p 5000
#Address is 0.0.0.0 so the app binds to the public ips on the box (for accessing it on our machine)
```

You are done! View the web application at [localhost:8001](localhost:8001).

![window](blogimages/finished.png)


### Troubleshooting
I went through a few issues to get the server up and running. For example, I was stuck on this screen for a while:

![stuck](blogimages/stuck.png)

To fix it, you must restart your computer and boot into BIOS (usually by function keys or a special power button on the computer). Afterwards, select virtualization and enable it.