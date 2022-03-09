#############
Track
#############

A track keeps various results of ML training or experiments,
including the parameters, metrics, console logs, and any logged files or data.
It also enable visualization of the results with *TensorBoard*.

Create a Track
==============

A track could be created from a lab job or from a pipeline run.

To create a track from a lab:

TODO: create track from lab

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

Visualize Data with Tensorboard
===============================

To view multi-dimensional data displayed in Tensorboard:

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
