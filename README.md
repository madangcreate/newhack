# newhack
Testing
.. code:: python


    import time

    import background


    @background.task
    def work():
        # Do something expensive here.
        time.sleep(10)


    for _ in range(100):
        work()


Advanced Usage
--------------

.. code:: python

    import time

    import background

    # Use 40 background threads.
    background.n = 40
    

    @background.task
    def work():
        time.sleep(10)

    @background.callback
    def work_callback(future):
        print(future)


    for _ in range(100):
        work()

Installation
------------

::

    $ pipenv
