##########
Management
##########

Task
====

The task tab lists the tasks in the system.

* Name: task name
* UUID: tasks identifier
* Project ID: project identifier
* Status: task running status, could be *Done* (stopped and not occupying resources) or *Running*
* Owner: task owner
* Type: task type, could be *LAB*, *Webapp* and others
* Specification: flavor for the task
* Create time: task creation time
* Host: host where the task runs

.. image:: /_static/imgs/administration/management/view_tasks.png
    :width: 700

Task management operations:

#) Start
#) Stop
#) Kill
#) Delete

.. note::
    A task could only be deleted when it is *stopped* (in the *Done* status)

.. _management-flavor:

Flavor
======

The flavor tab lists the flavors in the system.

* Name: flavor name
* Tag: tags to select hosts
* Summary: flavor settings summary
* CPU: CPU cores to allocate
* Memory: memory to allocate in MB
* GPU: GPU cards to allocate. ``0`` means no GPUs will be allocated.
* GPU type: GPU type used. *Any* means no restrictions to GPU types.

.. image:: /_static/imgs/administration/management/view_flavors.png
    :width: 700

Flavor management operations:

#) Create: add a new flavor
#) Edit: modify an existing flavor
#) Delete: remove a flavor
#) Up/Down: change the order of showing available flavors in a dropdown list

Dataset
=======

The dataset tab lists the datasets in the system.

* Name: project name.
  A public built-in dataset is displayed by the dataset's name.
  A private project-scoped dataset is displayed by the project's identifier followed by the dataset's name.
* UUID: project identifier
* Project: owner project, empty for built-in datasets
* Permission: dataset access permission
* Owner: dataset creator
* Size: dataset size in MB
* Create time: dataset creation time

.. image:: /_static/imgs/administration/management/view_datasets.png
    :width: 700

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
    :width: 700

Project management operations:

#) Delete

.. note::
    A project could be created or edited only through the normal user interface.

Export a Project
----------------

Select a project and click on the *Export* button. Select backup items and click *Export*.
The export project task will be running in the background. Please wait for complete.

.. image:: /_static/imgs/administration/management/project_export.png
    :width: 700

The project will be exported to the backup folder of MLSteam. Administrators can
login to server via ssh and find the exported project directory, the directory name
will be the project uuid plus exported date time.

.. image:: /_static/imgs/administration/management/project_export_2.png
    :width: 700


Import a Project
----------------

Import a project by clicking the *Import* button in project page. Select the target project
and click *Import*. Once the import complete, the imported project will show up on the project list.

.. image:: /_static/imgs/administration/management/project_import_1.png
    :width: 700
.. image:: /_static/imgs/administration/management/project_import_2.png
    :width: 700

Template
========

The template tab lists the templates in the system.

* Name: template name
* Description: template description
* Author: template author. *MLSteam* means a built-in template.
* Version: template version
* Tag: template tags
* Create time: template creation time

.. image:: /_static/imgs/administration/management/view_templates.png
    :width: 700

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
* Create time: image creation time

.. image:: /_static/imgs/administration/management/view_images.png
    :width: 700

Image management operations:

#) Delete

.. note::
    All Docker images, including those not used in MLSteam, are listed here.

Setting
=======

The setting page lists the global system settings.

* open_files: maximum number of opened files for a container
* pids_limit: maximum number of processes for a container
* shm_size: shared memory size in GB for a container
* storage_limit: storage size in GB for a container

.. image:: /_static/imgs/administration/management/view_settings.png
    :width: 700

The setting management operations:

#) Edit: by clicking on the value

    .. image:: /_static/imgs/administration/management/edit_setting_1.png
        :width: 700
