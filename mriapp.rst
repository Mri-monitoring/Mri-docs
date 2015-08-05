Mri Application (Caffe)
=======================

The Mri application allows you to monitor Caffe training, as well as easily test hyperparameters and different architectures all at once. See getting started for instructions on how to install the Mri-app

Task List or Standalone
-----------------------
Mri-app offers two modes: a simple prototxt based mode and a more complete task list mode. 

In task list, you will specify a list of tasks in the configuration file and Mri-app will run all of those tasks in order. In this mode each task requires some setup -- a task requires a model file, a solver file, and a task file. Use the hyperparameter scripts to automatically generate these tasks based on a set of hyperparameters to test::

$ python MriApp.py

In prototxt mode, simply pass a prototxt file to Mri-app and Mri will run on that single prototxt. While less flexible, this mode requires almost no setup::

$ python MriApp.py --override_solver /path/to/solver.prototxt

Task Files
----------
A task file specifies additional information to Mri-app for each task to take place. At the moment, training is the only supported task. A task file looks like this:

.. code-block:: javascript

    {
        "directives": [
            {
                "type": "train", 
                "parameters": {
                    "solver": "/path/to/solver/solver.prototxt",
                    "resume": "/path/to/snapshots/snapshots_iter_20000.solverstate"
                }
            }
        ], 
        "id": "some_id_194183591835", 
        "title": "This net title"
    }

The `resume` field is optional and will pass `--snapshot` to Caffe to allow training to resume from a `.solverstate` file.

Configuration
-------------
The Mri configuration file is a plain-text file that contains all the required configuration settings. See the configuration template for an example. Note that not all modules are required, i.e. if you only plan to use the matplotlib-dispatch option, you do not need any other dispatch configuration settings.

Hyperparameter Testing
----------------------
Included in the `script` directory is a python script that makes it easy to test many hyperparameters in Caffe.

To use, first copy the configuration example to `config` and add your own values. The model and solver templates should simply replace any fields to be replaced by `%{field-name}%`. For example, you may have the following excerpt in your `solver.protobuf` file::

    # The base learning rate, momentum and the weight decay of the network.
    base_lr: %{base_lr}%
    momentum: 0.9
    weight_decay: %{weight_decay}%
    # The learning rate policy
    lr_policy: "step"

Then, create the hyperparameter file::

    base_lr: 1e-5, 1e-6, 1e-7
    weight_decay: 0.2, 0.1, 0.01

The field names can be in either the model or solver, just use unique names

To run script::

    python generate_tasks random -n 5       # Generates 5 random tasks sampled from the hyperparameter distribution
    python generate_tasks grid              # Generate tasks for all possible hyperparameter values


