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
