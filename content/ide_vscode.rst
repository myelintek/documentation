.. _ide_vscode:

VSCode
======

Step by step tutorial to setup VSCode for a lab


Install VSCode
-----------------

Download VSCode that according to your operating system from following link

https://code.visualstudio.com/Download

.. image:: ../_static/remote_ide/vscode/vscode-install.gif

Click downloaded file to install VSCode.


Install extenstions in VSCode
--------------------------------

Search and install extension for remote SSH

.. image:: ../_static/remote_ide/vscode/vscode-ssh.gif


SSH key and SSH config
-----------------------

Open someone lab you want to remote in brower. Make sure the lab is running, click SSH tab in right navbar and generate SSH conifg.

Download the ssh private key by clicking sshkey link

.. note:: In the Linux operating system, you need to change the sshkey file to 600 mode.

.. image:: ../_static/remote_ide/sshkey.jpg

Copy the ssh config by clicking copy icon on top right of the config

.. image:: ../_static/remote_ide/copyconf.jpg

.. note:: Windows10 accept both / and \ as path separator


Paste ssh config in VSCode
-----------------------------

Open remote explorer in VSCode. Click configure in ssh targets. 

Paste the copied ssh config to ssh config in VSCode. Save the config file and click refresh button in the ssh targets.

.. image:: ../_static/remote_ide/vscode/vscode-sshconfig.gif


Connect to remote lab
-------------------------

Click created ssh target to connect to remote lab

.. image:: ../_static/remote_ide/vscode/vscode-connect.gif

.. note:: if there is an error while connecting, try to remove *know_hosts* file in .ssh folder


Open remote folder
---------------------

Once connected to remote lab, open remote folder in left column to browse files

.. image:: ../_static/remote_ide/vscode/vscode-openfolder.gif


Edit in VSCode
-----------------

You can open console in VSCode and upload/download files in left column.

.. image:: ../_static/remote_ide/vscode/vscode-edit.gif


You can visit VSCode website to find out more extensions supported by VSCode!

https://code.visualstudio.com/docs/editor/extension-gallery

