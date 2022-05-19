Software Configuration
======================

After sensor configuration, here show you how to make software configuration

* Installation ROS environment
* Installation camera daemon
* Installation sensors_pkg

Installation ROS Environment
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

We have provided the way how to isntall ROS enviroment, please click `<https://adlink-ros.github.io/roscube-doc/neuronsdk/neuron_startup_menu/installation.html>`_.

.. note:: 
    
    **Install ROS environment in container**.

    Since NVIDIA platform BSP is Ubuntu 18.04, it's inconvenient to run ROS 2 foxy, which is the ROS LTS version.
    
    Open Robotics only supports **ROS 2 foxy** on Ubuntu 20.04.

Installation Camera Daemon
^^^^^^^^^^^^^^^^^^^^^^^^^^

Building the daemon from github.

Building
--------

.. code-block:: bash

    cd ~
    git clone https://github.com/Adlink-ROS/camera_trigger_daemon.git
    cd camera_trigger_daemon

Installation
------------

.. code-block:: bash

    # Install Mraa
    sudo add-apt-repository ppa:mraa/mraa
    sudo apt-get update
    sudo apt-get install libmraa2 libmraa-dev libmraa-java 
    sudo apt-get install python-mraa python3-mraa node-mraa mraa-tools

    # Install Neuron Library
    sudo apt install neuron-library

For more information about Neuron Library, click `<https://adlink-ros.github.io/roscube-doc/neuronsdk/neuron_library/index.html>`_.

Usage
-----

Before start the daemon for **Frame Synchronization**, make sure that **interfacing** and **configurations** are correct.


The daemon provides four function:

* Start : trigger cameras with external signal.
* Stop : stop the daemon.
* Restart : stop and then start.
* Start_free : trigger cameras without external signal.

Default option:

* GPIO(ISR) = 5 pin
* trigger hz = 5 hz

.. code-block:: bash

    # Start the daemon
    sudo python3 isr_camera.py start
    # Otherwise, trigger cameras by 10 hz and setting GPIO: 6 pin to interrupt.
    sudo python3 isr_camera.py start 10 6

    # Stop the daemon
    sudo python3 isr_camera.py stop

    # Restart the daemon 
    sudo python3 isr_camera.py restart

    # Start the daemon without the PPS
    sudo python3 isr_camera.py start_free
    # Otherwise, trigger cameras by 10 hz.
    sudo python3 isr_camera.py start_free 10

.. warning:: 

    If the daemon didn't work, please check the ``daemon.log`` file.

Testing
-------

.. note:: 
    
    You should trigger the frame first before running camera streaming.

    And make sure the camera driver is installed.

    You can check camera devices by using command in terminal : ``ls /dev/video*``.

Use **GStreamer NVArgusCameraSrc plugin** to preview the video streaming by following command below:

.. code-block:: bash

    # Open a terminal and type command to open camera 1's video streaming.
    gst-launch-1.0 nvarguscamerasrc sensor-id=0 ! 'video/x-raw(memory:NVMM), width=2048, height=1280, framerate=30/1' ! nvvidconv flip-method=0 ! 'video/x-raw, format=(string)I420' ! xvimagesink -e
    # Can change the snesor-id for other cameras.

For more information, click `<https://adlink-ros.github.io/roscube-doc/roscube-x/gmsl_camera/camera_usage.html>`_.

Installation ``sensors_pkg``
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Install ``sensors_pkg``, which is provided by **Adlink-ROS**, to view the timestamp of camera, lidar and imu.

Install necessary packages
--------------------------

.. code-block:: bash

    sudo apt install wget

Get the code
------------

.. code-block:: bash

    mkdir -p sensors_pkg_ws/src
    cd sensors_pkg_ws
    wget https://raw.githubusercontent.com/Adlink-ROS/sensors_pkg/main/sensors.repos
    vcs import src < sensors.repos

Build xsens library 
-------------------

Refer to https://github.com/bluespace-ai/bluespace_ai_xsens_ros_mti_driver


.. code-block:: bash

    pushd src/bluespace_ai_xsens_ros_mti_driver/lib/xspublic && make && popd

Build
-----

.. code-block:: bash

    rosdep install --from-paths src --ignore-src -r -y
    colcon build --symlink-install
    source install/local_setup.bash