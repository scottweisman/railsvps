# Sample app to deploy Rails to a VPS using Capistrano recipes
Check out
[Railscasts episode #337](http://railscasts.com/episodes/337-capistrano-recipes) for more info.
***

Uncomment gems

    gem unicorn
    gem capistrano

Create capfile

    $ capify .

Copy recipes you need from this sample app in config/recipes (nginx, postgresql, unicorn, rbenv, etc...)

Copy Capfile from this app

Change name of the app and ip address where needed (deploy.rb)

Go get a server: [http://digitalocean.com](http://digitalocean.com)
- Recommended setup: Ubuntu 10.04 x64

SSH to server

    $ ssh root@0.0.0.0

Create new user named deployer with admin privileges

    $ sudo adduser deployer

Give new user admin privileges

    $ visudo

    #User privileges
    root      ALL=(ALL:ALL) ALL
    deployer  ALL=(ALL:ALL) ALL

Cap Install

    $ cap deploy:install

Cap Setup

    $ cap deploy:setup

Cap Deploy

    $ cap deploy:cold

Future changes can be pushed with cap deploy

    $ cap deploy

Run Rails Console on server

    $ cap rails:console

Tail logs

    $ cap tail