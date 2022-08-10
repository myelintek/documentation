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

.. note::
    There is a quick way to stop the underlying active *lab job* or *pipeline run* associated with the track.
    Simply click on the *stop* button in the track page.

    .. image:: /_static/imgs/user/track/stop_track_1.png
        :width: 300

Track Your Training
===================

Hyperparameter values and console logs are logged by default in a track.
You could also fetch the hyperparameters and log more information (such as training and testing metrics)
programmatically through the `MLSteam Client library <https://pypi.org/project/mlsteam-client/>`_.

.. note::
    The *MLSteam Client library* is available in most of the built-in lab templates.
    To install the library in customized environments:

    .. code-block::

        pip install mlsteam-client

First, initialize the client:

.. code-block::

    import mlsteam
    from mlsteam import stparams  # optional, for hyperparameter fetching

    track = mlsteam.init()

On submitting a track in :ref:`hyperparameter tuning <lab-hyperparameter-tuning>`,
MLSteam writes the combination of hyperparameter values in the `mlsteam.yml` file,
which could be read by the client.

To fetch hyperparameter values:

    .. code-block::

        stparams.get_value(parm_name, parm_default_val)

    parm_name (str)
        parameter name
    parm_default_val (Any)
        default value when the parameter is undefined

    The following sets the default argument in a training program.

    .. code-block::

        parser = ArgumentParser()
        parser.add_argument('--batch', type=int, default=stparams.get_value('batch', 128))

To log a single value (aka. scalar):

    .. code-block::

        track[log_name] = log_value

    log_name (str)
        logging location.
        You could optionally use slashes `/` to organize the parameters in folders.
    log_value (int, float, or str)
        logging value

    The following logs the language model building settings.

    .. code-block::

        track['model/name'] = 'small_bert'
        track['model/layer'] = 4
        track['model/hidden'] = 256

To log a series:

    .. code-block::

        track[log_name].log(log_value)

    log_name (str)
        logging location.
        You could optionally use slashes `/` to organize the parameters in folders.
    log_value (int, float, or str)
        logging value

    MLSteam timestamps each series logging in the format of `timestamp,log_value`.

    The following logs the model training metrics for each epoch with PyTorch Lightning.

    .. code-block::

        class MyCallback(Callback):
            def on_train_epoch_end(self, trainer, pl_module, result):
                logs = trainer.logged_metrics
                # ['loss/val', 'acc/val', 'epoch', 'loss/train', 'acc/train']
                for key, value in logs.items():
                    track[key].log(value)

View Logged Data
================

To view logged data:

#) Go to the track page by clicking on the track item.

    .. image:: /_static/imgs/user/track/view_track_1.png
        :width: 600

#) All kinds of the logged data (such as parameters, metrics, console logs, and normal files) are organized in directories.
   You could view them in a unified way.

    .. image:: /_static/imgs/user/track/view_track_2.png
        :width: 600

#) You may also keep the view updated periodically by clicking on the *settings* button on the top-right corner

    .. image:: /_static/imgs/common/btn_settings.png

   and then enabling the *Reload data* checkbox. The reload period is in seconds.

    .. image:: /_static/imgs/user/track/view_track_3.png
        :width: 300

    .. image:: /_static/imgs/user/track/view_track_4.png
        :width: 600

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
