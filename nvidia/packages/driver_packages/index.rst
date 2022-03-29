Driver Packages Usage
#####################

The tutorial will guide you how to customize file system on **Host PC**.

Before customizing file system to ROScube, you should prepare the following items:

    * Host PC with Ubuntu 18.04 or 20.04 operating system.
    * A good quality micro-usb for connecting to ROScube.
    * Driver Package of ROScube


Driver Package is a package contains several assets that runs on host computer, which allows you to do:

    * Customize system file system.
    * Flash system image to target machine.
    * System image back up.
    * Create a custom mfi image.

| User can modify their rootfs on their host computer before flashing the image to target machine.
| You could use tar tool to unarchive driver_package.

.. code-block:: bash
    
    tar xvf <ROScube device>-Driver-Package.tar.gz

.. toctree::
   :maxdepth: 1

   customize_filesystem.rst
   flash_system.rst
   back_up.rst

