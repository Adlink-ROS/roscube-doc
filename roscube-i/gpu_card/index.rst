.. _gpu_card:

GPU Card
########

Supported Model: ROScube-I-E

In this chapter, we show you:

    * **How to Install NVDIA Driver** 
    * **GPU Performance Evaluation**

**GPU Table:**

These GPU cards which be used on **ROScube-I-E**.

**1. ADLINK:**

    * Quadro PEG T1000 
    * Quadro-E PEG P1000

.. note:: 

    For RQI series, we need to use ATX SKU.

.. note:: 
    
    | PN are as follows:
    | T1000: 92-97199-0010 (ATX bracket).
    | P1000: 91-95259-0010 (ATX bracket). Will EOL pretty soon.

**2. Others:**

    * NVIDIA RTX A2000  12G
    * NVIDIA GTX 1050   2G

.. warning:: 
    
    In others, we've not tested these GPU cards under critical thermal & vibration condition.

**Table of Contents:**

.. toctree::
   :maxdepth: 1

   nvidia_driver.rst
   common/gpu_performance/index.rst