.. _nlib_usage:

Usage
#####

API
---

Neuron Library provides two kinds of API: 

* C: http://iotdk.intel.com/docs/master/mraa/
* Python3: http://iotdk.intel.com/docs/master/mraa/python/

Pin Mapping
-----------

This library is developed for ADLINK products.
Supported hardware and information about the ROSCube I/O pin mapping can be found at: https://github.com/Adlink-ROS/mraa#supported-hardware.

C Example
---------

1. Create a working space under the ``/home`` directory and navigate to it.

.. code-block:: bash

    mkdir neuronlibex_ws
    cd neuronlibex_ws

2. Copy the example file to your working space.

.. code-block:: bash

    cp -r /opt/adlink/neuron-sdk/neuron-library/share/mraa/* .

3. Create a "build" directory under your working space and navigate to it.

.. code-block:: bash

    mkdir build
    cd build

4. Build the examples.

.. code-block:: bash

    cmake ../examples/
    make

5. Run the examples under the directory ``~/neuronlibex_ws/build/c/``.

.. code-block:: bash

    cd c/
    #Examples should be run as root
    sudo ./<the example you want to execute>

Python Example
--------------

1. Create a working space under the ``/home`` directory and navigate to it.

.. code-block:: bash

    mkdir neuronlibex_ws
    cd neuronlibex_ws

2. Copy the example file to your working space.

.. code-block:: bash

    cp -r /opt/adlink/neuron-sdk/neuron-library/share/mraa/* .

3. Move into the directory with the python examples.

.. code-block:: bash

    cd examples/python/

4. Run the python3 examples:

.. code-block:: bash

    sudo python3 <the example you want to execute>.py

.. note::

    If the pin number is wrong, change the pin in the example.
    