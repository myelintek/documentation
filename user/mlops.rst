##################
Quick Start: MLOps
##################

This tutorial will show you how to:

* Start a machine learning pipeline for `YOLOv5 <https://github.com/ultralytics/yolov5>`_ object detection.
* Visualize the YOLOv5 model training results to see the performance.

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

    * Name: ``my-yolov5``

#) Click on the *CREATE* button.

    .. image:: /_static/imgs/user/get_started/add_pipeline_1.png
        :width: 600

#) The newly created pipeline is now displayed with status *Not Run Yet*.

    .. image:: /_static/imgs/user/get_started/add_pipeline_2.png
        :width: 600

Define the Pipeline Process
===========================

We will define an MLOps pipeline consisting of two actions: (1) to download the latest YOLOv5 code, and (2) to train the YOLOv5 model.

#) Click on the *Add Action* button.

    .. image:: /_static/imgs/user/get_started/btn_add_action.png
        
#) In the new action dialog, click on the *Git Pull* action.

    .. image:: /_static/imgs/user/get_started/add_pipeline_action_1_1.png
        :width: 600

#) In the action settings dialog, input the following field in the *Git* section:

    * Git URL: `<https://github.com/myelintek/yolov5.git>`_

    .. image:: /_static/imgs/user/get_started/add_pipeline_action_1_2.png
        :width: 480

#) Input the following field in the *Settings* section:

    * Action name: ``get latest code``

#) Click on the *CREATE* button. The code-downloading action is now defined.

    .. image:: /_static/imgs/user/get_started/add_pipeline_action_1_3.png
        :width: 480

#) Define the model-training action. Click on the *New* button, select the *Docker Run* action template, and fill in the following fields:

    * In the *command* section:

        * Command:

            .. code-block:: shell

                apt-get update && apt-get install -y libgl1-mesa-glx
                pip uninstall -y typer
                pip install -qr requirements.txt
                python train.py --img 640 --batch 16 --epochs 10 --data coco128.yaml --weights yolov5s.pt --cache

        .. image:: /_static/imgs/user/get_started/add_pipeline_action_2_1.png
            :width: 480

    * In the *environment* section:

        * Container: ``pytorch:21.06-py3``
        * Flavor: ``small``

        .. image:: /_static/imgs/user/get_started/add_pipeline_action_2_2.png
            :width: 480

        .. note::
            The actual container version number may differ.

    * In the *settings* section:

        * Action name: ``train model``

        .. image:: /_static/imgs/user/get_started/add_pipeline_action_2_3.png
            :width: 480

    * Click on the *CREATE* button.

Now, we have defined all the actions and are ready to run the pipeline.

.. image:: /_static/imgs/user/get_started/add_pipeline_action_3.png
    :width: 600

Run the Pipeline
================

To run the Pipeline:

#) Click on the *RUN PIPELINE* button in the top-right corner.

    .. image:: /_static/imgs/common/btn_run_pipeline.png

#) Write a comment to denote this run or leave it blank.
#) Click on the *RUN NOW* button. The pipeline will start to run in a few seconds.

    .. image:: /_static/imgs/user/get_started/run_pipeline_1_1.png
        :width: 300
    
    .. note::
        A pipeline run may be delayed for a while
        if the system is busy on processing other labs or pipeline runs.

We could see the overall pipeline run information and the status in the pipeline run page.

.. image:: /_static/imgs/user/get_started/run_pipeline_1_2.png
    :width: 600

The immediate outputs of a pipeline action could be observed by clicking on the *LOG* button.

.. image:: /_static/imgs/user/get_started/run_pipeline_1_3.png
    :width: 600

We could also view the outputs in full screen by clicking on the *fullscreen* button.
Press :kbd:`Esc` to exit the full screen mode.

.. image:: /_static/imgs/user/get_started/run_pipeline_1_4.png
    :width: 600

The model validation results could be found in the last part of the outputs, something like::

    Validating /working/train/exp/weights/best.pt...
    Fusing layers... 
    Model Summary: 213 layers, 7225885 parameters, 0 gradients, 16.5 GFLOPs

                Class     Images     Labels          P          R     mAP@.5 mAP@.5:.95:   0%|          | 0/4 [00:00<?, ?it/s]
                Class     Images     Labels          P          R     mAP@.5 mAP@.5:.95:  25%|██▌       | 1/4 [00:00<00:02,  1.30it/s]
                Class     Images     Labels          P          R     mAP@.5 mAP@.5:.95:  50%|█████     | 2/4 [00:02<00:02,  1.10s/it]
                Class     Images     Labels          P          R     mAP@.5 mAP@.5:.95:  75%|███████▌  | 3/4 [00:03<00:01,  1.17s/it]
                Class     Images     Labels          P          R     mAP@.5 mAP@.5:.95: 100%|██████████| 4/4 [00:04<00:00,  1.05s/it]
                Class     Images     Labels          P          R     mAP@.5 mAP@.5:.95: 100%|██████████| 4/4 [00:04<00:00,  1.19s/it]
                  all        128        929      0.741      0.574      0.669       0.46
               person        128        254      0.817      0.669      0.789      0.521
              bicycle        128          6      0.776      0.586      0.627      0.388
                  car        128         46      0.659       0.37      0.481      0.229
           motorcycle        128          5      0.758      0.632       0.88      0.687
             airplane        128          6          1      0.823      0.995      0.789

The overall precision *0.741* seems acceptable for our practice.
We are now ready to run the pipeline again with more training epochs and
to visualize the results.

.. note::
    The actual results you get may slightly differ.

Visualize the ML Results
========================

Increase the training epochs:

#) Back to the run list by clicking on the link in the top-left corner.

    .. image:: /_static/imgs/common/link_back_to_run_list.png

#) Go to the action list by clicking on the *ACTIONS* button.

    .. image:: /_static/imgs/common/btn_actions.png

#) Click on the *train model* action and increase the epoch number from 10 to 20.
   The complete commands:

    .. code-block:: shell

        apt-get update && apt-get install -y libgl1-mesa-glx
        pip uninstall -y typer
        pip install -qr requirements.txt
        python train.py --img 640 --batch 16 --epochs 20 --data coco128.yaml --weights yolov5s.pt --cache

#) Click on the *SAVE* button.

Then, we run the pipeline again. But at this time, we enable *track* to keep and visualize the results.

#) Click on the *RUN PIPELINE* button.
#) Toggle on *Use Track*.
#) Click on the *RUN NOW* button.

    .. image:: /_static/imgs/user/get_started/run_pipeline_2_1.png
        :width: 480

.. note::

    :doc:`Track <track>` is a mechanism to keep track of the results,
    which avoids the trained results being overwritten by succeeding pipeline runs.
    It also enables visualizing the results data.
    More details could be found in the :doc:`track <track>` documentation.

Be patient and wait until the run is finished.

Let's see our training results:

#) Go to the track listing page by clicking on the *Track* item in the left menu.

    .. image:: /_static/imgs/user/get_started/goto_tracks.png
        :width: 600

#) Go to the track details page by clicking on the corresponding track link in the list.

    .. image:: /_static/imgs/user/get_started/goto_track.png
        :width: 600
    
    .. note::
        A track is named by the initial part of the project name, followed by the run number.

#) In the track details page, click the *SWITCH TO TENSORBOARD* button in the top-left corner.
   TensorBoard will show up in a few seconds.

    .. image:: /_static/imgs/common/btn_switch_to_tensorboard.png

Now, we could see various logged data displayed in various figures.

.. image:: /_static/imgs/user/get_started/view_tensorboard.png
    :width: 600

.. note::
    Refer to the `TensorBoard <https://www.tensorflow.org/tensorboard>`_ Website for visualization operations.