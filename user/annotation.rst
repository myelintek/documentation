##########
Annotation
##########

Annotation provides mainstreaming annotation tools and well integrated to MLSteam.

Setup Label Studio
==================

`Label Studio <https://labelstud.io/>`_ is a data annotation tool,
available in MLSteam. To setup Label Studio:

#) :ref:`Create a project-scoped folder <create-and-manage-project-scoped-folder>` as image source.
   
    We use ``yolo-sample`` as an example here.

#) In Annotation page, click on the *new* button

#) Create a Label Studio environment

    * Annotation environment: select ``Label Studio``
    * Folders: ``yolo-sample``

    .. image:: /_static/imgs/user/annotation/create_annotation.png
        :width: 700

#) Enter Label Studio.

    .. image:: /_static/imgs/user/annotation/launch_label_studio.png
        :width: 480

#) Click on the *Create Project* button.
#) In the dialog, fill in the following fields, and click on the *Save* button:

    * Project name tab:

        * Project name: the project name
        * Description: a brief description (optional)

        .. image:: /_static/imgs/user/webapp/setup_labelstudio_4.png
            :width: 480

    * Labeling setup tab:

        * Select *Object Detection with Bounding Boxes*.
        * Define the labels.

        .. image:: /_static/imgs/user/webapp/setup_labelstudio_5.png
            :width: 480

        .. image:: /_static/imgs/user/webapp/setup_labelstudio_6.png
            :width: 480

#) In the project page, click on the *Settings* button.

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_7.png
        :width: 700

#) In the *Cloud Storage* section, click on the *Add Source Storage* button.

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_8.png
        :width: 700

#) In the dialog, fill in the following fields, and click on the *Add Storage* button.

    * Storage type: ``Local files``
    * Storage title: a storage title (optional)
    * Absolute path: path to the images to label
      (for the *yolo-sample* dataset, this would be ``/data/yolo-sample/training_data/yolo/images``)
    * File filter regex: image file filter in regular expressions (optional)
      (for the *yolo-sample* dataset, this would be ``.*jpg``)
    * Treat every bucket object as a source file: ``enabled``

    .. image:: /_static/imgs/user/annotation/setup_labelstudio_9.png
        :width: 480

    .. note::
        #) The root of storage path could be copied from the folder sidebar.

            .. image:: /_static/imgs/user/annotation/setup_labelstudio_9b.png
                :width: 700

        #) You may click on the *Check Connection* button to test the existence of storage path.

#) Back to the project settings page, click on the *Sync Storage* button.

    .. image:: /_static/imgs/user/annotation/setup_labelstudio_10.png
        :width: 700

#) Back to the project main page by clicking on the top navbar.

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_11.png
        :width: 480

#) Select an image to label, add the bounding boxes for the corresponding classes,
   and click on the *Submit* button.

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_12.png
        :width: 700

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_13.png
        :width: 700

#) Repeat the previous step until all the images are labelled.

Export Label Studio Annotations to an Attached Folder
=====================================================

#) Make sure the destination MLSteam folder has been attached to Label Studio
   and has an output directory (E.g., ``output``).

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_1.png
        :width: 480

#) Go to the project settings page, click on the *Add Target Storage* button.

    .. image:: /_static/imgs/user/annotation/setup_labelstudio_14.png
        :width: 700

#) In the dialog, fill in the following fields, and click on the *Add Storage* button.

    * Storage type: ``Local files``
    * Storage title: a storage title (optional)
    * Absolute local path: the output path created in the mounted project-scoped folder
      (For example, ``/data/yolo-sample/output``)

    .. image:: /_static/imgs/user/annotation/setup_labelstudio_15.png
        :width: 480

#) Back to the project settings page, click on the *Sync Storage* button.

    .. image:: /_static/imgs/user/annotation/setup_labelstudio_16.png
        :width: 700

#) Back to the folder page, the labelling data will be saved in the output directory.

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_17.png
        :width: 700

Export Label Studio Annotations to any Project Folder
=====================================================

#) Make sure the destination MLSteam folder has been created in the project and has an output directory.
#) Click on the *Export Annotation* item in the top menu.

    .. image:: /_static/imgs/user/annotation/export_labelstudio_annotation_1.png
        :width: 700

#) In the dialog, fill in the following fields, and then click on the *Select* button.

    * Source: the Label Studio view to export.

        .. note::
            Label Studio uses views (a tab within a project) to filter the annotation tasks.
            In this example, the project name is ``New Project #1`` and the tab name is ``Default``.

    * Format: the export format.

    .. image:: /_static/imgs/user/annotation/export_labelstudio_annotation_2.png
        :width: 700

#) Select the output folder and directory, and then click on the *OK* button.

    .. image:: /_static/imgs/user/annotation/export_labelstudio_annotation_3.png
        :width: 480

#) Click on the *Export* button to start annotation export.

    .. image:: /_static/imgs/user/annotation/export_labelstudio_annotation_4.png
        :width: 480

#) Wait for a while, and the exported file will be saved in the output folder.

    .. image:: /_static/imgs/user/annotation/export_labelstudio_annotation_5.png
        :width: 700


Setup CVAT
==========

`CVAT <https://cvat.org/>`_ is a data annotation tool,
available in MLSteam. To setup CVAT:

#) :ref:`Create a project-scoped folder <create-and-manage-project-scoped-folder>` as image source.
   
    We use ``yolo-sample`` as an example here.

#) In Annotation page, click on the *new* button

#) Create a CVAT environment.

    * Annotation environment: select ``CVAT``
    * Folders: ``yolo-sample``

    .. image:: /_static/imgs/user/annotation/add_cvat.png
        :width: 480

#) Enter CVAT.
#) Click on the *Create new task* button.
#) Fill the task creation form fields.

    * To create annotation tasks from an attached project folder, click on *Connected file share*,
      expand directory tree, and sellect the needed files.

    .. image:: /_static/imgs/user/webapp/setup_cvat_4.png
        :width: 700

    .. warning::
        Don't include ``.cvat`` directory. It will result in error.

#) Open the task after submit.

    .. image:: /_static/imgs/user/webapp/setup_cvat_5.png
        :width: 700

#) Open the job.

    .. image:: /_static/imgs/user/webapp/setup_cvat_6.png
        :width: 700

#) Do the labeling (labeling process is not covered here).

Export CVAT Annotations to any Project Folder
=============================================

#) Make sure the destination MLSteam folder has been created in the project and has an output directory.
#) Click on the *Export Annotation* item in the top menu.

    .. image:: /_static/imgs/user/annotation/export_cvat_annotation_1.png
        :width: 700

#) In the dialog, fill in the following fields, and then click on the *Select* button.

    * Source: the CVAT task to export.
    * Format: the export format.

    .. image:: /_static/imgs/user/annotation/export_cvat_annotation_2.png
        :width: 700

#) Select the output folder and directory, and then click on the *OK* button.

    .. image:: /_static/imgs/user/annotation/export_cvat_annotation_3.png
        :width: 480

#) Click on the *Export* button to start annotation export.

    .. image:: /_static/imgs/user/annotation/export_cvat_annotation_4.png
        :width: 480

#) Wait for a while, and the exported file will be saved in the output folder.

    .. image:: /_static/imgs/user/annotation/export_cvat_annotation_5.png
        :width: 700
