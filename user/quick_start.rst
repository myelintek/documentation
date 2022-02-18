#################################
Quick Start: Machine Learning Lab
#################################

This tutorial will show you how to:

* Start a machine learning lab for classifying `CIFAR-10 <https://www.cs.toronto.edu/~kriz/cifar.html>`_ image data.
* Train the model and monitor the resource consumption.

Preparation
===========

Make sure there is a project for you to run a lab. Otherwise, create a new project:

#) Go to the projects page by clicking on the *Projects* item in the left menu.

    .. image:: /_static/imgs/user/get_started/goto_projects.png
        :width: 600

#) Click on the *NEW* button.

    .. image:: /_static/imgs/user/get_started/btn_new.png

#) In the new project dialog, input the project name as `my-proj`.
#) Click on the *CREATE* button.

    .. image:: /_static/imgs/user/get_started/add_project_2.png
        :width: 600

#) The new project will be displayed.

    .. image:: /_static/imgs/user/get_started/add_project_3.png
        :width: 600

Create a CIFAR-10 Lab
=====================

We will start a lab to train a ML model for the CIFAR-10 dataset. MLSteam has a built-in image classification model for CIFAR-10, which saves lots of efforts. Simply create a lab from template.

#) Go to the project page by clicking on the project card.

    .. image:: /_static/imgs/user/get_started/goto_project.png
        :width: 600

#) Click on the *Lab*  item in the left menu.

    .. image:: /_static/imgs/user/get_started/goto_lab.png
        :width: 600

#) Click on the *NEW* button.

    .. image:: /_static/imgs/user/get_started/btn_new.png

#) Click on the *Pytorch Cifar10* template.

    .. image:: /_static/imgs/user/get_started/add_lab_1.png
        :width: 600

#) In the new lab dialog, input the following fields:

    * name: `my-cifar10`
    * flavor: `small`

#) Click on the *CREATE* button.

    .. image:: /_static/imgs/user/get_started/add_lab_2.png
        :width: 600

#) The newly created lab is now displayed with status *running*.

    .. image:: /_static/imgs/user/get_started/add_lab_3.png
        :width: 600

Train the Model
===============

We will then train the model in the lab.

#) Go to the lab page by clicking on the lab item. The lab interactive environment will be opened.

    .. image:: /_static/imgs/user/get_started/run_lab_1.png
        :width: 600

#) Open the model training notebook by double clicking on the *entry.ipynb* file on the left.

    .. image:: /_static/imgs/user/get_started/run_lab_2.png
        :width: 600

#) Train the model by clicking on the menu item: *Run* → *Restart Kernel and Run All Cells*.

    .. image:: /_static/imgs/user/get_started/run_lab_3a.png
        :width: 600

    Alternatively, click on the toolbar icon.

    .. image:: /_static/imgs/user/get_started/run_lab_3b.png
        :width: 600

#) Click on the *Restart* button.

    .. image:: /_static/imgs/user/get_started/run_lab_4.png
        :width: 300

#) The training program will start running cell by cell.

    .. image:: /_static/imgs/user/get_started/run_lab_5.png
        :width: 600

#) You could also monitor the real-time resource utilization by clicking on the top area. A watch window will be opened.

    .. image:: /_static/imgs/user/get_started/run_lab_6.png
        :width: 600

TODO: submit as a track for visualization