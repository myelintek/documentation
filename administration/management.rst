########
Managemt
########

Task
====

The task tab lists the tasks in the system.

* Name: task name
* UUID: tasks identifier
* Project ID: project identifier
* Status: task running status, could be `Done` (stopped and not occupying resources) or `Running`
* Owner: task owner
* Type: task type, could be `LAB` or `JOB`
* Spec: flavor for the task
* Create time: task creation time
* Host: host where the task runs

.. image:: /_static/imgs/administration/management/view_tasks.png
    :width: 600

Task management operations:

#) Start
#) Stop
#) Delete

.. note::
    A task could only be deleted when it is *stopped* (in the `Done` status)

Flavor
======

The flavor tab lists the flavors in the system.

* Name: flavor name
* Summary: flavor settings summary
* CPU: CPU cores to allocate
* Memory: memory to allocate in MB
* GPU: GPU cards to allocate. `0` means no GPUs will be allocated.
* GPU type: GPU type used. `Any` means no restrictions to GPU types.

.. image:: /_static/imgs/administration/management/view_flavors.png
    :width: 600

Flavor management operations:

#) Create
#) Edit
#) Delete

Dataset
=======

Project
=======

Template
========

Setting
=======

Image
=====
