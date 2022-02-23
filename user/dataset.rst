############
Dataset
############

A dataset is a collection of data organized in files and directories.
Dataset files could be used in labs for model training and validation.

There are system datasets and project-scoped datasets.
The datasets page lists all projects visible to the user,
where the system datasets are displayed in the dataset name,
and the project-scoped datasets are displayed in the beloning project's ID followed by the dataset name.

.. image:: /_static/imgs/user/dataset/view_all_datasets.png
    :width: 600

The project datasets page lists all project-scoped datasets for the current project.
A system dataset is not accessible by a project before it is :ref:`added as a project-scoped dataset <create-and-manage-project-scoped-dataset>`.

.. image:: /_static/imgs/user/dataset/view_project_datasets.png
    :width: 600

A dataset could have multiple versions by creating *snapshots*.
TODO: restoration

.. _create-and-manage-project-scoped-dataset:

Create and Manage a Project-Scoped Dataset
==========================================

To create a database:

#) Click on the *ADD* button in the dataset page.
#) Select the dataset type and fill in the fields:

    #) *Empty Dataset* (create an empty dataset stored in the MLSteam system space):

        * Dataset name: dataset name

        .. image:: /_static/imgs/user/dataset/add_dataset_empty.png
            :width: 300

    #) *Mount NFS* (mount an existing dataset stored in a remote NFS space):

        * Name: dataset name
        * NFS server path: NFS share path. E.g., ``192.168.0.1:/nfs/dataset-1``

        .. image:: /_static/imgs/user/dataset/add_dataset_nfs.png
            :width: 300

    #) *Mount CIFS* (mount an existing dataset stored in a remote CIFS/SMB space):

        * Name: dataset name
        * CIFS server path: CIFS share path. E.g., ``//192.168.0.1/share/dataset-x``
        * User: CIFS username
        * Password: CIFS password

        .. image:: /_static/imgs/user/dataset/add_dataset_cifs.png
            :width: 300

    .. note::
        A remotely accessible NFS/CIFS shared directory could be mounted as a dataset.

#) Click on the *CREATE* or the *IMPORT* button.
    Changes to the dataset will be writen to the remote space.

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
    
    #) Compress all files in an archive file (*.zip*, *.tar*, *.tar.gz*, or *.tgz*).
    #) Upload the archive file.
    #) :ref:`Extract the files <extract-files-from-dataset>` from the archive.

.. _extract-files-from-dataset:

To extract the files from an archive:

#) Select the archive file for extraction (*.zip*, *.tar*, *.tar.gz*, or *.tgz*).
#) Click on the *EXTRACT* button.
#) Click on the *OK* button.

To download a file from the dataset:

#) Select the file to download.
#) Click on the *DELETE* button in the top toolbar or the *download* button in the preview area.
#) Click on the *OK* button.

Create a Project-Scoped Dataset by Cloning
==========================================

In situations where modifications to a read-only dataset (such as a built-in dataset) is needed,
or to leverage a dataset that belongs to another project,
one could clone the dataset of interest and use the clone instead.

To clone a dataset:

#) Click on the *ADD* button in the dataset page.
#) Select *Import Database* from the menu.
#) Select the dataset to clone.

    .. note::
        Datasets beloning to the current project are not listed here.
        To modify such a dataset and to preserve its current data, :ref:`snapshot the dataset <snapshot-dataset>` instead.

#) For cloning a mounted remote dataset, select the import method:

    * *Mount*: mount the remote dataset directly.
      Changes to the dataset will be written to the remote space and viewable by all other projects that mount the same dataset.
    * *Clone*: copy the data from the dataset.
      Data are stored in the MLSteam system space. Changes to the cloned dataset will not affect the original one.

#) Click on the *IMPORT* button.

    .. image:: /_static/imgs/user/dataset/copy_dataset_1.png
        :width: 300

.. note::
    The cloned dataset will belong to the current project and be accessible by the labs and pipeline in the same project.

Delete a Dataset
================

To delete a dataset:

#) Clock on the *delete* button.

    .. image:: /_static/imgs/user/dataset/del_dataset_1.png
        :width: 480

#) Click on the *OK* button.

.. note::
    Deleting a mounted dataset does not delete the dataset contents;
    it only removes the linkage to the remote space.

Preview Bounding Box Images in a Dataset
========================================

.. _snapshot-dataset:

Snapshot a Dataset
==================
