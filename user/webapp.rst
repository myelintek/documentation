#########
WebApp
#########

A WebApp enables deployment of a Web-based ML applications in a simple way.
Services for project users may also be provided as a WebApp.

For example, the *YOLOv5 Inference* WebApp detects the objects and their boundaries
in a user-provided image.

.. image:: /_static/imgs/user/webapp/view_web_app_2.png
    :width: 600

Create a WebApp
===============

To create a WebApp:

#) In the WebApp page, click on the *NEW* button.
#) Select the WebApp template.
#) Fill in the settings.

    .. note::

        The settings vary with the selected template.

        For example, the *YOLOv5 Inference* template has settings for
        the WebApp name, flavor, bind port, WebApp protocol, and model.
        *YOLOv5 Inference* requires a model containing a weights file
        named *yolov5.pt* in the model's root directory.

        .. image:: /_static/imgs/user/webapp/add_webapp_1.png
            :width: 480

#) Click on the *CREATE* button.

To access a WebApp:

#) Start the WebApp if it has not been in the *Running* state.
#) Click on the *open* button.

    .. image:: /_static/imgs/user/webapp/view_web_app_1.png
        :width: 480

#) The WebApp will be opened in a new tab or window.

Delete a WebApp
===============

To delete a WebApp:

#) Click on the *stop* button if the WebApp is still in the *Running* state.

    .. image:: /_static/imgs/user/webapp/stop_webapp.png
        :width: 480

#) Click on the *delete* button.

    .. image:: /_static/imgs/user/webapp/del_webapp.png
        :width: 480

Setup Label Studio
==================

`Label Studio <https://labelstud.io/>`_ is a data annotation tool,
available as a WebApp in MLSteam. To setup Label Studio:

#) :ref:`Create a project-scoped dataset <create-and-manage-project-scoped-dataset>`
   and add an output directory in the dataset.

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_1.png
        :width: 600

#) Create a Label Studio WebApp with. TODO: dataset (IMG 2)

    * Flavor: ``micro``
    * Mount dataset: the project-scoped dataset created in the previous step
    * Mount container path: ``/data``

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_2.png
        :width: 480

#) Open the Label Studio WebApp.
#) Create a new account with your email address and a new password.

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_3.png
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
      (for the *yolo-sample* dataset, this would be ``/data/training_data/yolo/images``)
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
    * Absolute local path: the output path created in the mounted project-scoped dataset
      (For example, ``/data/output``)

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_15.png
        :width: 480

#) Back to the project settings page, click on the *Sync Storage* button.

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_16.png
        :width: 600

#) Back to the dataset page, the labelling data will be saved in the output directory.

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_17.png
        :width: 600

Setup CVAT
==========

`CVAT <https://cvat.org/>`_ is a data annotation tool,
available as a WebApp in MLSteam. To setup CVAT:

#) :ref:`Create a project-scoped dataset <create-and-manage-project-scoped-dataset>`

#) Create a CVAT WebApp from template.

    .. image:: /_static/imgs/user/webapp/setup_cvat_1.png
        :width: 600

#) Input name and select desired dataset from the dropdown, then press "Create". Notice default credentials.

    .. image:: /_static/imgs/user/webapp/setup_cvat_2.png
        :width: 600

#) When the webapp is running press "External link" button to open CVAT.

    .. image:: /_static/imgs/user/webapp/setup_cvat_3.png
        :width: 600
    
    .. note::
        While CVAT status is running it might take few minutes for system to fully setup and create accaunt.


#) In the CVAT tab input default credentials ``admin/cvat@mlsteam``
#) Press "Create new task" button
#) Fill the task creation form fields. To use project dataset for annotation click "Connected file share" expand directory tree and sellect needed files.


    .. image:: /_static/imgs/user/webapp/setup_cvat_4.png
        :width: 600

    .. warning::
        Don't include ``.cvat`` directory. It will result in error.

#) Open task 

    .. image:: /_static/imgs/user/webapp/setup_cvat_5.png
        :width: 600

#) Open job

    .. image:: /_static/imgs/user/webapp/setup_cvat_6.png
        :width: 600

#) Do the labeling (labeling process is not covered here)

#) To use annotations, download them first then unzip and upload annotation file to MLSteam dataset. To download unnotations press "Menu"->"Dump annotations" then select desired format.

    .. image:: /_static/imgs/user/webapp/setup_cvat_7.png
        :width: 600