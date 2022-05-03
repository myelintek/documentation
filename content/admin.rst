.. _admin:

**************
Administration
**************
After entering administration credentials in the login page, a *More* icon will apear in the left. Click it to see a popup window with different options for administration.

.. image:: ../_static/admin/popup.png
  :width: 400

Profile
=======

You can see current user profile and an option to change password.

.. image:: ../_static/admin/popup_profile.png
  :width: 400

.. image:: ../_static/admin/profile.png
  :width: 600

.. image:: ../_static/admin/change_password.png
  :width: 400

Account
=======

User
----

User managment tab allows creating, editing and deleting users.

Create
++++++

Click "Account" button.

.. image:: ../_static/admin/popup_users.png
  :width: 400

Click "Create" button.

.. image:: ../_static/admin/create_user.png

Fill username and password. Select single role from drop down list.

.. image:: ../_static/admin/create_user_modal.png
  :width: 400

Edit
++++

Select user that needs to be edited, click "Edit" button.

.. image:: ../_static/admin/edit_user.png

Fill new info. We decrease the sotrage limit from 2 to 1 GB.

.. image:: ../_static/admin/edit_user_modal.png
  :width: 400

Delete
++++++

Select user that needs to be deleted, click "Delete" button. Notice the change in the storage limit.

.. image:: ../_static/admin/delete_user.png

Confirm.

.. image:: ../_static/admin/delete_user_confirmation.png
  :width: 400


Dashboard
=========

Check various statistics about the system

.. image:: ../_static/admin/popup_dashboard.png
  :width: 400  

Task
----

Shows a list of currently running instances of labs.

.. image:: ../_static/admin/list_task.png

Stop
++++

Select the instance that needs to be stopped, and then click "Stop".

Only instances with running status can be stopped.

.. image:: ../_static/admin/stop_task.png

Delete
++++++

Select the instance to be deleted, and click "Delete" to delete the task.

Only not running instances can be deleted.

.. image:: ../_static/admin/delete_task.png

Project
-------

Project management tab. Shows list of projects.

.. image:: ../_static/admin/list_project.png

Create
++++++

Click create button.

.. image:: ../_static/admin/create_project.png

Fill project name and annotation, click "Create".

.. image:: ../_static/admin/create_project_modal.png
  :width: 400

Delete
++++++

Select needed project and click "Delete" button. Confirm.

.. image:: ../_static/admin/delete_project.png

Auditlog
--------

Log of system events in chronological order. Use "Search" box on top to look for specific events.

.. image:: ../_static/admin/auditlog.png

Device
======

Shows hardwave information of all hosts.

.. image:: ../_static/admin/view_device.png


Setting
=======

Host
----

Shows list of hosts in the system.

.. image:: ../_static/admin/list_host.png

Create
++++++

To add a new node to the system, click "Add" and follow shown instructions. Download the host agent installer to the machine you want to use as a host and run it.

.. image:: ../_static/admin/add_host.png
  :width: 600

Authorize
+++++++++

After successfull creation of a new host node, you should see it in the host list. However, you need to authorize it first for full operation.

.. image:: ../_static/admin/authorize_host.png
  :width: 600

Delete
++++++

Select needed host and click "Delete" button. Confirm.

.. image:: ../_static/admin/delete_host.png
  :width: 600

.. image:: ../_static/admin/delete_host_modal.png
  :width: 400

Flavor
------

Users can choose a flavor for their Labs, which corresponds to designating hardware resources

Create
++++++

To add a new flavor, click "Create"

.. image:: ../_static/admin/create_flavor.png

Choose the name, number of GPUs, their type, number of CPU cores, and memory for your new flavor, then click "Create".

.. image:: ../_static/admin/create_flavor_modal.png
  :width: 600

Edit
++++

To change preciously created flavor you need to first select the flavor you want to alter and click "Edit".

.. image:: ../_static/admin/edit_flavor.png

Choose what you want to change, we'll adjust the number of GPUs available to in this flavor.

.. image:: ../_static/admin/edit_flavor_modal.png
  :width: 600

Delete
++++++

To remove a flavor, select it and click "Delete"

.. image:: ../_static/admin/delete_flavor.png

Confirm your choice and proceed. 

.. image:: ../_static/admin/delete_flavor_modal.png
  :width: 400


Webhook
-------

Webhook is designed to help calculate system usage data. Webhook is triggered at the next events: lab stop/start/restart/delete.
Webhook sends POST request to the specified url containing data in the next format:

.. code-block:: python

  {
    'username': 'admin', 
    'timestamp': '2021-02-01 06:54:11.375141',
    'action': 'lab_start', 
    'uuid': 'u52ca065', 
    'flavor': "{
                  'id': 2, 
                  'name': 'micro', 
                  'cpu': 2, 
                  'gpu': 0, 
                  'gpu_type': 'Any', 
                  'memory': 2048, 
                  'cpu_lab': True, 
                  'info': '(vCPUs: 2, RAM: 2GB, GPU: 0)'
                }"
  }


To create webhook go to Settings Webhook page and press "Create".

.. image:: ../_static/admin/create_webhook.png

Enter desired url, include token if needed, press "Apply".

.. image:: ../_static/admin/create_webhook_modal.png

To delete webhook sellect checkbox and press "Delete". Than confirm action.
 
.. image:: ../_static/admin/delete_webhook.png


License
-------

Edit
++++++

Shows current license file.

If license needs to be updated click "Edit" to input new license file.

.. image:: ../_static/admin/license_system.png
  :width: 600

Input license text in the field and click "Save".

.. image:: ../_static/admin/license_system_modal.png
  :width: 600
