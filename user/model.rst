#########
Model
#########

A model is a collection of files that record a trained ML model.

.. _create-model:

Create and Manage a Model
=========================

To create a model:

#) In the models page, click on the *NEW* button.
#) Fill in the model name and description in the dialog.
#) Click on the *CREATE* button.

    .. image:: /_static/imgs/user/model/add_model_1.png
        :width: 700

#) You can see the new created model name is on the Model page

Create Model Version from data
------------------------------

#) Go to the model page by clicking on the link of model.

    .. image:: /_static/imgs/user/model/add_model_2.png
        :width: 700

#) Click on the *NEW VERSION* button.

    .. image:: /_static/imgs/user/model/new_version.png
        :width: 700

#) Fill in the model version and select the model files.
   The model files could be selected from a :doc:`track <track>`
   or from a :doc:`folder <folder>`.

    .. note::
        To select the model files, choose the data source (a track or a dataset),
        select one or multiple files or folders, and then click on the *INSERT* button.

        You may repeat this step to add more model files from different sources or folders.

        .. image:: /_static/imgs/user/model/add_model_3.png
            :width: 700

#) Click on the *CREATE* button.

    .. image:: /_static/imgs/user/model/add_model_4.png
        :width: 300

#) The new model version will be displayed.

    .. image:: /_static/imgs/user/model/add_model_5.png
        :width: 700


Create Model Version from MLFlow/BentoML
----------------------------------------

#) Go to the Track page and select a MLFlow generated Track record.
#) Click on *Register Model* Button on the top.

    .. image:: /_static/imgs/user/model/add_track_model_1.png
        :width: 700

#) Select *Model* and given a *Version* name, click *Create*.

    .. image:: /_static/imgs/user/model/add_track_model_2.png
        :width: 700

#) The new model version will be created as shown below

    .. image:: /_static/imgs/user/model/add_track_model_3.png
        :width: 700

Build Model Template
====================

Build Model as a template, please reference to :ref:`Model Build <modelbuild_bento>`


Encrypt a Model
===============

MLSteam enables model protection with :ref:`encrypted model packages <core-concept-model>`.

To encrypt a model:

#) Make sure the model files have been saved in a project folder.
#) :ref:`Create a model <create-model>` if does not exist.
#) Go to the model page and click on the *New Version* button.
#) Set the following fields.

    * Version: the model version name
    * Type: select ``packaged-encrypted``
    * Within the *model files* tab, add the model files from the folder.
    * Within the *hook files* tab, add the hook files from the folder.
    * Within the *manifest* tab, add the manifest file from the folder.
    * Within the *encryption* tab, select the encryption key generation method:

      * *Auto generation* generates a model-specific strong encryption key by MLSteam.
      * *Customize* enables specifying the key passphrase. A strong encryption key is derived from the passphrase.

        .. note::
            Customization is useful in controlling the key generation
            (such as having consistent model encryption keys among a set of models that will be deployed together).

    .. image:: /_static/imgs/user/model/add_enc_model_1.png
        :width: 300

#) Click on the *Create* button.

.. note::
    Encrypted models can be accessed through
    `MLSteam Model SDK <https://mlsteam-model-sdk-doc.readthedocs.io/en/latest/index.html>`_.

Example
-------

To create an encrypted model for time-series prediction:

#) Upload the following files into an empty project folder:

    * Package files: :download:`model.zip </_downloads/stockpred/model.zip>`
    * Runtime requirements: :download:`requirments.txt </_downloads/stockpred/requirements.txt>`

#) Extract ``model.zip`` within the folder.
#) Create a *packaged-encrypted* model version by adding the following files:

    * Within the *model files* tab, add ``models/`` directory from the folder.
    * Within the *hook files* tab, add the ``hooks/`` directory from the folder.
    * Within the *manifest* tab, add the ``manifest.json`` file from the folder.
    * Within the *encryption* tab, select *Auto generation* method.

#) A new encrypted model version is created.

    .. image:: /_static/imgs/user/workspace/add_enc_model_2.png
        :width: 480

Delete a Model
==============

To delete a model version:

    #) Click on the *delete* button for the model version.

        .. image:: /_static/imgs/user/model/del_model_version.png
            :width: 420

    #) Click on the *OK* button.
