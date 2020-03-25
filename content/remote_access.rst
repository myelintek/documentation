****************************
Remote connection to the lab
****************************

This chapter will explain how to connect IDE on user's PC to the lab running on server.

VSCode
======

Tested setup: Ubuntu 16.04, Visual Studio Code - Insiders.

Install `ms-vscode-remote.remote-ssh` extension on VSCode.

Open needed lab in the browser and generate ssh key.


.. image:: ../_static/generate_ssh.png

Download <lab_id>_sshkey file (downloading will start automatically, if it does not press "Download" button).

Change sshkey file permissions to 600:

.. code-block:: console

  chmod 600 <lab_id>_sshkey

On VSCode bottom-right corner press "Open a remote window" then from drop down menu at top-center select "Open configuration file", finaly select needed ssh configuration (usually /home/<user>/.ssh/config).

.. image:: ../_static/vscode_remote1.png

.. image:: ../_static/vscode_remote2-1.png

Copy lab ssh config from web browser and paste to the configuration file. Modify "IdentityFile" field to match the location of <lab_id>_sshkey file.

.. image:: ../_static/vscode_remote2.png

.. image:: ../_static/vscode_remote3.png

Save configuration file.

Press "Open remote window again". 

.. image:: ../_static/vscode_remote1.png

Sellect "Connect to host" from drop down manu. Then sellect host name corresponding to lab.

.. image:: ../_static/vscode_remote2-2.png

VSCode will open new window where it will try to connect to lab. When it asks about fingerprint press "Continue".

.. image:: ../_static/vscode_remote4.png

Now VSCode is connected to the lab container.

To edit lab code go to Explorer and press "Open Folder". Sellect `/mlsteam/lab`, press "OK". When VSCode asks about fingerprint press "Continue".

.. image:: ../_static/vscode_remote5.png

.. image:: ../_static/vscode_remote4.png


PyCharm
=======

Tested setup: Window 10, 2019.3.3 (Professional Edition)

Open needed lab in the browser and generate ssh key.

.. image:: ../_static/generate_ssh.png

Download <lab_id>_sshkey file (downloading will start automatically, if it does not press "Download" button).

.. image:: ../_static/pycharm_remote2.png

Open the PyCharm application and create new project.

.. image:: ../_static/pycharm_remote3.png

Find the existing interpreter and click the rightmost button in "Pure Python".

.. image:: ../_static/pycharm_remote4.png

Type your host, port and user information. (You can find it in lab page)

.. image:: ../_static/pycharm_remote5.png

.. image:: ../_static/pycharm_remote6.png

Jump out the warning modal to ask if you need to add new host in ~/.ssh/known_host

Click Yes to continue

.. image:: ../_static/pycharm_remote7.png

Select the Key pair option and input the location of the private key.

.. image:: ../_static/pycharm_remote8.png

PyCharm will connect and find the default python path. However, if using MLSteam, you need to select "/ var / bin / python3".

Click Finish to complete the configuration in PyCharm.

.. image:: ../_static/pycharm_remote9.png

Make sure your existing interpreter is correct, then click the "Create" button. You can select a remote project location at this time or later.

.. image:: ../_static/pycharm_remote10.png

If you want to change the location of the remote project after the project is created. You can find the configuration in the toolbar. (Tools-> Deployment-> Configuration)

.. image:: ../_static/pycharm_remote11.png

Select the configuration you want to edit. Select the Mapping tab. Click the folder button to the right of Deployment Path.

.. image:: ../_static/pycharm_remote12.png

Selector will display the remote path after a success connection.

Select the desired path and click OK.

.. image:: ../_static/pycharm_remote13.png

There is nothing in your folder now.
You can find "Download from" in the toolbar. (Tools-> Deployment-> Download from ...)

.. image:: ../_static/pycharm_remote14.png

Click this button and download all folders and data files from the mapped folder.
You can also click the "Sync with Deployed to ..." button to synchronize the mapped folder and working directory on your local host.

.. image:: ../_static/pycharm_remote15.png

Next, set up a python interpreter for your project.
Click Settings (Ctrl + Alt + S) in the File tab.

.. image:: ../_static/pycharm_remote16.png

Select the project interpreter below the project: <localhost_folder>.
Select your remote python via the drop-down menu.

.. image:: ../_static/pycharm_remote17.png