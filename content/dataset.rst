.. _dataset:


*******
Dataset
*******

.. _create_dataset:

Create dataset
==============

Click "New dataset" button.

.. image:: ../_static/dataset/new_dataset.png

Input dataset name and click "Create".

Empty dataset will be created.

.. image:: ../_static/dataset/new_dataset_modal.png

Create dataset from remote source
=================================

Currently system supports creation of dataset from NFS. Admin needs first setup host with password-less privilege for mount.

Click "New dataset". Input dataset name and check "External storage" box. From drop down menu select dataset type as NFS.
Input ip and mount point. click "Create".

.. image:: ../_static/dataset/nfs_dataset.png


Manipulate dataset
==================

Browse dataset
++++++++++++++

Click on dataset name.

.. image:: ../_static/dataset/browse_dataset.png

Clone dataset
+++++++++++++

Click "Clone" button to create a copy of dataset.

.. image:: ../_static/dataset/clone_dataset.png

Upload files to dataset
+++++++++++++++++++++++

Browse needed dataset.

Then drag and drop files from local pc. Or click "Upload" button.

.. image:: ../_static/dataset/upload_dataset.png

Extract files from archive
++++++++++++++++++++++++++

Supported format *tar, tgz, tar.gz, zip.*

Select archive file and click "Extract".

.. image:: ../_static/dataset/extract_dataset.png

New folder
++++++++++

Click "New folder" button to create new folder within dataset.

.. image:: ../_static/dataset/new_folder_dataset0.png

Input folder name. click create.

.. image:: ../_static/dataset/new_folder_dataset.png

Download folder/file
++++++++++++++++++++

Select folders and/or files that need to be downloaded and click "Download".

.. image:: ../_static/dataset/download_dataset.png

Delete folder/file
++++++++++++++++++

Select folders and/or files that need to be deleted and click "Delete".

.. image:: ../_static/dataset/delete_file_dataset.png

Visualize dataset
=================

If the dataset is of standart types it can be visualized.

Sellect folder with images, then click "Visualize" button. Sellect dataset type.
In our example the dataset is of yolov3 type.

.. image:: ../_static/dataset/visualize_dataset.png

Fill all fields with pathes inside datased folder. click "Start". Refresh page to see changes.

.. image:: ../_static/dataset/visualize_dataset_modal.png

Visualization with bounding boxes will appear on the left when one image is selected.

.. image:: ../_static/dataset/visualize_dataset_show.png

If visualization needs to be removed go inside folder with images and click cross on the visualization tag.

.. image:: ../_static/dataset/visualize_dataset_remove.png

Delete dataset
==============

Open the list of datasets then click trash icon in front of dataset name. Confirm.

.. image:: ../_static/dataset/delete_dataset.png
