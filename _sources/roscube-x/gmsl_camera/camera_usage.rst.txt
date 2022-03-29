.. _camera_usage:

Camera Usage
############

Different video frameworks have different methods to run cameras.
You should check which video framework your camera is and select the right method.

Here we show how to run cameras with gstreamer plugin based on NVIDIA Argus or V4L2.

NVIDIA Argus
------------

Cameras without ISP can use **Argus API** to preview the camera's video streaming, 
or you can use **GStreamer NVArgusCameraSrc plugin** to preview the video streaming.

Make sure you have modified **sensor-id=0** on the following command.

+---------------+-----------+
| Camera Number | Sensor ID |
+===============+===========+     
| Camera 1      | 0         |
+---------------+-----------+
| Camera 2      | 1         |
+---------------+-----------+
| Camera 3      | 2         |
+---------------+-----------+
| Camera 4      | 3         |
+---------------+-----------+
| Camera 5      | 4         |
+---------------+-----------+
| Camera 6      | 5         |
+---------------+-----------+
| Camera 7      | 6         |
+---------------+-----------+
| Camera 8      | 7         |
+---------------+-----------+

i. Open a terminal and type command to open ``camera 1's video`` streaming.

.. code:: bash

    gst-launch-1.0 nvarguscamerasrc sensor-id=0 ! 'video/x-raw(memory:NVMM), width=2048, height=1280, framerate=30/1' ! nvvidconv flip-method=0 ! 'video/x-raw, format=(string)I420' ! xvimagesink -e

ii. Open **another** terminal and type command to ``open camera 2's video`` streaming.

.. code:: bash

    gst-launch-1.0 nvarguscamerasrc sensor-id=1 ! 'video/x-raw(memory:NVMM), width=2048, height=1280, framerate=30/1' ! nvvidconv flip-method=0 ! 'video/x-raw, format=(string)I420' ! xvimagesink -e

.. image:: images/gst-test.png
  :width: 80%
  :align: center

If successful, you will see two windows from different cameras, like below.

.. image:: images/gst-preview.png
  :width: 80%
  :align: center

.. warning::

    If you find that Argus plugin can't operate well, you can restart nvargus-daemon.
    ``sudo systemctl restart nvargus-daemon.service``

V4L2
----

To use V4L2, you can read video device under ``/dev/`` directly.
The camera will be listed like ``/dev/videoX``, while X is from 0-7.
You can also read the camera under ``/dev/gmsl/*``.
Both two ways are available.

To read camera 1 by gstreamer:

.. code:: bash

    gst-launch-1.0 v4l2src device=/dev/video0 ! videoconvert ! videoscale ! video/x-raw,format=UYVY ! queue ! videoconvert ! ximagesink sync=no

To read camera 1 by v4l2 tools

.. code:: bash

    v4l2-ctl -d /dev/video0 --set-fmt-video=width=1920,height=1080,pixelformat=UYVY --stream-mmap=3 --stream-count=600
