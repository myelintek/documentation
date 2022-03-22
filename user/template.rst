########
Template
########

A template is a creator of a
:doc:`lab <lab>`, :doc:`pipeline action <pipeline>`, or :doc:`WebApp <webapp>`
with predefined programs, datasets, models, or other settings.

Built-in Templates
==================

MLSteam has built-in templates for common ML tasks, such as:

* Image classification
* Object detection
* Face mask detection
* Speech recognition

.. image:: /_static/imgs/user/template/view_templates.png
    :width: 600

A template may have tags denoting its attributes.

* ``type:lab``: a lab template
* ``type:action``: a pipeline action template
* ``type:webapp``: a WebApp template


Create a Template
=================

A template could be created from an exported template file or from a raw Docker image.

To create a template from a template file:

#) Save the source template file in a project-scoped dataset.
#) In the template page, click on the *NEW* button.

    .. image:: /_static/imgs/common/btn_new.png

#) Click on the *From file* menu item.
#) In the template creation dialog, select the dataset and the source template file.
#) Click on the *IMPORT* button.

    .. image:: /_static/imgs/user/template/new_template_from_file_1.png
        :width: 480

#) After the template creation finishes,
   reload the template page and the new template will be displayed.

.. note:: 
    An MLSteam template file encapsulates a Docker image and the relevant template settings.

To create a template from a Docker image:

#) :ref:`Upload the Docker image <upload-image>` to MLSteam if it has not existed.
#) In the template page, click on the *NEW* button.

    .. image:: /_static/imgs/common/btn_new.png

#) Click on the *From image* menu item.
#) Under the *Template information* section, select the image and fill in the following fields:

    * Template name
    * Template version
    * Template description
    * Template tags (separated by commas, semicolons, or pipes)

#) Under the *Template type* section,
   choose one of the template type and fill in the corresponding fields:

    #) Lab

        * IDE Interface: could be ``terminal``, ``jupyter``, or both
        * Dataset mounts
        * Resource requirements: minimum resource requirements for CPU cores, memory size, and GPU cards

    #) WebApp

        * Command to launch the app
        * Bind port
        * Bind protocol
        * Dataset mounts
        * Parameters
        * Resource requirements: minimum resource requirements for CPU cores, memory size, and GPU cards

    #) Pipeline action

        * Command to run the pipeline
        * Command visibility: whether the command is ``readonly``, ``editable``, or ``hidden``
          in the pipeline action dialog
        * Dataset mounts
        * Parameters
        * Resource requirements: minimum resource requirements for CPU cores, memory size, and GPU cards

    .. note:: 
        Resource requirements are referential.
        They do not stop users from creating a lab with a flavor not satisfying the resource requirements;
        only a warning message is displayed.

Delete a Template
=================

To delete a template:

#) Go to template page, and click on the *delete* button at the selected version.

    .. image:: /_static/imgs/user/template/del_template_1.png
        :width: 480

#) Click on the *OK* button.

.. note:: 
    A built-in template could not be deleted in the template page.

Export a Template
=================

A template could be exported and imported between MLSteam systems.
To export a template:

#) :ref:`Create a project-scoped dataset <create-and-manage-project-scoped-dataset>`
   which serves as the export destination if it has not existed.
#) Go to template page, and click on the *EXPORT* button at the selected version.

    .. image:: /_static/imgs/user/template/export_template_1.png
        :width: 600

#) Select the distination dataset and the path within the dataset to save the exported template file.
#) Click on the *EXPORT* button.

    .. image:: /_static/imgs/user/template/export_template_2.png
        :width: 480

.. _upload-image:

Upload an Image
===============

This section describes several ways to upload a Docker image for creating a template.

.. _upload-image-from-registry:

To upload an image from a Docker image registry:

#) In the *Image* tab, click on the *NEW* button.
#) Click on the *Pull* menu item.
#) Fill in the registry link and the image name in the dialog.
#) Click on the *PULL* button.

To upload a local Docker container or image through registry:

#) Export the local Docker container or image with the ``docker export`` or ``docker save`` commands.
   The exported image file will be in the *tar* format.
#) Push the exported image file to a Docker image registry accessible by MLSteam.

    .. note:: 
        If your MLSteam installation has a Docker image registry,
        you may push the exported image by running the commands provided by MLSteam.
        To get the commands, click on the *NEW* button and click on the *Push* menu item.

#) Follow the :ref:`steps <upload-image-from-registry>` to upload an image from a Docker image registry.

.. _upload-image-from-file:

To upload an image from a Docker image file:

#) Save the source Docker image file in a project-scoped dataset.
#) In the *Image* tab, click on the *NEW* button.
#) Click on the *From File* menu item.
#) Fill in the image name and select the source image file from the dataset.
#) Click on the *IMPORT* button.

To upload a local Docker container or image without registry:

#) Export the local Docker container or image with the ``docker export`` or ``docker save`` commands.
   The exported image file will be in the *tar* format.
#) Upload the exported image file to a project-scoped dataset.
#) Follow the :ref:`steps <upload-image-from-file>` to upload an image from dataset.
