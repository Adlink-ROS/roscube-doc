.. _gmsl_camera:

GMSL 2 Camera
#############

Supported model: **ROScube RQX-58G series only**

**RQX-58G** is one of the **ROScubeX series model**, which extends **GMSL 2** standard protocol cameras.

**GMSL 2** is SerDes protocol which provides high bandwidth and low latency video streaming for high resolution cameras.

Unlike IP camera or other USB UVC standard cameras,
GMSL 2 camera provide RAW frame which has not been compressed by certain encoding algothrim, e.g. H.264 or H.265.

.. warning::

    GMSL 2 camera does not support hot-plugging.
    Please connect the camera before bootup, or ROScube-X can not detect it.

**Supported GMSL 2 camera**

The following table is the supported GMSL 2 camera list of RQX-58G.

+-------------------------+--------------+-------+-----------------+------------------------------------------------------------------------------------------------------------------+
| Camera Model            | Vendor       | ISP   | Video Framework | website link                                                                                                     |
+=========================+==============+=======+=================+==================================================================================================================+
| LI-AR0233-GMSL2         | Leopard      |       | NVIDIA Argus    | `link <https://www.leopardimaging.com/product-category/autonomous-camera/maxim-gmsl2-cameras/li-ar0233-gmsl2/>`_ |
+-------------------------+--------------+-------+-----------------+------------------------------------------------------------------------------------------------------------------+

**Table of Contents:**

.. toctree::
   :maxdepth: 1

   system_diagram.rst
   camera_driver.rst
   camera_usage.rst
   frame_sync.rst