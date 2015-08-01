Mri Server
==========

The Mri-server is built on Reportr_ and so additional info can be found there, as well as on the server README_.

.. _Reportr: https://github.com/Reportr/dashboard
.. _README: https://github.com/Mri-monitoring/Mri-server/blob/master/README.md

Automatic Deployment
--------------------

Deploying via Heroku is the easiest way to get started with Mri.

By deploying this app to Heroku you can easily start your own private instance of Mri-server with minimal configuration. Heroku is a scalable cloud platform that offers a free-tier sufficient to run your own Mri-server. Simply click the button below to get started. You will need to create an account and provide credit card information. 

.. tip:: 
    Don't worry -- credit card information is only used if you try and scale up your Mri-server to multiple machines. As long as you stick to the default free dyno you will not be charged.

Heroku will ask you to set authentication variables and will automatically set the remaining configuration variables. You will also be given the option to choose an app name.

.. image:: https://www.herokucdn.com/deploy/button.png
    :target: https://heroku.com/deploy?template=https://github.com/Mri-monitoring/Mri-server

Manual Deployment
-----------------
To run Mri-server locally you will need to install the Heroku toolbelt.::

$ git clone https://github.com/Mri-monitoring/Mri-server.git 
$ npm install .

To run it locally, you should use foreman_ (configuration can be stored in a env_ file)::

$ foreman start

.. _foreman: http://ddollar.github.io/foreman/
.. _env: https://devcenter.heroku.com/articles/config-vars#local-setup

To deploy it on Heroku ::

$ heroku config:set MONGODB_URL=mongodb://...
$ heroku config:set AUTH_USERNAME=...
$ heroku config:set AUTH_PASSWORD=...
$ git push heroku master

