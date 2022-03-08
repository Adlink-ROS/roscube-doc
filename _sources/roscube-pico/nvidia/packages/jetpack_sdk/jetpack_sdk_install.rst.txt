Jetpack SDK Installation
########################

Since Nvidia L4T 32.4.x support L4T OTA, users can download Nvidia JetPack from Nvidia’s official APT
repository.
For ROScube-X users, you can use apt to install Nvidia JetPack compoments, e.g. tensorrt, cuda.

1. Install nvidia-l4t-jetson-multimedia-api
-------------------------------------------
Before installing JetPack SDK, you should install nvidia-l4t-jetson-multimedia-api in a proper ver-
sion coresponding to L4T version.

.. code-block:: bash

    sudo apt update
    sudo apt install nvidia-l4t-jetson-multimedia-api

.. warning:: 
    | It's **not suggested** to install ``nvidia-jetpack`` directly, because nvidia-jetpack is a meta package which will install **all JetPack SDK** compoments which occupy **8GB**.
    | You can only install ``particular`` JetPack SDK compoment.

2. Install the whole JetPack SDK
--------------------------------
Assuming your Jetson developer kit has been flashed with and is running **L4T 32.3.1** or higher,
the following commands will install **all** ``JetPack``.

.. code-block:: bash

    sudo apt update
    sudo apt install nvidia-jetpack

3. Install particular JetPack SDK compoment.
--------------------------------------------
(e.g. ``nvidia-tensorrt``)

.. code-block:: bash

    sudo apt update
    sudo apt install nvidia-tensorrt