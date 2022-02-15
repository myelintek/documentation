##############################
Infrastructure
##############################

Add a Host
----------

To add a host:

#) Click on the *ADD* button.

   .. image:: /_static/imgs/administration/infrastructure/add_host_1.png
       :width: 600

#) Follow the instructions displayed:

   .. image:: /_static/imgs/administration/infrastructure/add_host_2.png
       :width: 600
    
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
   
   .. image:: /_static/imgs/administration/infrastructure/add_host_3.png
       :width: 600

#) TODO: authorize

Delete a Host
-------------

To delete a host:

#) Select the host.
#) Click on the *DELETE* button.
#) Confirm the deletion.

.. image:: /_static/imgs/administration/infrastructure/del_host.png
    :width: 600

Monitor a Host
--------------

Setup Multiple Hosts
--------------------

High Availability
-----------------

failover case - shutdown a controller