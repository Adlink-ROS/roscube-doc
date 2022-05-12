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
we should make the timestamp difference among these sensors is as smaller as possible.

**Table of Contents:**

.. toctree::
   :maxdepth: 1

   architecture.rst
   configuration.rst
   synchronization.rst
   result.rst
