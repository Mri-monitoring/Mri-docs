Getting Started
===============

This is a minimal getting started guide for Mri. For more detailed instructions on each component see its respective page.

Deploying A Server
------------------

Getting started with Mri is a two step process. First you will need to get the server component running. While you can run the server on your own machine, the easiest way to run the server is to use a free Heroku account. 

By deploying this app to Heroku you can easily start your own private instance of Mri-server with minimal configuration. Heroku is a scalable cloud platform that offers a free-tier sufficient to run your own Mri-server. Simply click the button below to get started. You will need to create an account and provide credit card information. 

.. tip:: 
    Don't worry -- credit card information is only used if you try and scale up your Mri-server to multiple machines. As long as you stick to the default free dyno you will not be charged.

Heroku will ask you to set authentication variables and will automatically set the remaining configuration variables. You will also be given the option to choose an app name.

.. image:: https://www.herokucdn.com/deploy/button.png
    :target: https://heroku.com/deploy?template=https://github.com/Mri-monitoring/Mri-server

Using Caffe as a Client
-----------------------

Caffe users can use the Mri-app to run and monitor Caffe training, as well as automatically generate tasks for hyperparameter testing. 

First you will need to install the Python client::

$ pip install -e git+https://github.com/Mri-monitoring/Mri-python-client.git#egg=mri-master

Then install the application::

$ git clone https://github.com/Mri-monitoring/Mri-app.git
$ cd Mri-app
$ cp config.Template config.txt

Make the appropriate edits to the config file (see template)::

$ cd ..
$ pip install -r requirements.txt
$ python setup.py install

Then run the app::

$ cd mriapp
$ python MriApp.py --override_solver /path/to/solver.prototxt

Using the Python API as a Client
--------------------------------

Mri offers a Python API to allow easy integration with Python based deep learning packages.::

$ pip install -e git+https://github.com/Mri-monitoring/Mri-python-client.git#egg=mri-master
