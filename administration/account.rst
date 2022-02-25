###############
Account
###############

Create and Manage a User
========================

The *User* tab lists the registered MLSteam users.

* Name: displayed name
* Account: login account
* Password: login password
* Role: user role. Could be *Admin* (system maintainer) or *Developer* (deep learning developer)
* Plan: resource limitation plan for running the user's owning labs
* From: account type. Could be *MLSteam* (managed by MLSteam), *LDAP* (managed by LDAP), or *AD* (managed by AD)

.. image:: /_static/imgs/administration/account/view_users.png
    :width: 600

To create a user:

#) Click on the *CREATE* button.
#) Fill in the user settings:

    * Name: displayed name
    * Account: login account
    * Password: login password
    * Role: could be *Admin* (system maintainer) or *Developer* (deep learning developer)
    * Plan: resource limitation plan for running the user's owning labs

        .. note::
            Select the *Unlimited* plan to disable resource limitation.

    * Storage Limit: storage usage limitation for running the user's owning labs in GB

        .. note::
            Set ``0`` to disable storage usage limitation
        
#) Click on the *CREATE* button.

    .. image:: /_static/imgs/administration/account/add_user_1.png
        :width: 300

To edit a user:

#) Select the user to edit.
#) Click on the *EDIT* button.
#) Change the user settings.
#) Click on the *SAVE* button.

To delete a user:

#) Select the user to delete.
#) Click on the *DELETE* button.

.. warning::
    On deleting a user:
    
    #) That user's access to all projects will be removed.
    #) All projects owned by that user will be deleted.

Set Plan for Resource Limitation
--------------------------------

Integrate LDAP/AD
=================

To enable remote user authentication schemes, set up an LDAP or AD server here.

.. image:: /_static/imgs/administration/account/init_ldap_ad.png
    :width: 600

To set up LDAP authentication:

#) Click on the *LDAP* button.
#) Fill in the settings fields.
#) Click on the *SUBMIT* button.

    .. image:: /_static/imgs/administration/account/setup_ldap_1.png
        :width: 600

To set up AD authentication:

TODO: AD

.. note::
    #) You could set up either *LDAP* or *AD* (but not both) for remote authentication.
    #) A remote authenticated user is listed in the *User* tab only after it had logged in MLSteam.