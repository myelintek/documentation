###########
Marketplace
###########

A number of useful services could be installed in marketplace.

.. image:: /_static/imgs/administration/marketplace/view_marketplace.png
    :width: 600

* To install a service, click on the *INSTALL* button for the service.

    .. image:: /_static/imgs/administration/marketplace/add_service_1.png

* To customize a service, click on the *VIEW* button for the service.

    .. image:: /_static/imgs/administration/marketplace/set_service_1.png

* To delete a service, click on the *REMOVE* button for the service.

GitLab
======

TODO: default settings, such as username and password for administrator

Basic settings:

* FQDN: fully qualified domain name, or IP address (along with port number)
* Port: TODO: desc
* Web port: port number for the Web server

.. _gitlab-ldap-settings:

LDAP settings:

* FQDN: URL for accessing the LDAP server with the `ldap` or `ldaps` protocol
* Port: port number for the LDAP server
* Base DN: distinguished name (DN) for search base
* Bind DN: distinguished name (DN) for the user making queries
* Password: password for the user making queries
* Filter: query filter
* UID: locating the user record given the user name

HedgeDoc
========

Basic settings:

* FQDN: fully qualified domain name, or IP address (along with port number)
* Port: TODO: desc
* Web port: port number for the Web server

Refer to the GitLab setction for :ref:`LDAP settings <gitlab-ldap-settings>`.

OpenLDAP
========

Basic settings:

* FQDN: fully qualified domain name, or IP address (along with port number)
* Port: TODO: desc
* Web port: port number for the Web server
* Account: distinguished name (DN) for the administrator
* Password: password for the administrator
