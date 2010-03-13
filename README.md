Integrity Heroku
================

Deploy [Integrity](http://integrityapp.com) on [Heroku](http://heroku.com)'s platform.

    git clone git://github.com/sr/integrity-heroku
    cd integrity-heroku
    heroku create
    git push heroku master
    heroku rake db
    heroku open

This is being used to power the CI servers for my open source ruby projects:

1. [Integrity 1.8.6](http://integrity186.heroku.com/)
2. [Integrity 1.8.7](http://integrity187.heroku.com/)
3. [Integrity 1.9.1](http://integrity191.heroku.com/)

For future reference, here is my .git/config:

    [remote "sr"]
    	url = git://github.com/sr/integrity-heroku.git
    	fetch = +refs/heads/*:refs/remotes/sr/*
    [remote "origin"]
    	url = git@github.com:myronmarston/integrity-heroku.git
    	fetch = +refs/heads/*:refs/remotes/origin/*
    [remote "186"]
    	url = git@heroku.com:integrity186.git
    	fetch = +refs/heads/*:refs/remotes/186/*
    [remote "187"]
    	url = git@heroku.com:integrity187.git
    	fetch = +refs/heads/*:refs/remotes/187/*
    [remote "191"]
    	url = git@heroku.com:integrity191.git
    	fetch = +refs/heads/*:refs/remotes/191/*
    [branch "master"]
    	remote = origin
    	merge = refs/heads/master

There are a couple of convenience rake tasks:

    rake deploy

This deploys to all 3 heroku apps.

    rake heroku COMMAND="whatever --arg value"

This runs "heroku whatever --arg value" against all 3 heroku apps.

Want a free CI server for your open source ruby project, running against all 3 versions of ruby?
Let me know and I'll be happy to add your projects.  Or feel free to use this to setup your own!