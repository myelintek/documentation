##########
Management
##########

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

The dataset tab lists the datasets in the system.

* Name: project name
* UUID: project identifier
* Project: TODO: meaning
* Permission: dataset access permission
* Owner: dataset owner
* Size: TODO: meaning; 0 MB?
* Create time: dataset creation time

.. image:: /_static/imgs/administration/management/view_datasets.png
    :width: 600

Dataset management operations:

#) Delete

.. note::
    A dataset could be created or edited only through the normal user interface.

Project
=======

The project tab lists the projects in the system.

* Name: project name
* UUID: project identifier
* Note: project description
* Owner: project owner
* Create time: project creation time

.. image:: /_static/imgs/administration/management/view_projects.png
    :width: 600

Project management operations:

#) Delete

.. note::
    A project could be created or edited only through the normal user interface.

Template
========

The template tab lists the templates in the system.

* Name: template name
* Description: template description
* Author: template author. `MLSteam` means a built-in template.
* Version: template version
* Tag: template tags
* Create time: template creation time

.. image:: /_static/imgs/administration/management/view_templates.png
    :width: 600

Template management operations:

#) Reload: restore all built-in templates, in case that some templates get deleted or changed accidentally
#) Delete

.. note::
    A template could be created or edited only through the normal user interface.

Image
=====

The image tab lists the Docker images in the system.

* Name: image tagged names
* UUID: image identifier
* Project: project in the image registry
* Layer: image layer numbers
* Size: image size
* Local: TODO: meaning
* Create time: image creation time

.. image:: /_static/imgs/administration/management/view_images.png
    :width: 600

Image management operations:

#) Delete

.. note::
    All Docker images, including those not used in MLSteam, are listed here.

Setting
=======

The setting page lists the global system settings.

* open_files: maximum number of opened files
* pids_limit: maximum number of processes
* shm_size: shared memory size in GB
* storage_limit: storage size in GB

.. image:: /_static/imgs/administration/management/view_setting.png
    :width: 600

TODO: per host settings?
TODO: update image (Unit: g and G)

The setting management operations:

#) Edit: by clicking on the value

    .. image:: /_static/imgs/administration/management/edit_setting_1.png
        :width: 600
