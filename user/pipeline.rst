#########
Pipeline
#########

A pipeline is a repeatable procedure consisting of actions for running ML tasks.
You may define a pipeline for a subset of common ML tasks.
You may even define an end-to-end pipeline to fulfill `MLOps <https://en.wikipedia.org/wiki/MLOps>`_ that
retrains and evaluates the model for new model designs or dataset
and finally deploys the ML application to an experimental or production site.

Create a Pipeline
=================

To create a pipeline:

#) In the project page, click on the *Pipeline*  item in the left menu.

    .. image:: /_static/imgs/user/get_started/goto_pipeline.png
        :width: 600

    .. note::
        A :doc:`project <project>` should be created first before we could create or use a pipeline.

#) Click on the *NEW* button.
#) Input the pipeline name.
#) Click on the *CREATE* button.

    .. image:: /_static/imgs/user/get_started/add_pipeline_1.png
        :width: 600

Manage Pipeline Actions
=======================

A pipeline action is a step in a pipeline procedure.
Available action types:

* *Git pull*: pull source code from git repository
* *Docker run*: run commands in a Docker container
* *Model publish*: publish training artifacts to model

To add a pipeline action:

#) In the actions tab, create the *NEW* button.
#) Select the action type.
#) Fill in the action settings. Main action settings for different action types:

    * *Git pull*: Git URL, username, and password
    * *Docker run*: commands, container image, container flavor, and datasets
    * *Model publish*: model name, model version, and artifacts path

    .. image:: /_static/imgs/user/get_started/add_pipeline_action_2_2.png
        :width: 480

    .. note::
        To use datasets in a pipeline, add the *dataset paths* in a *Docker run* action.

#) Click on the *CREATE* button.

To edit a pipeline action:

#) Click on the action.
#) Edit the action settings.

    .. image:: /_static/imgs/user/pipeline/edit_action_1.png
        :width: 300

#) Click on the *SAVE* button.

To delete a pipeline action:

#) Click on the *delete* button.

    .. image:: /_static/imgs/user/pipeline/del_action_1.png
        :width: 300

#) Click on the *OK* button.

To re-order the pipeline actions:

#) Press on the *re-order* label. Hold the mouse button.
#) Drag the action onward or downward to the new location.

    .. image:: /_static/imgs/user/pipeline/reorder_action_1.png
        :width: 300

#) Release the mouse button.

Run a Pipeline
==============

To run the Pipeline:

#) Click on the *RUN PIPELINE* button in the top-right corner.
#) Write a comment to denote this run or leave it blank.
#) Click on the *RUN NOW* button. The pipeline will start to run in a few seconds.

    .. image:: /_static/imgs/user/get_started/run_pipeline_1_1.png
        :width: 300
    
    .. note::
        A pipeline run may be delayed for a while
        if the system is busy on processing other labs or pipeline runs.

Run Status
----------

The overall pipeline run information and the status are displayed.

.. image:: /_static/imgs/user/get_started/run_pipeline_1_2.png
    :width: 600

.. note::
    Pipeline runs are numbered among all pipelines in the system.
    The pipeline run number may not start from *1*.

The immediate outputs of a pipeline action could be observed by clicking on the *LOG* button.

.. image:: /_static/imgs/user/get_started/run_pipeline_1_3.png
    :width: 600

We could also view the outputs in full screen by clicking on the *fullscreen* button.
Press :kbd:`Esc` to exit the full screen mode.

.. image:: /_static/imgs/user/get_started/run_pipeline_1_4.png
    :width: 600

File Storage
------------

By default, files in pipeline runs are saved in *FILESYSTEM*, a pipeline-specific space in the system.
*FILESYSTEM* always keeps the latest file contents,
and changes to *FILESYSTEM* will overwrite the contents saved in previous runs for the same pipeline.

To view the current contents in *FILESYSTEM*, click on the *FILESYSTEM* button.

.. image:: /_static/imgs/user/pipeline/view_filesystem.png
    :width: 600

To preserve the file contents in a pipeline run, toggle on *Use Track* on starting a run.
The files in that pipeline run will be saved in a :doc:`track <track>`
and will not be overwritten in succeeding pipeline runs.

.. image:: /_static/imgs/user/get_started/run_pipeline_2_1.png
    :width: 480

To view the contents in a track for a pipeline run,

    * Click on the *TRACK* button in the pipeline run page.

        .. image:: /_static/imgs/common/btn_track.png

    * Alternatively, click on the corresponding track in the track listing page.

        .. image:: /_static/imgs/user/get_started/goto_track.png
            :width: 600

        .. note::
            A track is named by the initial part of the project name, followed by the run number.

.. note::
    #) When a pipeline run uses *Track*, the files are displayed in the *Track* page.
       Otherwise, the files are displayed in the *FILESYSTEM* page.
    #) Refer to the :doc:`track <track>` documentation for data visualization and other *Track* operations.

Delete a Pipeline
=================

To delete a pipeline:

#) Go to the settings page by clicking on the *SETTINGS* button.

    .. image:: /_static/imgs/common/btn_settings_2.png

#) Click on the *DELETE* button.

    .. image:: /_static/imgs/user/pipeline/del_pipeline_1.png
        :width: 600

#) Click on the *OK* button.