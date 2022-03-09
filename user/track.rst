#############
Track
#############

A track keeps various results of ML training or experiments,
including the parameters, metrics, console logs, and any logged files or data.
It also enables visualization of the results with *TensorBoard*.

Create a Track
==============

A track could be created from a lab job or from a pipeline run.

To create a track from a lab:

#) In the lab page, click on the *Submit* menu item.

    .. image:: /_static/imgs/user/lab/tune_parms_2.png
        :width: 600

#) Click on the *SUBMIT* button.

    .. image:: /_static/imgs/user/lab/tune_parms_3.png
        :width: 480

#) A new browser window will open, which shows the submitted *jobs* as tracks.

    .. note:: 
        One or more tracks will be created
        depending on the :ref:`hyperparameter settings <lab-hyperparameter-tuning>`.

To create a track from a pipeline run:

#) In the pipeline page, click on the *RUN PIPELINE* button.
#) Toggle on *Use Track*.
#) Click on the *RUN NOW* button.

    .. image:: /_static/imgs/user/get_started/run_pipeline_2_1.png
        :width: 480

#) A button that opens the track will be displayed.

    .. image:: /_static/imgs/user/track/add_track_2_1.png
        :width: 600

View Logged Data
================

TODO: view logged data

Visualize Data with TensorBoard
===============================

To view multi-dimensional data displayed in TensorBoard:

#) Click the *SWITCH TO TENSORBOARD* button in the top-left corner.

    .. image:: /_static/imgs/common/btn_switch_to_tensorboard.png

#) TensorBoard will show up in a few seconds.

    .. image:: /_static/imgs/user/get_started/view_tensorboard.png
        :width: 600

.. note::
    Refer to the `TensorBoard <https://www.tensorflow.org/tensorboard>`_ Website for visualization operations.

Delete a Track
==============

To delete a track:

#) Select the track to delete.
#) Click on the *DELETE* button.
#) Click on the *OK* button.
