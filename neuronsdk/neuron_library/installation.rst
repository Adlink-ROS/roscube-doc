.. _nlib_installation:

Installation
############

There are two ways to install Neuron Library.

* Install from apt server
* Build from source code

Install from apt server
-----------------------

* Setup ADLINK apt repository

.. code-block:: bash

    curl -L --insecure https://neuron.adlinktech.com/debian/repo_signing.key | sudo apt-key add -
    echo 'Acquire::https::neuron.adlinktech.com::Verify-Peer "false";' | sudo tee /etc/apt/apt.conf.d/99roscube > /dev/null
    echo 'Acquire::https::neuron.adlinktech.com::Verify-Host "false";' | sudo tee -a /etc/apt/apt.conf.d/99roscube > /dev/null
    echo "deb [arch=$(dpkg --print-architecture)] https://neuron.adlinktech.com/debian/common $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/roscube.list > /dev/null
    sudo apt update

* Install Neuron Library from ADLINK apt repository

.. code-block:: bash

    sudo apt install neuron-library

* After installation, the Neuron Library will be located in ``/opt/adlink/neuron-sdk/neuron-library/``.

Build from source code
----------------------

You can also build Neuron Library from source code.
The source code of Neuron Library can be found at https://github.com/Adlink-ROS/mraa, and include usage examples and detailed information of the latest version.
