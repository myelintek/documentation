###############
Account
###############

Create and Manage a User
------------------------

#) Click on the *CREATE* button.
#) Fill in the user settings:

    * Name: displayed name
    * Account: login account name
    * Password: login password
    * Role: could be `Admin` (system maintainer) or `Developer` (deep learning developer)
    * Plan: resource limitation plan for running the user's owning labs

        .. note:: Select the `Unlimited` plan to disable resource limitation.

    * Storage Limit: storage usage limitation for running the user's owning labs in GB

        .. note:: Set `0` to disable storage usage limitation
        
#) Click on the *CREATE* button.

    .. image:: /_static/imgs/administration/account/add_user_1.png
        :width: 600

Set Plan for Resource Limitation
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Delete a User
-------------

To delete a user:

#) Select the user to delete.
#) Click on the *DELETE* button.

.. warning::
    On deleting a user:
    
    #) That user's access to all projects will be removed.
    #) All projects owned by that user will be deleted.

Integrate LDAP/AD
-----------------

To enable remote user authentication schemes, set up the corresponding LDAP or AD servers here.

.. image:: /_static/imgs/administration/account/init_ldap_ad.png
    :width: 600

LDAP
~~~~

To set up LDAP authentication:

#) Click on the *LDAP* button.
#) Fill in the settings fields.
#) Click on the *Test Server* button.

.. image:: /_static/imgs/administration/account/setup_ldap_1.png
    :width: 600

TODO: LDAP

AD
~~~

TODO: AD

