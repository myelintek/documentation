##########
Lab
##########

A lab is a Web IDE (based on `JupyterLab <https://jupyter.org/>`_) that organizes files and datasets.
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
           If a lab could not be started due to a shortage of resources, try to stop some labs or pipeline runs.


Run a Lab
=========

To run (evaluate) the program code in a single cell, 

Attach a Dataset
================

Monitor HW in a Lab
===================

Delete a Lab
============

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