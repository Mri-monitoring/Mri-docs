Mri Python Client
=================

The Python client for Mri offers a simple interface to the Mri-server. See Getting Started for installation instructions. 

Tutorial
--------
For a commented version, see `examples/python_bindings`.

Import 

>>> from mri import MriServer
>>> from mri import TrainingEvent
>>> import time

Setup server (one time)

>>> server = MriServer(SERVER_ADDR, USER, PASS)
>>> task = {'title': 'Example Bindings', 'id': '001'}
>>> dispatch = server.new_dispatch(task)
>>> dispatch.setup_display('iteration', ['iteration', 'loss', 'accuracy'])

Train!

>>> for i in range(1, 10):
>>>     training_data = {'iteration': i, 'loss': -i, 'accuracy': i/10.0}
>>>     event = TrainingEvent(training_data, 'iteration')
>>>     print('Sending event {} to server'.format(event))
>>>     dispatch.train_event(event)
>>>     time.sleep(1)
