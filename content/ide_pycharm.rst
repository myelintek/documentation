.. _ide_pycharm_windows:

PyCharm
=======

Tested setup: Window 10, 2019.3.3 (Professional Edition)

Install PyCharm
---------------

Download VSCode that according to your operating system from following link

https://www.jetbrains.com/pycharm/download/

.. image:: ../_static/remote_ide/pycharm/install.png

SSH key
-------

Open needed lab in the browser and generate ssh key.

.. image:: ../_static/remote_ide/sshkey.jpg

Download <lab_id>_sshkey file (downloading will start automatically, if it does not press "Download" button).

.. image:: ../_static/remote_ide/pycharm/download_ssh.png

.. note:: In the Linux operating system, you need to change the sshkey file to 600 mode.

PyCharm Project
---------------

Open the PyCharm application and create new project.

.. image:: ../_static/remote_ide/pycharm/pycharm_open.png

Find the existing interpreter and click the rightmost button in "Pure Python" tab.

.. image:: ../_static/remote_ide/pycharm/pure_python.png

Connect
-------

Type your host, port and user information. (You can find it in lab page)

.. image:: ../_static/remote_ide/pycharm/ssh_interpreter.png

Jump out the warning modal to ask if you need to add new host in ~/.ssh/known_host

Click Yes to continue

.. image:: ../_static/remote_ide/pycharm/connect.png

Select the Key pair option and input the location of the private key.

.. image:: ../_static/remote_ide/pycharm/private_key.png

PyCharm will connect and find the default python path. However, if using MLSteam, you need to select "/ var / bin / python3".

Click Finish to complete the configuration in PyCharm.

.. image:: ../_static/remote_ide/pycharm/python_interpreter.png

Make sure your existing interpreter is correct, then click the "Create" button. You can select a remote project location at this time or later.

.. image:: ../_static/remote_ide/pycharm/create.png

Synchronize
-----------

If you want to change the location of the remote project after the project is created. You can find the configuration in the toolbar. (Tools-> Deployment-> Configuration)

.. image:: ../_static/remote_ide/pycharm/configuration.png

Select the configuration you want to edit. Select the Mapping tab. Click the folder button at the right of Deployment Path.

.. image:: ../_static/remote_ide/pycharm/deployment.png

Selector will display the remote path after a success connection.

Select the desired path and click OK.

.. image:: ../_static/remote_ide/pycharm/deployment_path.png

There is nothing in your folder now.
You can find "Download from" in the toolbar. (Tools-> Deployment-> Download from ...)

.. image:: ../_static/remote_ide/pycharm/download_file.png

Click this button and download all folders and data files from the mapped folder.
You can also click the "Sync with Deployed to ..." button to synchronize the mapped folder and working directory on your local host.

.. image:: ../_static/remote_ide/pycharm/download_log.png

Interpreter
-----------

Next, set up a python interpreter for your project.
Click Settings (Ctrl + Alt + S) in the File tab.

.. image:: ../_static/remote_ide/pycharm/setting.png

Select the project interpreter below the project: <localhost_folder>.
Select your remote python via the drop-down menu.

.. image:: ../_static/remote_ide/pycharm/project_interpreter.png