###########################################
Tutorial: Yolov7 Training (VC Pipeline)
###########################################

.. _tutorial_yolov7_training:

.. note::
    Please ensure your VCProject plugin was installed

Create VC Project
=================

To create a new VC project:

#) On the projects page, click on the *NEW* button.
#) Click on the *USE* button of the *Connect A Repository*.

    .. image:: /_static/imgs/user/project/add_vc_project_1.png
        :width: 700

#) Use following github repository in *Clone Address*

    .. code-block:: shell

      https://github.com/myelintek/yolov7


    .. image:: /_static/imgs/user/get_started/tutorial_yolov7_1.png
        :width: 700


Create a Training Pipeline
==========================

Click left *Pipeline* menu and click *New* button. Dialog will detect the pipeline yaml file
*mlsteam-yolov7.yaml* in Yolov7 repository. Use the yaml file
and click *Create* button.

    .. warning::
        When creating a VC Pipeline, the *.mlsteam-ci* directory in the Git repository will be scanned for YAML files.

    .. image:: /_static/imgs/user/get_started/tutorial_yolov7_2.png
        :width: 700

Model Training by VC Pipeline
=============================

#) Click the create pipeline, Click *Actions* tab on top menu to show the workflow chart.
#) Click the *Run* button to trigger the pipeline execution.

    .. image:: /_static/imgs/user/get_started/tutorial_yolov7_3.png
        :width: 700

#) Wait for the pipeline finished with Success as shown below

    .. image:: /_static/imgs/user/get_started/tutorial_yolov7_4.png
        :width: 700

Model Create by Track
=====================

#) Click Track Page to see the uploaded track metrics charts
#) Click the Track record to pop-up MLFlow server page for viewing the trained artifacts
 
    .. image:: /_static/imgs/user/get_started/tutorial_yolov7_5.png
        :width: 700


    .. note::
        Please follow the BentoML documents and `sample code <https://github.com/myelintek/yolov7/blob/main/train.py#L45-L73>`_ to generate the *.bento* files

3) Select the Track and Click *Register Model* button on top to create a *Model Version*

    .. image:: /_static/imgs/user/get_started/tutorial_yolov7_6.png
        :width: 700

4) New model will display in the model version list

    .. image:: /_static/imgs/user/get_started/tutorial_yolov7_7.png
        :width: 700

.. _modelbuild_bento:

Model Build (Bento File)
========================

To build a model version into an inferencing endpoint.
#) Click the *Build Model Version* button on top of the target model version

    .. image:: /_static/imgs/user/get_started/tutorial_yolov7_8.png
        :width: 700

#) Click the *background task* icon to switch to the detail building progress
#) Wait until the build process finished

Launch Inference Endpoint
=========================

#) Once the model build task finished, there will be a new Template with same model *Name* and *Version*
#) Select the model template to create a *Webapp*

    .. image:: /_static/imgs/user/get_started/tutorial_yolov7_9.png
        :width: 700

#) The Model Template will run an API swagger interface as shown below

    .. image:: /_static/imgs/user/get_started/tutorial_yolov7_10.png
        :width: 700


