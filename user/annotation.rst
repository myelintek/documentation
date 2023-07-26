##########
Annotation
##########

Annotation provides mainstreaming annotation tools and well integrated to MLSteam.

Setup Label Studio
==================

`Label Studio <https://labelstud.io/>`_ is a data annotation tool,
available in MLSteam. To setup Label Studio:

#) :ref:`Create a project-scoped folder <create-and-manage-project-scoped-folder>`,
   ``yolo-sample`` as example here, and add an ``output`` directory in the folder.

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_1.png
        :width: 600

#) In Annotation page, create a new annotation
    .. image:: /_static/imgs/user/annotation/create_annotation.png
        :width: 600 

#) Create a Label Studio environment

    * Annotation environment: select ``Label Studio``
    * Folders: ``yolo-sample``

    .. image:: /_static/imgs/user/annotation/add_label_studio.png
        :width: 600

#) Launch the Label Studio annotation.

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
        :width: 600

#) In the *Cloud Storage* section, click on the *Add Source Storage* button.

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_8.png
        :width: 600

#) In the dialog, fill in the following fields, and click on the *Add Storage* button.

    * Storage type: ``Local files``
    * Storage title: a storage title (optional)
    * Absolute path: path to the images to label
      (for the *yolo-sample* dataset, this would be ``/data/ds1/training_data/yolo/images``)
    * File filter regex: image file filter in regular expressions (optional)
      (for the *yolo-sample* dataset, this would be ``.*jpg``)
    * Treat every bucket object as a source file: ``enabled``

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_9.png
        :width: 480

#) Back to the project settings page, click on the *Sync Storage* button.

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_10.png
        :width: 600

#) Back to the project main page by clicking on the top navbar.

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_11.png
        :width: 480

#) Select an image to label, add the bounding boxes for the corresponding classes,
   and click on the *Submit* button.

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_12.png
        :width: 600

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_13.png
        :width: 600

#) Repeat the previous step until all the images are labelled.
#) Back to the project settings page, click on the *Add Target Storage* button.

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_14.png
        :width: 600

#) In the dialog, fill in the following fields, and click on the *Add Storage* button.

    * Storage type: ``Local files``
    * Storage title: a storage title (optional)
    * Absolute local path: the output path created in the mounted project-scoped folder
      (For example, ``/data/output``)

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_15.png
        :width: 480

#) Back to the project settings page, click on the *Sync Storage* button.

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_16.png
        :width: 600

#) Back to the folder page, the labelling data will be saved in the output directory.

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_17.png
        :width: 600

