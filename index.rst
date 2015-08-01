.. mri documentation master file, created by
   sphinx-quickstart on Fri Jul 31 12:50:25 2015.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to Mri's documentation!
===============================

Mri is a set of tools and applications to allow you to easily monitor neural network training from anywhere.

Included in Mri is:

* A webserver based on Reportr_ that allows you to easily monitor training from anywhere.
* A Python interface to the server API for use with Theano/Pylearn/Blocks/Keras/etc.
* An interface to Caffe to enable easy hyperparameter testing and monitoring of multiple network architectures. 

.. warning::
    Mri is a new project and is currently under development. All projects and APIs are subject to change, and 
    while incompatability warnings will be released, you should not expect long term stability

.. tip::
    If you are interested in Mri, please feel free to open issues on Github_, and to contribute via pull requests

.. _Reportr: https://github.com/Reportr/dashboard
.. _Github: https://github.com/Mri-monitoring

Contents:

.. toctree::
   :maxdepth: 1
    
   getting_started.rst
   mriserver.rst
   mriapp.rst
   mripython.rst
   python/index.rst
   app/index.rst



Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
