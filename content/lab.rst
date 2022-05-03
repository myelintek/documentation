####
Lab
####

A lab is a web IDE (based on JupyterLab). Here we listed all available operations in each section.

* :ref:`create_lab`
* :ref:`browse_lab`
* :ref:`stop_lab`
* :ref:`start_lab`
* :ref:`attach_dataset_lab`
* :ref:`delete_lab`


.. _create_lab:

Create lab
==========

To create a lab, navigate to your project dashboard and click the *Check* button on the *Lab* panel.

.. figure:: ../_static/lab/list_lab.jpg

  click the *Check* button on the *Lab* panel

.. figure:: ../_static/lab/create_lab.jpg

  click the *Create New* button

Write a name for your lab, choose a flavor you want, and select a docker image to create a lab. Choose from 2 images based on *myelintek/python-gpu*, which have all common libraries for deep learning built-in, but use different versions of tensorflow. You can also choose the type of lab to run, it will either use Jupyterlab or a simple terminal.  
Finalize your choice by clicking *Create* button and your lab should be ready in a moment!

.. figure:: ../_static/lab/create_lab_modal.jpg

  create a lab with small flavor and python-gpu:tf-1.15.0-v14 (tensorflow v1) image


.. caution::

  GPU number is exclusive for each lab. Be cautious that system may run out of GPU resources and labs won't be launched unless GPU resources are released.

.. tip::

  Set flavor to micro (gpu 0), which will make your lab run with CPU only.

.. _browse_lab:
 
Browse labs
===========

To browse labs of a specific project, navigate to the *Home* dashboard first and choose the project you want. 

.. figure:: ../_static/lab/browse_project.jpg

  click *View* button to enter that project dashboard

This project will become *default* and can be accessed quickly from the *Project* tab. To look at all the labs created in the current project, click the *Check* button. 

.. figure:: ../_static/lab/list_lab.jpg

  click the *Check* button on the *Lab* panel

Labs are listed together with information like name, UUID, status indicator, number of GPUs used, and also time of creation. You can get more details by clicking the *+* sign.

.. figure:: ../_static/lab/detail_lab.jpg

  Check the detail of the lab.

To open the lab to modify it or run experiments click *Jupyter*, this will open another window, where you need to start your lab.

.. figure:: ../_static/lab/view_lab.jpg

  click *Jupyter* button to open the lab

.. _start_lab:

Start lab
=========

To start a lab, click *Start* indicator

.. image:: ../_static/lab/start_lab_in.jpg

or click *Start* at the lab list page.

.. image:: ../_static/lab/start_lab_out.jpg

.. _stop_lab:

Stop lab
========

To stop a lab, click the *Stop* button

.. image:: ../_static/lab/stop_lab_in.jpg

or click *Stop* at the lab list page.

.. image:: ../_static/lab/stop_lab_out.jpg


.. _attach_dataset_lab:

Attach dataset to the lab
=========================

To attach a dataset, select the desired dataset in dataset section and click *attach dataset*.

.. figure:: ../_static/lab/attach_dataset.png
  :width: 400

  attach *mnist* dataset for this lab.

.. note::

    Attaching dataset will automatically restart the lab, make sure all the files have already been saved.


.. figure:: ../_static/lab/attach_dataset_alert.jpg
  :width: 500

  confirm to restart the lab


Attached dataset info will appear on the dataset section.

.. image:: ../_static/lab/attach_dataset_done.jpg
  :width: 400

Dataset files can be browsed in the window on the left under `/input` directory.

.. tip::

    You can choose to mount your dataset in a subdirectory inside /input/ by writing appropriate name in the *Mount* form

.. figure:: ../_static/lab/attach_dataset_file.jpg
  :width: 300

  browse dataset files in /mlsteam/input folder

Add new directory to dataset, if needed.

.. image:: ../_static/lab/attach_dataset_folder.jpg
  :width: 300

Upload new files to dataset, if needed.

.. image:: ../_static/lab/attach_dataset_upload.jpg
  :width: 300

Upload a zip file to lab.

.. image:: ../_static/lab/zipfile.png

Launch the terminal and unzip the file.

.. code-block:: batch

  unzip <file_name.zip>

.. image:: ../_static/lab/unzipfile.png


Generate ssh key (if enabled)
=============================

This feature is disabled by default. Generates ssh key to be able to ssh into lab. Click on ssh tab, inside tab click "Generate", save sshkey file to your local PC.
More about connecting to the lab in "Remote connection to the lab" section.

.. image:: ../_static/lab/create_ssh_key.png

Expose port with proxy
======================

Expose port from inside of the lab to the outer world. Click on "Proxy" tab, enter port you want to expose, press "Expose".

.. image:: ../_static/lab/expose_port.png

Use the shown link to access specified port.

.. image:: ../_static/lab/expose_port_proxy.png

To stop expossing port and delete the proxy press "Delete".

.. image:: ../_static/lab/expose_port_delete.png


.. _delete_lab:

Delete lab
==========
On the project page click "Lab" button.
Stop needed lab.
On the list of labs page click on the trash icon on the side of the lab name.

.. image:: ../_static/lab/delete_lab.jpg
