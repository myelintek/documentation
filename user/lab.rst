##########
Lab
##########

A lab is a Web IDE (based on `JupyterLab <https://jupyter.org/>`_ with MLSteam's add-on functionalities) that organizes files and datasets.
You may design ML models and make experiments in a lab.
When the development is done, you may convert a lab into a :doc:`template <template>` for reuse in other labs, pipelines or deployment.

Create a Lab
============

A lab is created from a pre-defined template.

#) In the lab page, click on the *NEW* button.

    .. image:: /_static/imgs/user/get_started/btn_new.png

    .. note::
        A :doc:`project <project>` should be created first before we could create or use a lab.

#) Select a template.

    .. image:: /_static/imgs/user/get_started/add_lab_1.png
        :width: 600

#) Fill in the fields in the dialog, and then click on the *CREATE* button.

    * Name: lab name
    * Flavor: the resources allocated for the lab
    * Dataset mount paths (optional): pre-defined by the template. You may add or delete the mount paths.

    .. caution::
        #) Some labs require one or more GPUs to run. Make sure you select a flavor that meets the lab's requirements.
        #) GPUs are independently allocated for each started lab or pipeline run.
           If a lab could not be started due to a shortage of resources, try to :ref:`stop unused labs <delete-lab>` or to stop pipeline runs.


Run a Lab
=========

Program code in a Jupyter Notebook is organized in cells. 
A Jupyter Notebook file has a name ended with `.ipynb` and could be opened by double clicking on the entry in the file browser on the left.
In Jupyter Notebook, code is run in a process called the Kernel.

To run (evaluate) the program code in a single cell,
click on the menu item: *Run* → *Run Selected Cells* or press the `Shift-Enter` key combination.

.. note::
    Depending on the Kernel execution state, sometimes you may need to run all previous cells before running the current one.
    Click on the menu item: *Run* → *Run All Above Selected Cell*.

To run all the program code from a clean Kernel execution state,
click on the menu item: *Run* → *Restart Kernel and Run All Cells*.

.. image:: /_static/imgs/user/get_started/run_lab_3a.png
    :width: 600

.. note::
    Refer to `JupyterLab Documentation <https://jupyterlab.readthedocs.io/en/stable/index.html>`_ for more usage information.

Attach a Dataset
================

Monitor Resource Consumption in a Lab
=====================================

To monitor the real-time resource consumption, click on the top area. A watch window will be opened.

.. image:: /_static/imgs/user/get_started/run_lab_6.png
    :width: 600

Hardware resources displayed:

* Compute

    * CPU utilization in percentage

* Memory

    * memory utilization in percentage
    * used memory in GB
    * total memory in GB

* Storage

    * disk storage in percentage
    * used storage in GB
    * total storage in GB

* GPU

    * GPU compute utilization in percentage
    * used GPU memory in GB
    * total GPU memory in GB

.. _delete-lab:

Delete a Lab
============

To delete a lab:

#) If the lab is in the *running* state, stop the lab by clicking on the *stop* button.

    .. image:: /_static/imgs/user/lab/stop_lab_1.png
        :width: 480

#) Click on the *delete* button.

    .. image:: /_static/imgs/user/lab/stop_lab_2.png
        :width: 480

SSH into a Lab
==============

TODO: VSCode

Hyperparameter Tuning
=====================

TODO: Submit a training job, Multiple

Save a Lab as a Template
========================

Troubleshooting & FAQs
======================

TODO: Run with web terminal, change flavor, proxy, configuration