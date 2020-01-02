.. _lab:

***
Lab
***

.. _create_lab:

Create lab
==========

Select project that lab will be created in.
Press "Lab" button.

.. image:: ../_static/create_lab.png

Press "New Lab".

.. image:: ../_static/create_lab2.png

Sellect docker image to create lab in. The default image is "myelintek/python-gpu".
Sellect the number of gpus to assign to lab. Add a comment, if needed.
Press "Submit".

.. image:: ../_static/create_lab3.png

.. image:: ../_static/create_lab4.png

.. _browse_lab:
 
Browse labs
===========

Browse labs of the specific project. Go to project page. Press "Lab" button.

.. image:: ../_static/create_lab.png

Press on lab id or "Browse" button at the Actions collumn.

.. image:: ../_static/browse_labs.png


Stop lab
========

Press on "Running" button, then select "Stop"

.. image:: ../_static/stop_lab.png

or press "Stop" at the Actions column.

.. image:: ../_static/stop_lab2.png

.. _start_lab:

Start lab
=========

Press "Stop" button, then select "Start" 

.. image:: ../_static/start_lab.png

or press "Start" at the Actions column.

.. image:: ../_static/start_lab2.png

Restart lab
===========

Press "Running" button, then select "Restart"

.. image:: ../_static/restart_lab.png

or press "Restart" at the Actions column.

.. image:: ../_static/restart_lab2.png

.. _attach_dataset_lab:

Attach dataset to the lab
=========================

Type dataset name at the "Attach dataset" box.
Press "Attach dataset" button. 

.. note::

    Restart lab for changes to take effect.

.. image:: ../_static/attach_dataset.png

Attached dataset info will appear on the right.

.. image:: ../_static/attach_dataset2.png

Dataset files can be browsed in the window on the left under `/input` directory.

.. image:: ../_static/attach_dataset3.png

Add new directory to dataset, if needed.

.. image:: ../_static/attach_dataset4.png

Upload new files to dataset, if needed.

.. image:: ../_static/attach_dataset5.png

.. _pass parameters:

Pass parameters
===============

Users can update parameters (hypter-parameters) of a model by defining parameters on web page. Parameters supports YAML format definition and also supports multiple values per key value. System will automatically create multiple jobs for all combinations and run created jobs in parallel on different GPUs.

In your model source code. Please import mlsteam function

.. code-block:: console

  from mlsteam import stparams

Replace code as below to enable parameter update from web page. in this example, we define 'train_bs' keyword.

.. code-block:: console

  -      default=128,
  +      default=stparams.get_value('train_bs', 128),

Now you can define keyword value in *Params* input block of a lab. for example, we can change 'train_bs' to 64.

.. code-block:: console

  params:
    train_bs: 64
    

.. _run_lab:

Run lab
=======

First attach dataset to the lab.

Write necessary code and adjust config file `mlsteam.yml`.

.. image:: ../_static/start_lab_config.png

Press "Commit and run".

.. image:: ../_static/run_lab.png

This will create a job from the code that lab contains.

Browse job to see output. In our case, output is the content of folder `/mlsteam/input`.

.. image:: ../_static/run_lab2.png


.. _delete_lab:

Delete lab
==========
On the project page press "Lab" button.
Stop needed lab.
On the list of labs page click on the trash icon on the side of the lab name.

.. image:: ../_static/delete_lab.png
