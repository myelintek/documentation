#################################
Quick Start: Machine Learning Lab
#################################

This tutorial will show you how to:

* Start a machine learning lab for `YOLOv5 <https://github.com/ultralytics/yolov5>`_ object detection.
* Train the model and monitor the resource consumption.
* Visualize the model training results.

Preparation
===========

Make sure there is a project for you to run a lab. Otherwise, create a new project:

#) Go to the projects page by clicking on the *Projects* item in the left menu.

    .. image:: /_static/imgs/user/get_started/goto_projects.png
        :width: 600

#) Click on the *NEW* button.

    .. image:: /_static/imgs/common/btn_new.png

#) In the new project dialog, input the project name as ``my-proj``.
#) Click on the *CREATE* button.

    .. image:: /_static/imgs/user/get_started/add_project_2.png
        :width: 600

#) The new project will be displayed.

    .. image:: /_static/imgs/user/get_started/add_project_3.png
        :width: 600

Create a YOLOv5 Lab
=====================

We will start a lab to train a YOLOv5 ML model.
MLSteam has built-in image object detection models for YOLO, which saves lots of efforts.
Simply create a lab from template.

#) Go to the project page by clicking on the project card.

    .. image:: /_static/imgs/user/get_started/goto_project.png
        :width: 600

#) Click on the *Lab*  item in the left menu.

    .. image:: /_static/imgs/user/get_started/goto_lab.png
        :width: 600

#) Click on the *NEW* button.

    .. image:: /_static/imgs/common/btn_new.png

#) Click on the *YOLOv5 Trainer* template.

    .. image:: /_static/imgs/user/get_started/add_lab_1.png
        :width: 600

#) In the new lab dialog, input the following fields:

    * name: ``my-yolov5-lab``
    * flavor: ``small``

#) Click on the *CREATE* button.

    .. image:: /_static/imgs/user/get_started/add_lab_2.png
        :width: 600

#) The newly created lab is now displayed with status *running*.

    .. image:: /_static/imgs/user/get_started/add_lab_3.png
        :width: 600

Before training the model, we need to enlarge the shared memory size to 8 GB for the lab:

#) Go to the lab page by clicking on the *JupyterLab* icon. The lab interactive environment will be opened.

    .. image:: /_static/imgs/user/get_started/run_lab_1.png
        :width: 480

#) Click on the *settings* button.
#) Expand the *Configuration* section in the side bar and set ``8`` in the *Shared Memory* field.

    .. image:: /_static/imgs/user/get_started/set_shm_1.png
        :width: 600

    .. image:: /_static/imgs/user/get_started/set_shm_2.png
        :width: 300

#) The lab will be restarted with the new setting.

Train the Model
===============

We will then train the model in the lab by creating a Python notebook.

#) Create the model training notebook by clicking on the *Python 3 (ipkernel)* launcher under the *Notebook* section.

    .. image:: /_static/imgs/user/get_started/run_lab_2.png
        :width: 600

#) Copy the lines below into the first cell in the notebook.

    .. code-block:: 

        # Setup
        !git clone https://github.com/ultralytics/yolov5  # clone
        %cd yolov5
        %pip install -qr requirements.txt  # install

        import torch
        from yolov5 import utils
        display = utils.notebook_init()  # checks

    .. image:: /_static/imgs/user/get_started/run_lab_3a.png
        :width: 600

#) Click on the *insert* button to insert a second cell.

    .. image:: /_static/imgs/user/get_started/run_lab_3b.png
        :width: 300

#) Copy the lines below into the second cell.

    .. code-block:: 

        # Inference
        !python detect.py --weights yolov5s.pt --img 640 --conf 0.25 --source data/images
        display.Image(filename='runs/detect/exp/zidane.jpg', width=600)

#) Insert the third cell. Copy the lines below into this cell.

    .. code-block:: 

        # Train YOLOv5s on COCO128 for 3 epochs
        !python train.py --img 640 --batch 16 --epochs 3 --data coco128.yaml --weights yolov5s.pt --cache

    The notebook should now look like this:

    .. image:: /_static/imgs/user/get_started/run_lab_3c.png
        :width: 600

#) Train the model by clicking on the menu item: *Run* → *Restart Kernel and Run All Cells*.

    .. image:: /_static/imgs/user/get_started/run_lab_4a.png
        :width: 600

    Alternatively, click on the toolbar icon.

    .. image:: /_static/imgs/user/get_started/run_lab_4b.png
        :width: 300

#) Click on the *Restart* button.

    .. image:: /_static/imgs/user/get_started/run_lab_4c.png
        :width: 300

#) The training program will start running cell by cell.

    .. image:: /_static/imgs/user/get_started/run_lab_5.png
        :width: 600

#) You could also monitor the real-time resource utilization by clicking on the top area. A watch window will be opened.

    .. image:: /_static/imgs/user/get_started/run_lab_6.png
        :width: 600

Visualize the Model Training Results
====================================

After the previous model training experiment,
here we will submit a training job and then view the training results:

#) Click on the *more* button.
#) Click on the *Submit track* menu item.

    .. image:: /_static/imgs/user/get_started/submit_job_1U.png
        :width: 600

#) Click on the *SUBMIT* button.

    .. image:: /_static/imgs/user/get_started/submit_job_2U.png
        :width: 480

#) A new browser window will be opened, listing the :doc:`track <track>` for the submitted job.
#) Go to the track page by clicking on the link of the track.

    .. image:: /_static/imgs/user/get_started/view_job_track_1.png
        :width: 600

#) Wait for one minute while the training results are accumulated.
#) Click on the *SWITCH TO TENSORBOARD* button.

    .. image:: /_static/imgs/user/get_started/view_job_track_2.png
        :width: 600

#) Congratulations! The YOLOv5 model training results are displayed in the TensorBoard page.
   You may adjust the settings to view the results in different ways.

    .. image:: /_static/imgs/user/get_started/view_job_track_3.png
        :width: 600
