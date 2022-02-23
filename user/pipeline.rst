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
Action types available:

* *Git pull*: pull source code fromt git repository
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

#) Press on the *re-order* icon. Hold the mouse button.
#) Drag the action onward or downward to the new location.

    .. image:: /_static/imgs/user/pipeline/reorder_action_1.png
        :width: 300

#) Release the mouse button.

Run a Pipeline
==============

.. note::
    The pipeline run number is unique in the system.

Delete a Pipeline
=================

To delete a pipeline:

#) Go to the settings page by clicking on the *SETTINGS* button.

    .. image:: /_static/imgs/common/btn_settings_2.png

#) Click on the *DELETE* button.

    .. image:: /_static/imgs/user/pipeline/del_pipeline_1.png
        :width: 600

#) Click on the *OK* button.