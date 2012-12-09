# This is an app with example Capistrano recipes

Uncomment gems

    gem unicorn
    gem capistrano

Create capfile

    $ capify .

Copy recipes you need (nginx, postgresql, unicorn, rbenv, etc...)

Change name of app where needed

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
