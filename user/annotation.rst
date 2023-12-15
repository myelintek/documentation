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


Automatic Annotation
====================

Instead of using Nuclio serverless framework for automatic labeling, MLSteam provides integrated solution to replace Nuclio.
First, launching an *inferencing API server* as a Webapp service. The **inference API Webapp** must include the following REST API.

Inference API Webapp
+++++++++++++++++++++

.. http:get:: /status

    Inference service status and message

    **Example request**:

    .. sourcecode:: bash

            $ curl http://<webapp ip>:<webapp port>/status

    **Example response**:

    .. sourcecode:: json

            {"state":"ready","msg":""}

    .. note::

        :Response JSON Object:

         * **state** (*string*) -- required, should be one of ``starting``, ``ready``, or ``error``.
         * **msg** (*string*) -- optional, service status message.

.. http:get:: /cvat_info

    Inference label and other specification

    **Example request**:

    .. sourcecode:: bash

            $ curl http://<webapp ip>:<webapp port>/cvat_info

    **Example response**:

    - For **single endpoint**, it is a dict

    .. sourcecode:: json

            {
                "name": "Lpr detector Malaysia",
                "description": "detect Plate/Car/Motobike",
                "type": "detector",
                "spec": [
                    {
                        "id": 0,
                        "name": "Plate",
                        "attributes": [
                            {
                            "name": "Number",
                            "input_type": "text"
                            }
                        ]
                    },
                    {
                        "id": 1,
                        "name": "Car"
                    },
                    {
                        "id": 2,
                        "name": "Motobike"
                    }
                ]
            }

    .. note::

        :Response JSON Object:

         * **name** (*required*) -- a unique endpoint name in this service.
         * **description** (*required*) -- a brief endpoint description.
         * **type** (*required*) -- should be one of ``detector``, ``interactor``, ``reid``, or ``tracker``.
         * **prefix** (*optional*) -- API url prefix for invoking this endpoint, ommitable for single endpoint. Prefix is required for multiple endpoints to distinguish between the endpoints.
         * **spec** (*optional*) -- Needed for the ``detector`` endpoint types. A list of labels, each label is a dict:

            - id (*required*): a unique integer starting from 0
            - name (*required*): label name
            - attributes (*optional*): a list of attributes. Each attribute is a dict. For example:

            .. sourcecode:: bash

                [
                    {"name": "plate_number", "input_type": "text"},
                    {"name": "age", "input_type": "number", "values": ["0", "150", "1"]},
                    {"name": "gender", "input_type": "select", "values": ["female", "male"]}
                ]

            .. note::

                CVAT only recognizes the attributes that exactly match the defined ones in tasks.

    - For **multiple endpoints**, it is a list of the above dict for each endpoint

    .. note::

        API url prefix for invoking this endpoint. Prefix is required for multiple endpoints to distinguish between the endpoints.


.. http:post:: /invoke

    Inference endpoint

.. http:post:: /invoke/<prefix>

    Inference endpoint with *prefix*

    **Example request**:

        For *detector* type request

    .. sourcecode:: bash

            $ (echo -n '{"image": "'; base64 ~/image.jpg; echo '"}') | curl -H "Content-Type: application/json" -d @- http://<ip>:<port>/invoke

    .. note::

        :Request JSON Object:

        * **image** (*required*) -- base64-encoded image

    **Example response**:

    .. sourcecode:: json

        [
            {
                "label": "Car",
                "points": [
                    15,
                    0,
                    354,
                    282
                ],
                "type": "rectangle"
            },
            {
                "label": "Plate",
                "points": [
                    38,
                    210,
                    152,
                    59
                ],
                "type": "rectangle",
                "attributes": [
                    {"name": "plate_number", "value": "ABC-1234"}
                ]
            }
        ]

    .. note::

        For more response format, please refer to `CVAT SDK example <https://opencv.github.io/cvat/docs/api_sdk/sdk/auto-annotation/>`_


CVAT Autolabel Setup
+++++++++++++++++++++

Once you started an **Inference API Webapp**, go Annotation page and click *autolabel* button

    .. image:: /_static/imgs/user/annotation/autolabel_1.png
        :width: 700

Select the **Inference API Webapp** and apply.

    .. image:: /_static/imgs/user/annotation/autolabel_2.png
        :width: 700

Click CVAT -> Models menu, you will see the *Inference API Webapp* is registered as a *Model*

    .. image:: /_static/imgs/user/annotation/autolabel_3.png
        :width: 700

In CVAT -> Tasks page, click **Automatoic annotation** from one of label tasks

    .. image:: /_static/imgs/user/annotation/autolabel_4.png
        :width: 700

Select model and choose label mappings between the **Task** labels and **Inference API Webapp** labels

    .. image:: /_static/imgs/user/annotation/autolabel_5.png
        :width: 700

Start the annotation and you will see the progress bar in your task

    .. image:: /_static/imgs/user/annotation/autolabel_6.png
        :width: 700
