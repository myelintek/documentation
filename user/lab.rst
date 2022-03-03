##########
Lab
##########

A lab is a Web IDE (based on `JupyterLab <https://jupyter.org/>`_ with MLSteam's add-on functionalities) that organizes files and datasets.
You may design ML models and make experiments in a lab.
When the development is done, you may convert a lab into a :doc:`template <template>` for reuse in other labs, pipelines or deployment.

Create a Lab
============

A lab is created from a pre-defined template.

#) In the lab page, click on the *NEW* button.

    .. note::
        A :doc:`project <project>` should be created first before we could create or use a lab.

#) Select a template.

    .. image:: /_static/imgs/user/get_started/add_lab_1.png
        :width: 600

#) Fill in the fields in the dialog, and then click on the *CREATE* button.

    * Name: lab name
    * Flavor: the resources allocated for the lab
    * Dataset mount paths (optional): pre-defined by the template. You may add or delete the mount paths.

    .. note::
        #) Some labs require one or more GPUs to run. Make sure you select a flavor that meets the lab's requirements.
        #) GPUs are independently allocated for each started lab or pipeline run.
           If a lab could not be started due to a shortage of resources, try to :ref:`stop unused labs <delete-lab>` or to stop pipeline runs.


Run a Lab
=========

Program code in a *Jupyter Notebook* is organized in *cells*. 
A Jupyter Notebook file has a name ended with ``.ipynb`` and could be opened by double clicking on the entry in the *File Browser* on the left.
In Jupyter Notebook, code is run in a process called the Kernel.

To run (evaluate) the program code in a single cell,
click on the menu item: *Run* → *Run Selected Cells* or press the :kbd:`Shift-Enter` key combination.

.. note::
    Depending on the Kernel execution state, sometimes you may need to run all previous cells before running the current one.
    Click on the menu item: *Run* → *Run All Above Selected Cell*.

To run all the program code from a clean Kernel execution state,
click on the menu item: *Run* → *Restart Kernel and Run All Cells*.

.. image:: /_static/imgs/user/get_started/run_lab_3a.png
    :width: 600

.. _open-web-terminal:

To open a terminal for running commands:

#) Click on the *New Launcher* icon in *File Browser* or click on the menu item: *File* → *New Launcher*.

    .. image:: /_static/imgs/user/lab/btn_new_launcher.png

#) Click on the *Terminal* icon in the *Launcher* tab.

    .. image:: /_static/imgs/user/lab/open_terminal_1.png
        :width: 600

#) A Linux terminal will open. You could type and run shell commands now.

    .. image:: /_static/imgs/user/lab/open_terminal_2.png
        :width: 600

Jupyter also supports adding, deleting, and renaming files in its *File Browser* on the left.

.. note::
    Refer to `JupyterLab Documentation <https://jupyterlab.readthedocs.io/en/stable/index.html>`_ for more usage information.

Attach or Detach a Dataset
==========================

To list and manage the dataset attachments, click on the top area. A side bar will be opened.

.. image:: /_static/imgs/user/lab/view_attached_datasets.png
    :width: 600

To attach or detach a dataset:

#) Click on the settings button in the dataset side bar.

    .. image:: /_static/imgs/common/btn_settings.png

#) Toggle on a dataset to attach or toggle off a dataset to detach.

    .. image:: /_static/imgs/user/lab/set_dataset_attachments_1.png
        :width: 480

#) Click on the *APPLY* button.
#) Click on the *OK* button. The lab will be restarted to apply the new configuration.

    .. image:: /_static/imgs/user/lab/set_dataset_attachments_2.png
        :width: 300

.. note::
    The dataset path is available by hovering over the dataset or by clicking on the *copy* icon in the end.

    .. image:: /_static/imgs/user/lab/view_dataset_path.png
        :width: 300

Monitor Resource Consumption in a Lab
=====================================

To monitor the real-time resource consumption, click on the top area. A watch window will be opened.

.. image:: /_static/imgs/user/get_started/run_lab_6.png
    :width: 600

Hardware resources displayed:

* Compute

    * CPU utilization in percentage

* Memory

    * memory utilization in percentage
    * used memory in GB
    * total memory in GB

* Storage

    * disk storage in percentage
    * used storage in GB
    * total storage in GB

* GPU

    * GPU compute utilization in percentage
    * used GPU memory in GB
    * total GPU memory in GB

.. _delete-lab:

Stop or Delete a Lab
====================

To delete a lab:

#) If the lab is in the *running* state, stop the lab by clicking on the *stop* button.

    .. image:: /_static/imgs/user/lab/stop_lab_1.png
        :width: 480

#) Click on the *delete* button.

    .. image:: /_static/imgs/user/lab/stop_lab_2.png
        :width: 480

.. _ssh-into-lab:

SSH into a Lab
==============

MLSteam also support accessing a lab with SSH,
which is handy for users to use their favorite editors or tools to accelerate ML design and experiments.
This section will show instructions for VSCode.

.. note::
    This feature is only available in labs running in SSH-enabled containers.
    E.g., labs created from the *Pytorch Cifar10* are SSH-enabled by default.

    You may also install an SSH server to enable SSH in a Ubuntu-based container
    by running the commands in a terminal:

    .. code-block:: shell

        apt-get update
        apt-get install openssh-server

VSCode
------

Preparation:

#) Install `VSCode <https://code.visualstudio.com/Download>`_ on the local computer.
#) Open VSCode, search and install the `Remote SSH <https://code.visualstudio.com/docs/remote/ssh>`_ extension.

    .. image:: /_static/imgs/user/lab/install_vscode_remote_ssh.png
        :width: 480

To enable SSH access to a lab:

#) Open the lab to access.
#) Click on the settings button in the dataset side bar.

    .. image:: /_static/imgs/common/btn_settings.png

#) Create a SSH access key by clicking on the *add* button in the *SSH Key* section.

    .. image:: /_static/imgs/common/btn_add.png

#) Input the key expiration days.
#) Click on the *ADD* button.

    .. image:: /_static/imgs/user/lab/add_ssh_key_1.png
        :width: 300

#) Download the SSH access key by expanding the *SSH Key* section and clicking on the *download* button.

    .. image:: /_static/imgs/common/btn_download.png

#) Save the SSH access key to the local computer.

    .. image:: /_static/imgs/user/lab/add_ssh_key_2.png
        :width: 480

#) View the SSH configuration by clicking on the *view* icon.

    .. image:: /_static/imgs/user/lab/add_ssh_key_3.png
        :width: 300

#) Copy the SSH configuration text displayed.

    .. image:: /_static/imgs/user/lab/add_ssh_key_4.png
        :width: 300

#) Open the SSH configuration file on the local computer.
   Append the configuration text in the previous step. Save the file.

    .. image:: /_static/imgs/user/lab/add_ssh_key_5.png
        :width: 480

    .. note::
        #) The SSH configuration file on a Windows computer is at ``C:\Users\{USER-NAME}\.ssh\config``.

           On a MacOS or Linux computer, it is at ``~/.ssh/ssh_config``.
        #) The SSH configuration text displayed by MLSteam assumes
           the access key is saved in the ``Downloads`` directory.
           If the access key file is renamed or saved in another directory,
           replace the settings of ``IdentityFile`` by the actual file location.

Now, we are ready to access the lab with VSCode.

#) In VSCode, open the *Remote Explorer* panel on the left.
   The SSH host we just configured will be displayed in the *SSH TARGETS* section.

    .. image:: /_static/imgs/user/lab/open_ssh_vscode_1.png
        :width: 300
    
    .. note::
        If the SSH host has not been displayed, refresh the list by clicking on the *refresh* button.

#) Connect to the SSH host by clicking on the *connection* button. This will open a new VSCode window.

    .. image:: /_static/imgs/user/lab/open_ssh_vscode_2.png
        :width: 480

#) Answer the questions from VSCode on opening the remote host:

    #) Select platform of the remote host: ``Linux``
    #) Are you sure you want to continue? ``Continue``

    .. image:: /_static/imgs/user/lab/open_ssh_vscode_3.png
        :width: 600

#) Wait while VSCode is initializing the remote host.
#) Finally, open the terminal by clicking on the menu item:
   *Terminal* → *New Terminal*
#) Now, you could run commands in the lab through the terminal.

    .. image:: /_static/imgs/user/lab/open_ssh_vscode_4.png
        :width: 600

Hyperparameter Tuning
=====================

TODO: Submit a training job, Multiple

Save a Lab as a Template
========================

Troubleshooting & FAQs
======================

Q: Could I run Linux commands in a Lab?
---------------------------------------

Yes, two methods are available:

#) :ref:`Open a Web terminal <open-web-terminal>` and run commands in MLSteam.
#) :ref:`Set up SSH access <ssh-into-lab>` to the lab
   and run commands with your favorite tools on the local computer,
   such as an SSH client or *VSCode*.

Q: Could I view the ML program and run the experiments on the local computer?
-----------------------------------------------------------------------------

MLSteam includes a powerful Jupyter-based interface for
viewing, editing, and running the ML programs.

However, if you prefer using a handy tool on the local computer.
You could do so by :ref:`setting up SSH access <ssh-into-lab>` to the lab.
The lab files are under the ``/mlsteam`` directory.

The instructions below are for *VSCode*.

To view and edit files in the lab:

#) Open the *Explorer* panel on the left.
#) Click on the *Open Folder* button.

    .. image:: /_static/imgs/user/lab/view_remote_files_vscode_1.png
        :width: 600

#) Go to the ``/mlsteam`` directory and click on the *OK* button.

    .. image:: /_static/imgs/user/lab/view_remote_files_vscode_2.png
        :width: 480

#) Click on the *Trust Folder & Continue* button.

    .. image:: /_static/imgs/user/lab/view_remote_files_vscode_3.png
        :width: 300

#) Then, you could view and edit the files in usual way.

    .. image:: /_static/imgs/user/lab/view_remote_files_vscode_4.png
        :width: 600

    .. note::
        #) *VSCode* access the files *remotely*. The files are still saved in the MLSteam system.
        #) You may install *Python extension for Visual Studio Code* to use the advanced features for Python files.

To view, edit, and run a *Jupyter Notebook program*:

#) Open the *Jupyter Notebook* program file in the *Explorer* panel on the left.

    .. image:: /_static/imgs/user/lab/view_remote_notebooks_vscode_1.png
        :width: 600
    
#) It is possible to run the program by clicking on the *run* button.

    .. note::
        #) This *VSCode* feature is currently unstable.
           It is suggested turning back to the MLSteam's Jupyter interface
           if you have some problems running the experiments remotely through *VSCode*.
        #) Python 3.7 or higher is needed for this feature.
           You may install a supported Python version in a lab by running the commands in a terminal:

           .. code-block:: shell

               apt-get update
               apt-get install software-properties-common
               add-apt-repository ppa:deadsnakes/ppa
               apt-get install python3.8
        
        #) You may need to install extensions or change the Python version used when it is prompted by *VSCode*.

TODO: Run with web terminal, change flavor, proxy, configuration