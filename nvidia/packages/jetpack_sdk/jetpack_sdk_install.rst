Jetpack SDK Installation
########################

Since NVIDIA L4T 32.4.x support L4T OTA, users can download NVIDIA JetPack from NVIDIA’s official APT
repository.
For ROScube NVIDIA platform users, you can use apt to install NVIDIA JetPack compoments, e.g. CUDA, tensorrt.

1. Install the whole JetPack SDK
--------------------------------
Assuming your Jetson developer kit has been flashed with and is running **L4T 32.4.x**,
the following commands will install **all** ``JetPack``.

.. code-block:: bash

    sudo apt update
    sudo apt install nvidia-jetpack

.. warning:: 

    | It's **not suggested** to install ``nvidia-jetpack`` directly, because nvidia-jetpack is a meta package which will install **all JetPack SDK** compoments which occupy **8GB**.
    | You can only install ``particular`` JetPack SDK compoment.

2. Install particular JetPack SDK compoment.
--------------------------------------------
If we only want to use parts of JetPack SDK (e.g. CUDA) instead the whole JetPack SDK,
we can just install related library.

.. code-block:: bash

    # If we just want to use CUDA library
    sudo apt update
    sudo apt install nvidia-cuda nvidia-l4t-cuda

3. (Optional) Use CUDA in the container.
----------------------------------------
If you want to use CUDA in the container, follow the steps below.

a. Install CUDA library in the native host.
b. Use `Neuron Startup Menu <https://adlink-ros.github.io/roscube-doc/neuronsdk/neuron_startup_menu/index.html>`_ to install containers, which already include necessary packages and docker arguments.
c. Entering the containers and typing the following commands.

.. code-block:: bash

    # CUDA 10.2 only supports gcc8 and g++8
    sudo apt update
    sudo apt install gcc-8 g++-8
    sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-8 8
    sudo update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-8 8
    # Install libcudnn8-dev
    sudo apt install libcudnn8-dev
