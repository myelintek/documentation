.. _image:

************
Docker Image
************

Each user can manage his/her own docker images in the image page. User saved images are private
which can only seen by the user itself, unless the image is tagged under group namespaces and all users in the same group share the images.



List Image
===========

Click the **Image** botton in a project, the image list table shows all available container images.

.. image:: ../_static/image/list_image.png

Delete Image
============

Click the trash icon of the image you want to delete.

.. image:: ../_static/image/delete_image.png

Save Image
==========

In the lab page, you can save the lab environment as an image.
Click "Save as" button in a running lab and type-in image name to store the image.

.. figure:: ../_static/image/save_as.png
  :width: 400

  click save as image button


.. figure:: ../_static/image/save_image.png
  :width: 400

  type-in image name


.. note:: 
    Image name must be valid ASCII, lowercase, uppercase letters, digits, underscores, periods and dashes.

Build Image
============

Following steps show you how to upload a dockerfile to build your own image

Enable docker build config
----------------------------

Login as administrator.
Click "Setting".

.. image:: ../_static/image/dockerfile_1.png
  :width: 400

Click "Config".
Tick the docker_build checkbox.

.. figure:: ../_static/image/dockerfile_2.png

  Click *Edit* to change value

.. figure:: ../_static/image/dockerfile_3.png
  :width: 600
  Update value

.. figure:: ../_static/image/dockerfile_4.png

  Check the result


Create a DockerFile
--------------------

In this step, you write a Dockerfile that builds a Docker image.

For example, create a file named Dockerfile and paste the following:

.. code-block:: bash

  FROM nvcr.io/nvidia/tensorflow:18.08-py3
  RUN pip3 install jupyterlab
  RUN rm -rf /usr/lib/x86_64-linux-gnu/libcuda.so /usr/lib/x86_64-linux-gnu/libcuda.so.1 /tmp/*
  WORKDIR /mlsteam/lab
  CMD ["bash", "-c", "source /etc/bash.bashrc && jupyter notebook --notebook-dir=/tf --ip 0.0.0.0 --no-browser --allow-root"]


Build DockerFile
-------------------

If you want to upload your own dockerfile and build it into an image. Click the "Add" button inside image list, then click "Builder".

.. image:: ../_static/image/dockerfile.png

Type the image name and select dockerfile in your file system.

.. image:: ../_static/image/dockerfile_modal.png

System will start building dockerfile once you click submit.

.. image:: ../_static/image/new_image1.png

If the build is successfull, the image will be given an ID and saved locally.

.. image:: ../_static/image/new_image2.png

You can view the building log message by clicking the image file icon.


.. figure:: ../_static/image/dockerfile_version.png

  dockerfile with same image name will be grouped

The contents of the dockerfile used to build the image are shown in the *Dockerfile* tab 

.. image:: ../_static/image/dockerfile_content.png

Load Image File
================

Upload tar file to the dataset of your choice. 

.. image:: ../_static/image/upload_tar.PNG

Click the "Add" button inside image list, then click "Load".

.. image:: ../_static/image/load_image.png

Type prefered image tag. Type image path. Path format is the following: <username>/<dataset name>/<path in dataset>, 
ex: admin/to_build/hello-world.tar

.. image:: ../_static/image/load_image_modal.PNG

Wait for image to appear on the list (might take some time for a bigger images).

.. image:: ../_static/image/load_image_list.png


Push & Pull Image
==================

Following steps show how to manage project images from your PC
Your PC has to install docker for managing images from command.

If your PC is Windows, install the Docker Desktop

Install Docker Desktop
----------------------

Docker Desktop for Windows is Docker designed to run on Windows 10.

**System Requirements**


- Windows 10 64-bit: Pro, Enterprise, or Education (Build 15063 or later).
- Hyper-V and Containers Windows features must be enabled.
- The following hardware prerequisites are required to successfully run Client Hyper-V on Windows 10:
    - 64 bit processor with Second Level Address Translation (SLAT) 4GB system RAM
    - BIOS-level hardware virtualization support must be enabled in the BIOS settings. For more information, see Virtualization.

You can get Docker Desktop on Windows from following link.

https://hub.docker.com/editions/community/docker-ce-desktop-windows/

.. image:: ../_static/image/install.png

Legacy desktop solution. Docker Toolbox is for older Mac and Windows systems that do not meet the requirements of Docker Desktop for Mac and Docker Desktop for Windows. We recommend updating to the newer applications, if possible.

You can get Docker Toolbox on Windows from following link:

https://docs.docker.com/toolbox/toolbox_install_windows/

Double-click Docker for Windows Installer to run the installer.

When the installation finishes, Docker starts automatically. The whale in the notification area indicates that Docker is running, and accessible from a terminal.


Please add insecure registry. Edit daemon.json for Linux OS.

Add insecure registry
------------------------

Add the following contents in the ``daemon.json`` file, whose default location is ``/etc/docker/daemon.json`` on Linux or ``C:\ProgramData\docker\config\daemon.json`` on Windows Server. If you use Docker Desktop for Mac or Docker Desktop for Windows, click the Docker icon, choose Preferences, and choose +Daemon.

An example for Linux:

.. code-block:: bash

  vim /etc/docker/daemon.json


.. code-block:: bash

  {
      "insecure-registries" : ["<domain.sample.com>:<port>"]
      ,"runtimes": {
          "nvidia": {
              "path": "nvidia-container-runtime",
              "runtimeArgs": []
          }
      }
  }

.. image:: ../_static/image/daemon_example.png


Substitute the address of your insecure registry for the one in the example.

.. note:: 
    You can find the registry address in Project -> Image page.

Remember to restart Docker for the changes to take effect.

.. code-block:: bash

  systemctl restart docker


Login registry
--------------

Turn on a terminal and login to registry.

.. code-block:: bash

    sudo echo "cT6Xi2Ajcgs32M96QswD" | docker login <domain.sample.com>:<port> -u admin --password-stdin

.. note::
    You can find out access_token in profile page.

.. image:: ../_static/image/access_token.png

.. image:: ../_static/image/login.png

Pull image from the project
----------------------------

Your access_token can only pull images if you are project member.

Pull the image we just uploaded. 

.. image:: ../_static/image/new_image2.png

.. code-block:: bash

    docker pull 192.168.0.12:9101/91388126/test_dockerfile:latest

.. image:: ../_static/image/pull.png

You can also pull the public image, hello-world.

.. image:: ../_static/image/pull_helloworld.png

Push image to the project
--------------------------

Tag image name under the project id namespace if you want to push the image to the project.

.. code-block:: bash

    docker tag hello-world:latest 192.168.0.12:9101/91388126/hello-world:latest

.. image:: ../_static/image/tag_image.png

Then, push the image.

.. code-block:: bash

    docker push 192.168.0.12:9101/91388126/hello-world

.. image:: ../_static/image/push_helloworld.png

You will see the image shown in the project image list.

.. image:: ../_static/image/push_success.png

Download Image
================

Here show you how to download docker image from NGC (nvidia gpu cloud)

Step 1. click Pull button on your Image page

.. image:: ../_static/image/image_pull1.png


Step 2. put full docker image path in Image Link input and the image name you want (including namespace, name and tag)

.. image:: ../_static/image/image_pull2.png

.. note:: 
    Image namespace could be your project uuid, your account name, or your group name

System will start pulling the image. You can see the image in the create lab page once the image downloaded.

.. image:: ../_static/image/image_pull3.png


Tag Image
===========

Once you downloaded an image, you may want to share the image with other users.
Here shows you the steps to share your image with other users in the same group

Step 1. admin should already created a group and add you and other users in the same group. 
You will see groups you have joined in the Group page. ex. objectdetection group
Click the group name to see members in the group

.. image:: ../_static/image/usergroup1.png

Step 2. in the Image page, click tag button of the image you want to share, type the image name with the group as namespace
ex. objectdetection/pytorch:21.06-py3

.. image:: ../_static/image/groupimage1.png

Now you will see the image in both `admin` and `objectdetection` namespaces. Other users in the objectdetection group will be able to use the image.

.. image:: ../_static/image/groupimage2.png
