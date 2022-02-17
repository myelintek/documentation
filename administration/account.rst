###############
Account
###############

Create and Manage a User
------------------------

#) Click on the *CREATE* button.
#) Fill in the user settings:

    * Name: the displayed name
    * Account: the login account name
    * Password: the login password
    * Role: could be `Admin` (system maintainer) or `Developer` (deep learning developer)
    * Plan: resource limitation plan

        .. note:: Select the `Unlimited` plan to disable resource limitation.

    * Storage Limit: storage usage limitation in GB

        .. note:: Set `0` to disable storage usage limitation
        
        TODO: what kind of storage limitation?
        
#) Click on the *CREATE* button.

    .. image:: /_static/imgs/administration/account/add_user_1.png
        :width: 600

    FIXME: update image

Set Plan for Resource Limitation
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Delete a User
-------------

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

