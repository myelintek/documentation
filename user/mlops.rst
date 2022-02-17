##################
Quick Start: MLOps
##################

This tutorial will show you how to:

* Start a machine learning pipeline for `YOLOv5 <https://github.com/ultralytics/yolov5>`_ object detection.

Preparation
===========

Make sure there is a project for you to run a pipeline. Refer to :doc:`quick_start` for more details on preparation.

Create a YOLOv5 Pipeline
========================

We will start a pipeline to train and run a YOLOv5 model.

#) Go to the project page by clicking on the project card.

    .. image:: /_static/imgs/user/get_started/goto_project.png
        :width: 600

#) Click on the *Pipeline*  item in the left menu.

    .. image:: /_static/imgs/user/get_started/goto_pipeline.png
        :width: 600

#) Click on the *NEW* button.

    .. image:: /_static/imgs/user/get_started/btn_new.png

#) In the new project dialog, input the following fields:

    * Name: `my-yolov5`

#) Click on the *CREATE* button.

    .. image:: /_static/imgs/user/get_started/add_pipeline_1.png
        :width: 600

#) The newly created pipeline is now displayed with status *Not Run Yet*.

    .. image:: /_static/imgs/user/get_started/add_pipeline_2.png
        :width: 600

Define the Pipeline Process
===========================

#) Click on the *Add Action* button.

    .. image:: /_static/imgs/user/get_started/btn_add_action.png
        
#) In the new action dialog, click on the *Git Pull* action.

    .. image:: /_static/imgs/user/get_started/add_pipeline_action_1.png
        :width: 600

#) In the action settings dialog, input the following field in the *Git* tab:

    * Git URL: `<https://github.com/myelintek/yolov5.git>`_

    .. image:: /_static/imgs/user/get_started/add_pipeline_action_2.png
        :width: 300

#) Input the following field in the *Settings* tab:

    * Name (action name): `get latest code`

#) Click on the *CREATE* button.

    .. image:: /_static/imgs/user/get_started/add_pipeline_action_3.png
        :width: 300