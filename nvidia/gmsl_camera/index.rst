.. _gmsl_camera:

GMSL Camera
###########

Supported model: **ROScube RQX-58G ONLY**

**RQX-58G** is one of the **ROScubeX series model**, which extends **GMSL2** standard protocol cameras.

**GMSL** is SerDes protocol which provides high bandwidth and low latency video streaming for high resolution cameras.

Unlike IP camera or other USB UVC standard cameras, GMSL camera provide RAW frame which has not been compressed by certain encoding algothrim, e.g. H.264 or H.265.

**Before start you should prepare the following items:**

 * ROScube RQX-58G
 * Leopard AR0233 GMSL cameras

**Table of Contents:**

.. toctree::
   :maxdepth: 1

   system_diagram.rst
   camera_driver.rst
   test_result.rst
   frame_sync.rst