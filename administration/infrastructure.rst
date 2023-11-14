##############################
Infrastructure
##############################

Summary
=========

Infrastructure Host page shows overall summary of hardware resources including:

* Compute: total CPU cores usage of all online hosts
* Memory: total memory size usage of all online hosts
* GPU: total GPU cards usage of all online hosts
* Storage: total storage space usage for storing projects' data

   .. image:: /_static/imgs/administration/infrastructure/infra_dashboard.png
      :width: 700

Registry
========

A docker registry server is a centralized docker image management server.
It is required for multiple host clustering. It is optional for single host configuration.

To create the registry server, click *More* button next to the *Registry* and click *Create*.
Fill in *FQDN* and *port* of the registry server. Then click the *Create* button.

   .. image:: /_static/imgs/administration/infrastructure/infra_registry.png
      :width: 700

.. warning::
   Create or Remove the Registry service may obsolete existing Projects and should be
   performed in the beginning of the MLSteam deployment. Please consult administrators
   before any modification.

Datastore
=========

A datastore is for configuration a centralized storage space for storing Project data.
It is required for multiple host clustering. To create the datastore server, click
*More* button next to the *Datastore* and click *Create*. Choose one of Datastore type:

* local: launch the nfsv4 server on the master host and the local disk space for storage space
* nfs: connect to remote nfsv4 server and use the remote NFS space for storage space
* pure: connect to a Pure FlashBlade storage as storage space
* purefa: connect to a Pure FlashArray storage as storage space
* netapp: connect to a NetApp storage as storage space

   .. image:: /_static/imgs/administration/infrastructure/infra_datastore.png
      :width: 700


Detail Page
===========

The *Detail* button can switch to the page showing each host's current resource allocation.
Showing running *Tasks* on each host and the *type*, *name*, *username*, *up time* and
*occupied hardware resources* (CPU, Memory and GPUs)

   .. image:: /_static/imgs/administration/infrastructure/infra_detail_1.png
      :width: 700

   .. note::
      Administrators can stop running tasks by clicking the *stop* icon in the right side of the tasks

MIG Configuration
-----------------

MIG feature makes it possible to split a large data center GPU like A100 into
smaller GPUs that their memory, cache, and compute cores are completely isolated
from each other

To enable MIG, switch to the *Detail* page and click on the GPU you want to enable MIG.
Click on the *Enable Multi-Instance GPU* and choose a split policy from the menu.
Click *Update* to apply change.

   .. image:: /_static/imgs/administration/infrastructure/infra_mig.png
      :width: 700

.. note::
   MIG option only show up on supported GPU. No MIG feature GPU will not show MIG option 

Host
====

A host is a physical server managed by MLSteam.

Add a Host
----------

To add a host:

#) Click on the *ADD* button.

   .. image:: /_static/imgs/common/btn_add_2.png
      :width: 70

#) Follow the instructions displayed:

   .. image:: /_static/imgs/administration/infrastructure/add_host_2.png
       :width: 400

   #) Download the host agent installer.
   #) Copy the host agent installer to the host to add.
   #) Run the host agent installer on the host to add.

      .. code-block:: shell

         sudo bash mlsteam_agent_installer.sh

      .. note:: Replace the installer's file name with the actual one.

#) (Optional) After the installation is finished, you may check the logged messages.

   .. code-block:: shell

      sudo journalctl -f -u mlsteam_agent_xxx.xxx.xx.xx_xxxx.service

   .. note:: Refer to the end of the installer outputs for the actual `journalctl` command to run.

#) The host added will be in the list. Reload the page if the list has not been updated.
#) Click on the *AUTHORIZE* button.

.. image:: /_static/imgs/common/btn_authorize.png
   :width: 100

#) The status of host will be *Online*

.. image:: /_static/imgs/administration/infrastructure/add_host_3.png
   :width: 700

Delete a Host
-------------

To delete a host:

#) Select the host.
#) Click on the *DELETE* button.

   .. image:: /_static/imgs/common/btn_delete.png

#) Confirm the deletion.

Monitor a Host
--------------

The host area displays the following real-time monitoring data:

* Status: host running status
* Compute: CPU utilization
* Memory: memory utilization
* GPU: GPU utilization

   .. image:: /_static/imgs/administration/infrastructure/add_host_3.png
      :width: 700

A detailed real-time `Netdata <https://www.netdata.cloud/>`_ monitoring dashboard
is available by clicking on the links of host names.
A new browser window will be opened with the updated metrics for CPUs, memory, storage, and networking.

   .. image:: /_static/imgs/administration/infrastructure/view_host_netdata_1.png
      :width: 700

Host Tags
---------

Tags can be edited on each Host for restrict scheduling behavior by applying tags to the *Flavor*.
When a *Flavor* with some *Tags* been chosen for launching a *Lab*, only Hosts with *Tags* will
be selected for launching the Lab.

To edit the Host tags, select a Host and click the *Tag* button.
Type the tag name and click *Enter* to add a tag.

   .. image:: /_static/imgs/administration/infrastructure/infra_tag.png
      :width: 700

..
   TODO: multiple hosts
   Setup Multiple Hosts
   ====================

..
   TODO: HA
   High Availability
   =================

   failover case - shutdown a controller
