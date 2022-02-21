############
Dataset
############

A dataset is a collection of data organized in files and directories.
Dataset files could be used in labs for model training and validation.

TODO: could dataset be used in pipelines, templates, or webapps?
TODO: Dataset modeling (owner, permission)

Create and Manage a Dataset
===========================

To create a database:

#) Click on the *ADD* button in the dataset page.
#) Choose the dataset storage location and fill in the fields:

    #) Filesystem (stored in the MLSteam system space):

        * Dataset name: dataset name
        * Storage mode: `default`

        .. image:: /_static/imgs/user/dataset/add_dataset_filesystem.png
            :width: 300

    #) NFS (stored in a remote NFS space):
    #) CIFS (stored in a remote CIFS/SMB space):

#) Click on the *CREATE* button.

More operations on a dataset are available in the dataset page.

.. image:: /_static/imgs/user/dataset/view_dataset.png
    :width: 600

To create a folder in a dataset:

#) In the dataset page, click on the *NEW FOLDER* button.
#) Input the folder name.
#) Click on the *OK* button.

To upload files to a dataset, drag and drop the files into the files area.

.. image:: /_static/imgs/user/dataset/add_file_1_1.png
    :width: 600

Another method for file uploading:

#) In the dataset page, click on the *ADD DATA* button.
#) To add files from the local machine, click on the *BROWSE* button in the *LOCAL* tab and select a file. Repeat this step to add more files.

    .. image:: /_static/imgs/user/dataset/add_file_2_1a.png
        :width: 300

#) Alternatively, to add files from a Web source, input the remote link in the *URL* tab. Repeat this step to add more URLs.

    .. image:: /_static/imgs/user/dataset/add_file_2_1b.png
        :width: 300

    .. note::
        Password-protected links are unsupported.

#) Click on the *UPLOAD* button.

.. note::
    To download many files efficiently:
    
    #) Compress all files in an archive file (*.zip*).
    #) Upload the archive file.
    #) :ref:`Extract the files <extract_files_from_dataset>` from the archive.

.. _extract_files_from_dataset:

To extract the files from an archive:

#) Select the archive file for extraction (*.zip*).
#) Click on the *EXTRACT* button.
#) Click on the *OK* button.

To download a file from the dataset:

#) Select the file to download.
#) Click on the *DELETE* button in the top toolbar or the *download* button in the preview area.
#) Click on the *OK* button.

Clone a Dataset
===============

In situations where modifications to a read-only dataset (such as a built-in dataset) is needed, one could clone the dataset of interest and use the clone instead.

To clone a dataset:

#) Click on the *clone* button.

    .. image:: /_static/imgs/user/dataset/copy_dataset_1.png
        :width: 480

#) Fill in the dataset name.
#) Optionally, change the dataset storage location.
#) Click on the *CREATE* button.

.. note::
    The cloned dataset will belong to the current project. All modifications to a cloned dataset will not affect the original one.

Delete a Dataset
================

To delete a dataset:

#) Clock on the *delete* button.

    .. image:: /_static/imgs/user/dataset/del_dataset_1.png
        :width: 480

#) Click on the *OK* button.

Preview Bounding Box Images in a Dataset
========================================

Snapshot a Dataset
==================
