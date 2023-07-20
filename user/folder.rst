############
Folder
############

A Folder is a collection of data organized in files and directories.
Files in folder, like dateset, could be used in labs for model training and validation.

There are *system datasets* and *project-scoped datasets*.
The datasets page lists all projects visible to the user,
where the system datasets are displayed as the dataset name,
and the project-scoped datasets are displayed as the owner project's ID followed by the dataset name.

.. image:: /_static/imgs/user/dataset/view_all_datasets.png
    :width: 600

The project datasets page lists all project-scoped datasets for the current project.
A system dataset is not accessible by a project before it is :ref:`added as a project-scoped dataset <create-and-manage-project-scoped-dataset>`.

.. image:: /_static/imgs/user/dataset/view_project_datasets.png
    :width: 600

A dataset could have multiple versions by creating :ref:`snapshots <snapshot-dataset>`
and could also revert to a previous saved version.

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
        Using a mounted dataset is essentially accessing a remote network folder.
        There are no requirements for the internal folder or file structure of a remote network folder to mount.
        Changes to such a dataset will be written to the remote space.

#) Click on the *CREATE* or the *IMPORT* button.

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
    To upload many files efficiently:
    
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
#) Click on the *DOWNLOAD* button in the top toolbar or the *download* button in the preview area.
#) Click on the *OK* button.

To delete one or multiple files from the dataset:

#) Select the file(s) to delete.
#) Click on the *DELETE* button.
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
        Datasets belonging to the current project are not listed here.
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
    #) Deleting a mounted dataset does not delete the dataset contents;
       it only removes the linkage to the remote space.
    #) Deleting a dataset does not affect its cloned dataset(s).

Preview Bounding Box Images in a Dataset
========================================

To preview the bounding box images in a labelled dataset:

#) Select the folder that contains the labelled images.
#) Click on the *VISUALIZE* button.
#) Select the label format *yolo*.

    .. image:: /_static/imgs/user/dataset/view_labelled_dataset_1.png
        :width: 600

#) Fill in the fields:

    * class_file: file specifying the label index names
    * label_path: directory for label files
    * predict_path: (optional) model prediction results

    .. image:: /_static/imgs/user/dataset/view_labelled_dataset_2.png
        :width: 300

    .. note::
        A path could be:
        
        * *Relative path*: starting from the current displayed directory
        * *Absolute path*: prefixed by ``/``, starting from the root directory of the dataset

#) Click on the *SUBMIT* button.

The related files and directories will then be added the *yolo* tags.
Bounding boxes and the index names are displayed in the preview area.

.. image:: /_static/imgs/user/dataset/view_labelled_dataset_3.png
    :width: 600

*Yolo* tags could also be removed by clicking on the *cross* button in the end of tag.

.. image:: /_static/imgs/user/dataset/del_dataset_tag.png
    :width: 300

.. _snapshot-dataset:

Snapshot a Dataset
==================

To save the current dataset version (snapshot):

#) In the dataset page, click on the *VERSIONING* button.

    .. image:: /_static/imgs/common/btn_versioning.png

#) Fill in the version name.
#) Click on the *add* button.

    .. image:: /_static/imgs/user/dataset/add_dataset_version_1.png
        :width: 480

To restore the dataset to a saved version:

#) In the dataset page, click on the *VERSIONING* button.
#) Click on the *Restore* button for the version.

    .. image:: /_static/imgs/user/dataset/restore_dataset_version_1.png
        :width: 480
