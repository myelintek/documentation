##########
Lab
##########

A lab is a Web IDE (based on `JupyterLab <https://jupyter.org/>`_ with MLSteam's add-on functionalities) that organizes files and datasets.
You may design ML models and make experiments in a lab.
When the development is done, you may convert a lab into a :doc:`template <template>`
for reuse in other labs, pipelines or deployment.

Create a Lab
============

A lab is created from a pre-defined template.

#) In the lab page, click on the *NEW* button.

    .. note::
        A :doc:`project <project>` should be created first before we could create or use a lab.

#) Select a template.

    .. image:: /_static/imgs/user/lab/add_lab_1.png
        :width: 700

#) Fill in the fields in the dialog, and then click on the *CREATE* button.

    * Name: lab name
    * Flavor: the resources allocated for the lab
            
        .. image:: /_static/imgs/user/lab/add_lab_2.png
            :width: 300

    .. note::
        #) Some labs require one or more GPUs to run. Make sure you select a flavor that meets the lab's requirements.
        #) GPUs are independently allocated for each started lab or pipeline run.
           If a lab could not be started due to a shortage of resources, try to :ref:`stop unused labs <delete-lab>` or to stop pipeline runs.


Run a Lab
=========

After a lab is created, the lab development environment, *JupyterLab*,
could be accessed by clicking on the *Jupyter* button.

.. image:: /_static/imgs/user/lab/goto_jupyter.png
    :width: 480

Program code in a *JupyterLab Notebook* is organized in *cells*.
A JupyterLab Notebook file has a name ended with ``.ipynb``
and could be opened by double clicking on the entry in the *File Browser* on the left.
In JupyterLab Notebook, code is run in a process called the Kernel.

To run (evaluate) the program code in a single cell,
click on the menu item: *Run* → *Run Selected Cells* or press the :kbd:`Shift-Enter` key combination.

.. note::
    Depending on the Kernel execution state, sometimes you may need to run all previous cells before running the current one.
    Click on the menu item: *Run* → *Run All Above Selected Cell*.

To run all the program code from a clean Kernel execution state,
click on the menu item: *Run* → *Restart Kernel and Run All Cells*.

.. image:: /_static/imgs/user/lab/jupyter_cell.png
    :width: 700

.. _open-web-terminal:

To open a terminal for running commands:

#) Click on the *New Launcher* icon in *File Browser* or click on the menu item: *File* → *New Launcher*.

    .. image:: /_static/imgs/user/lab/btn_new_launcher.png

#) Click on the *Terminal* icon in the *Launcher* tab.

    .. image:: /_static/imgs/user/lab/open_terminal_1.png
        :width: 700

#) A Linux terminal will open. You could type and run shell commands now.

    .. image:: /_static/imgs/user/lab/open_terminal_2.png
        :width: 700

Jupyter also supports adding, deleting, and renaming files in its *File Browser* on the left.

.. note::
    Refer to `JupyterLab Documentation <https://jupyterlab.readthedocs.io/en/stable/index.html>`_ for more usage information.

Attach or Detach a Folder
==========================

To list and manage the folder attachments, click on the top area. A side bar will be opened.

.. image:: /_static/imgs/user/lab/view_attached_datasets.png
    :width: 700

To attach or detach a dataset:

#) Click on the *settings* button in the dataset side bar.

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

Monitor Resource Consumption
=====================================

To monitor the real-time resource consumption, click on the top area. A watch window will be opened.

.. image:: /_static/imgs/user/get_started/run_lab_6.png
    :width: 700

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

.. note::

    Stopping a Lab in a Basic Project, the whole Lab container files will be saved into a docker image automatically

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

MLSteam also supports accessing a lab with SSH,
which is handy for developers to use their favorite editors or tools to accelerate ML design and experiments.

Preparation
-----------

Enable SSH access to a lab.

#) In the lab's page, open the settings side bar by clicking on *settings* button on the top.
#) Create a SSH access key if none exists by clicking on the *add* button in the *SSH Key* section.

    .. image:: /_static/imgs/user/lab/add_ssh_key_0.png
        :width: 700

#) Input the key expiration days.
#) Click on the *ADD* button.

    .. image:: /_static/imgs/user/lab/add_ssh_key_1.png
        :width: 300

#) Download the SSH access key by expanding the *SSH Key* section and clicking on the *download* button.

    .. image:: /_static/imgs/common/btn_download.png

#) Save the SSH access key to the local computer.

    .. image:: /_static/imgs/user/lab/add_ssh_key_2.png
        :width: 480

    .. note::
        For the *Linux* operating systems, change the file permission to `600`.

        .. code-block:: shell

            chmod 600 /path/to/access/key/file
            # for example, chmod 600 ~/Downloads/u7fda28d_sshkey.pub

   .. _ssh-info:

#) View the SSH information by clicking on the *view* icon.

    .. image:: /_static/imgs/user/lab/add_ssh_key_3.png
        :width: 300

    .. image:: /_static/imgs/user/lab/add_ssh_key_4.png
        :width: 300

#) Now, you could access the lab using an SSH client tool,
   such as :ref:`command-line <ssh-commandline>`, :ref:`VSCode <ssh-vscode>`,
   or :ref:`MobaXterm <ssh-mobaxterm>`.

.. _ssh-commandline:

Command Line
------------

#) Open a command-line console.
#) Copy the command from the :ref:`SSH command line <ssh-info>` displayed in the lab page,
   and run it in the console.

    .. note::
        Change ``SSH_ACCESS_KEY_FILE`` to the actual SSH key file location.

        .. code-block:: shell

            ssh -X -p SSH_PORT -i SSH_ACCESS_KEY_FILE USER@SSH_HOST
            # for example, ssh -X -p 49191 -i ~/Downloads/u7fda28d_sshkey.pub root@192.168.0.1

        You may receive a warning message ``The authenticity of host ... can't be established.``
        for the first time you make an SSH connection to the lab. Enter ``yes`` to continue connecting.

.. _ssh-vscode:

VSCode
------

#) Install `VSCode <https://code.visualstudio.com/Download>`_ on the local computer.
#) Open VSCode, search and install the `Remote SSH <https://code.visualstudio.com/docs/remote/ssh>`_ extension.

    .. image:: /_static/imgs/user/lab/install_vscode_remote_ssh.png
        :width: 480

#) Edit the SSH configuration file and add the configuration
   according to the :ref:`SSH command line <ssh-info>` displayed in the lab page.

    .. image:: /_static/imgs/user/lab/add_ssh_key_5.png
        :width: 480

    .. note::
        The SSH configuration file on a Windows computer is at ``C:\Users\{USER-NAME}\.ssh\config``.
        On a MacOS or Linux computer, it is at ``~/.ssh/ssh_config``.

        SSH configuration format:

        .. code-block::

            Host UNIQUE_SSH_CONNECTION_NAME
                HostName SSH_HOST_IP_OR_DOMAIN_NAME
                User USERNAME
                Port SSH_PORT
                IdentityFile SSH_ACCESS_KEY_FILE

        For example,

        .. code-block::

            Host mylab
                HostName 192.168.0.1
                User root
                Port 49191
                IdentityFile C:\Users\geoyb\temp\u7fda28d_sshkey.pub

#) In VSCode, open the *Remote Explorer* panel on the left.

    .. image:: /_static/imgs/user/lab/open_ssh_vscode_1.png
        :width: 480

    .. note::
        If the SSH host has not been displayed, refresh the list by clicking on the *refresh* button.

#) Connect to the SSH host by clicking on the *connection* button. This will open a new VSCode window.

    .. image:: /_static/imgs/user/lab/open_ssh_vscode_2.png
        :width: 480

#) Answer the questions from VSCode on opening the remote host:

    #) Select platform of the remote host: ``Linux``
    #) Are you sure you want to continue? ``Continue``

    .. image:: /_static/imgs/user/lab/open_ssh_vscode_3.png
        :width: 480

#) Wait while VSCode is initializing the remote host.
#) Finally, open the terminal by clicking on the menu item:
   *Terminal* → *New Terminal*
#) Now, you could run commands in the lab through the terminal.

    .. image:: /_static/imgs/user/lab/open_ssh_vscode_4.png
        :width: 480

.. _ssh-mobaxterm:

MobaXterm
---------

Windows users may also use `MobaXterm <https://mobaxterm.mobatek.net/download.html>`_
to make SSH connection.

.. note::
    In session settings, specify ``SSH_HOST``, ``USERNAME``, ``SSH_PORT``, ``X11 forwarding``,
    and ``SSH_ACCESS_KEY`` according to the :ref:`SSH command line <ssh-info>` displayed in the lab page.

    .. image:: /_static/imgs/user/lab/set_x_forward_1.png
        :width: 480

.. _lab-hyperparameter-tuning:

Hyperparameter Tuning by Submitting Tracks
==========================================

To run ML experiments with a set a hyperparameters:

#) Create/modify ``mlsteam.yml`` file in the ``/mlsteam/lab`` directory.
#) ``command`` field is required. Define ``params`` fields to serve as hyperparameters
   to be appended to the command (values can be adjusted later).

    .. image:: /_static/imgs/user/lab/tune_parms_mlsteam_yml.png
        :width: 700

#) In the lab page, click on the *hyperparameter* icon in the top area.
#) Fill in the parameters to use in the sidebar.

    .. image:: /_static/imgs/user/lab/tune_parms_1.png
        :width: 700

    .. note::
        You could provide multiple parameter values delimited by commas.

#) Click on the *Submit track* menu item to submit the experiments as *track*.

    .. image:: /_static/imgs/user/lab/tune_parms_2.png
        :width: 700

#) Click on the *SUBMIT* button.

    .. image:: /_static/imgs/user/lab/tune_parms_3.png
        :width: 480

#) A new browser window will open, which shows the submitted :doc:`tracks <track>`.

    .. image:: /_static/imgs/user/lab/tune_parms_4.png
        :width: 700

    .. note::
        Each combination of the parameter values is used to the ML experiment with a track.

        In the above example,
        ``batch_size`` is given 2 values (*16* and *32*),
        ``epochs`` given 3 values (*3*, *5*, and *10*),
        and ``optimizer`` given 1 value (*SGD*),
        so there are *6* (= 2 * 3 * 1) tracks in total.

#) The parameter values used and other logged data could be observed by clicking into a track.

    .. image:: /_static/imgs/user/lab/tune_parms_5.png
        :width: 480

    .. note::
        Refer to the :doc:`track <track>` documentation for the concepts of track.

View Log
========

Once the lab is running, you will notice several buttons in the upper right corner:

#) Click on the *Text-Symbol* button (hover over it to reveal *more*) to access additional functions.

    .. image:: /_static/imgs/user/lab/labframe_hover_more.png
        :width: 350

#) Press the *Display logs* button.

    .. image:: /_static/imgs/user/lab/labframe_more.png
        :width: 250

#) The logs screen will appear instantly.

    .. image:: /_static/imgs/user/lab/labframe_log.png
        :width: 700

 
Flavor Settings
=================

In *Flavor Settings*, flavor type, shared memory size, and GPU compute mode can be modified.

#) Click the *Settings* button. (hover over it to reveal *Settings*) 

    .. image:: /_static/imgs/user/lab/labframe_hover_settings.png
        :width: 300

#) Press the *Flavor* button to expand the item.
#) Click  the *pen* icon or the grayed area to make modifications.

    .. image:: /_static/imgs/user/lab/labframe_setting_flavor.png
        :width: 270

#) Update them if necessary.

    .. image:: /_static/imgs/user/lab/labframe_flavor_SML.png.png
        :height: 150

    .. image:: /_static/imgs/user/lab/labframe_flavor_GPU.png.png
        :height: 150

    .. note:: 
        Refer to the :ref:`Plan <plandoc>` documentation for adjust the `shared memory limit`.


Troubleshooting & FAQs
======================

.. contents:: Contents
    :depth: 1
    :local:
    :backlinks: none

Q: How to run Linux commands in a Lab?
---------------------------------------

Yes, three methods are available:

#) :ref:`Open a JupyterLab Web terminal <open-web-terminal>` and run commands in MLSteam.
#) Open an independent Web terminal by clicking on the *terminal* button for the lab.

    .. image:: /_static/imgs/user/lab/open_independent_terminal_1.png
        :width: 480

    .. image:: /_static/imgs/user/lab/open_independent_terminal_2.png
        :width: 700

#) :ref:`Set up SSH access <ssh-into-lab>` to the lab
   and run commands with your favorite tools on the local computer,
   such as an SSH client or *VSCode*.

Q: How to view the ML program and run the experiments on the local computer?
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
        :width: 700

#) Go to the ``/mlsteam`` directory and click on the *OK* button.

    .. image:: /_static/imgs/user/lab/view_remote_files_vscode_2.png
        :width: 480

#) Click on the *Trust Folder & Continue* button.

    .. image:: /_static/imgs/user/lab/view_remote_files_vscode_3.png
        :width: 300

#) Then, you could view and edit the files in usual way.

    .. image:: /_static/imgs/user/lab/view_remote_files_vscode_4.png
        :width: 700

    .. note::
        #) *VSCode* access the files *remotely*. The files are still saved in the MLSteam system.
        #) You may install *Python extension for Visual Studio Code* to use the advanced features for Python files.
        #) It is possible to view, edit, and run a *JupyterLab Notebook program* in *VSCode*
           when the relevant extensions are installed.
           However, such a feature, provided by the  *VSCode* community, is currently unstable.
           It is suggested using the MLSteam's *JupyterLab* Web interface to deal with *JupyterLab Notebook programs* directly.

Q: How to add Jupyter support in a lab?
---------------------------------------

To add Jupyter support in a lab:

#) Ensure JupyterLab is installed.

    In the lab's terminal, run the following command:

    .. code-block:: shell

        jupyter lab --version

    If the command fails, install the latest version of JupyterLab by

    .. code-block:: shell

        pip3 install jupyterlab

#) Change the lab's start type.

    #) In the lab's page, open the settings side bar by clicking on *settings* button on the top.

        .. image:: /_static/imgs/common/btn_settings_3.png

    #) Expand the *Start Type* section in the side bar and click on the *settings* button.

        .. image:: /_static/imgs/user/lab/set_start_type_1.png
            :width: 300

    #) In the popped up dialog, select the start type option *Jupyter + Terminal*, and click on the *Update* button.
       The lab will be restarted with the new start type settings. You could then access Jupyter.

       .. note::
        If the lab fails to start after you update the settings, repeat the above steps and change the start type
        back to *Terminal*, and it should be able to start again. You may check the JupyterLab installation through
        the lab's terminal.

Q: How to change the type of GPU used in a lab?
-----------------------------------------------

It is achieved through changing the flavor of a lab.

#) Ensure the flavor for the target GPU type exists.

   .. note::
      A flavor could be :ref:`created <management-flavor>` in the management page.

#) Open the *JupyterLab* for the lab.
#) Open the settings side bar by clicking on the *settings* button on the top.

    .. image:: /_static/imgs/common/btn_settings_3.png

#) Expand the *Specification* section in the side bar and click on the *settings* button.

    .. image:: /_static/imgs/user/lab/set_flavor_1.png
        :width: 300

#) Select the flavor with the target GPU.
#) Click on the *UPDATE* button.

    .. image:: /_static/imgs/user/lab/set_flavor_2.png
        :width: 300

#) Click on the *OK* button. The lab will run on the selected GPU type after a restart.

Q: How to access other Web services running in a lab?
-----------------------------------------------------

To access the services in a lab, export the corresponding port(s) with *proxy*:

#) Click on the *settings* button.
#) Expand the *Proxy* section in the side bar and click on the *add* button.

    .. image:: /_static/imgs/user/lab/add_proxy_1.png
        :width: 700

#) Fill in the port the service is running on.
#) Click on the *ADD* button.

    .. image:: /_static/imgs/user/lab/add_proxy_2.png
        :width: 300

    .. note::
        Repeat the port adding steps for each port needed in accessing the service.

#) The mapping between service ports and exposed ports are displayed.
   You could now access the service with URL ``{MLSteam address}:{Exposed port}``.

    .. image:: /_static/imgs/user/lab/add_proxy_3.png
        :width: 300

    .. image:: /_static/imgs/user/lab/add_proxy_4.png
        :width: 480

Q: How to avoid other programs from sharing the GPU card(s) used in my lab?
---------------------------------------------------------------------------

By default, a GPU card may be shared among running of programs,
which is possible in situations where multiple running programs are using GPUs in the lab,
or where other programs on the host machine (not managed by MLSteam) are using the same GPUs.
Sharing a GPU card would enhance the GPU utilization
but may also affect the amount of GPU resources (such as GPU computation cores or GPU memory)
available for a single running program.

It is possible to restrict how a GPU device is used by setting the *accelerator compute mode*.

#) Click on the *settings* button.
#) Expand the *Configuration* section in the side bar and open the *Accelerator Mode* menu.

    .. image:: /_static/imgs/user/lab/set_accelerator_mode_1.png
        :width: 300

#) Select the *accelerator compute mode*. Available modes:

        * *default*: multiple processes can use the GPU device at the same time
        * *exclusive_process*: only one process can use the GPU device at the same time
        * *prohibited*: no processes can use the GPU device

        .. note::
            A *process* could be roughly thought of as a running program.
            Each running program has a process;
            sometimes a running program may have multiple processes, though.

Q: How to increase the shared memory size in the lab?
-----------------------------------------------------

Some programs require more shared memory,
especially those that communicate heavily between processes with shared memory buffer,
or those that use many GPU cores and consume lots of data.

To increase (or decrease) the shared memory size in a lab:

#) Click on the *settings* button.
#) Expand the *Configuration* section in the side bar and fill in the *Shared Memory* field.

    .. image:: /_static/imgs/user/lab/set_shared_memory_1.png
        :width: 300

    .. note::
        The shared memory size is in ``GB`` and should be a positive integer.

#) The lab will be restarted with the new setting.

Q: How to access Linux Graphics User Interface (X Window System) applications installed in the lab?
---------------------------------------------------------------------------------------------------

To run a Linux application and access it at the local desktop environment:

#) :ref:`Set up SSH access <ssh-into-lab>` to the lab.

    #) Add an SSH access key in the lab if none exists.
    #) Download the SSH access key and save it at client side.
    #) (Linux or macOS users) Change the file permission mode for the SSH access key.
    #) Copy the SSH access command.

#) Connect to the lab from the client side.

    Run the SSH access command (copied from the previous step) in a :ref:`commandline console <ssh-commandline>`,
    or with a user-friendly software such as :ref:`MobaXterm <ssh-mobaxterm>`.

#) Now, you may run the desired Linux application through the SSH connection at client side,
   and the window will be displayed at client side.

    .. image:: /_static/imgs/user/lab/set_x_forward_2.png
        :width: 480
