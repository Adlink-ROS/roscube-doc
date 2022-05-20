.. _time_sync:

Sensors Time Synchronization
============================

This scenario will show you how to get time-synced data from different sensors.

Sensors are the eyes of robots / automotive.
We use sensors to collect outside environment information.
It's really important to analyze sensors data and make the right decision, like avoiding obstacles.

However, each kind of sensor has its own charateristics.
For example, lidars can detect obstacles precisely, while cameras can do object detection.
Therefore, doing sensor fusion of these sensors can have all the advantages and cover their disadvantages.

To fuse data from different sensors with high quality,
we should make the time difference among the data from these sensors is as smaller as possible.

In the following sections, we'll first introduce the hardware/software architecture of the scenario.
Then show how to connect these sensors to ROScube and how to configure them.
Software configuration section will guide you how to setup ROS environment and install necessary packages.
Finally, we can run the application and show the result.

**Table of Contents:**

.. toctree::
   :maxdepth: 1

   architecture.rst
   sensor_configuration.rst
   software_configuration.rst
   synchronization.rst
