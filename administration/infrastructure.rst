##############################
Infrastructure
##############################

Add a Host
==========

To add a host:

#) Click on the *ADD* button.

   .. image:: /_static/imgs/common/btn_add_2.png

#) Follow the instructions displayed:

   .. image:: /_static/imgs/administration/infrastructure/add_host_2.png
       :width: 300

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
#) Click on the *AUTHORIZE* button. The status of host will be *Online*.

   .. image:: /_static/imgs/common/btn_authorize.png

   .. image:: /_static/imgs/administration/infrastructure/add_host_3.png
       :width: 480

Delete a Host
=============

To delete a host:

#) Select the host.
#) Click on the *DELETE* button.

   .. image:: /_static/imgs/common/btn_delete.png

#) Confirm the deletion.

Monitor a Host
==============

The host area displays the following real-time monitoring data:

* Status: host running status
* Compute: CPU utilization
* Memory: memory utilization
* GPU: GPU utilization
* Running tasks: number of running tasks

.. image:: /_static/imgs/administration/infrastructure/add_host_3.png
      :width: 480

A detailed real-time `Netdata <https://www.netdata.cloud/>`_ monitoring dashboard
is available by clicking on the links of host names.
A new browser window will be opened with the updated metrics for CPUs, memory, storage, and networking.

.. image:: /_static/imgs/administration/infrastructure/view_host_netdata_1.png
   :width: 600

Setup Multiple Hosts
====================

..
   TODO: HA
   High Availability
   =================

   failover case - shutdown a controller
