##############################
Infrastructure
##############################

Add a Host
----------

To ass a host:

#) Click on the *ADD* button.

   .. image:: /_static/imgs/administration/infrastructure/add_host_1.png
       :width: 600

#) Follow the instructions displayed.

   .. image:: /_static/imgs/administration/infrastructure/add_host_2.png
       :width: 600
    
   #) Download the host agent installer.
   #) Copy the host agent installer to the host to add.
   #) Run the host agent installer on the host to add.

      .. code-block: shell

         sudo bash mlsteam_agent_installer.sh
   
      Replace the installer's file name with the actual one.

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