###########
Marketplace
###########

Some useful plugins could be installed in marketplace. A plugin provides additional 3rd party 
software(s) to enrich MLSteam features.

.. image:: /_static/imgs/administration/marketplace/view_marketplace.png
    :width: 700

Install and Uninstall
=====================

* To install a service, click on the **Install** button for the service.
* To view or update a service, click on the **View** button for the service.
* To uninstall a service, click on the **Remove** button for the service.

    .. image:: /_static/imgs/administration/marketplace/view_marketplace_2.png
        :width: 700

VC Project
==========

This plugins includes **GitLab** and **SeaweedFS** services. Both services
has to be installed together to enable *Version Control* (VC) Project features

GitLab
------

Basic settings:

* HOST_FQDN: fully qualified domain name, or IP address (along with port number)
* SSH_PORT: port number for the GitLab ssh service
* HTTP_PORT: port number for the Web server

.. _gitlab-ldap-settings:

LDAP settings (optional):

* LDAP_FQDN: URL for accessing the LDAP server with the *ldap* or *ldaps* protocol
* LDAP_PORT: port number for the LDAP server
* LDAP_BASE: distinguished name (DN) for search base
* LDAP_BIND_DN: distinguished name (DN) for the user making queries
* LDAP_PASSWORD: password for the user making queries
* LDAP_FILTER: query filter
* LDAP_UID: locating the user record given the username

SeaweedFS
---------

Basic settings:

* FQDN: URL for accessing the SeaweedFS interface
* Host Data Dir: directory for storing object files
* Master Http Port: port number for the web port
* Master GRPC Port: port number for the GRPC port
* Volume Size Limit (MB): limitation for a single volume size in SeaweedFS
* S3 Http Port: port number for s3-compatible API interface
* S3 Admin User: account name for s3 authentication
* S3 Admin Secret: secret for s3 authentication


HedgeDoc
========

Basic settings:

* FQDN: fully qualified domain name, or IP address (along with port number)
* Port: port number for the HedgeDoc service
* Web port: port number for the Web server

Refer to the GitLab section for :ref:`LDAP settings <gitlab-ldap-settings>`.

OpenLDAP
========

Basic settings:

* FQDN: fully qualified domain name, or IP address (along with port number)
* Port: port number for the OpenLDAP service
* Web port: port number for the Web server
* Account: distinguished name (DN) for the administrator
* Password: password for the administrator

Mirror
======

Our plugin offers a robust solution for installing Python packages from the Python Package Index (PyPI) and Debian packages (DEBs) in an offline environment. This is especially useful in scenarios where internet access is restricted.

**Introduction:**

- **PyPI (Python Package Index):** PyPI is a repository of software packages for the Python programming language. It provides a vast collection of Python libraries and tools that developers can easily install using tools like `pip`. However, in some environments, direct internet access may be restricted, making it challenging to install packages from PyPI.

- **DEBs (Debian Packages):** DEBs are software packages used by Debian-based Linux distributions, such as Ubuntu. They contain pre-compiled software that can be easily installed on compatible systems. Our plugin supports the installation of DEBs for various Ubuntu versions, including "xenial," "bionic," "focal," and "jammy."

**Using the Plugin:**

To make the installation of these packages feasible in an offline environment, our plugin provides the following features:

1. **Local Package Mirror Service:** This service allows you to install Python packages and DEBs even without internet access.

2. **Package Organization:** For Python packages (PyPI), you can add packages in the form of `.whl` files. These files should be placed in the `/whl` folder. If the folder doesn't exist, you can create it.

    .. image:: /_static/imgs/administration/marketplace/browse_pypi.png
        :width: 700

3. **Support for Ubuntu Versions:** DEB packages are organized based on different Ubuntu version numbers. Currently, our plugin supports four Ubuntu versions: "xenial" "bionic" "focal" and "jammy". If the folder doesn't exist, you can create it.

    .. image:: /_static/imgs/administration/marketplace/browse_deb_pool.png
        :width: 700

    .. image:: /_static/imgs/administration/marketplace/browse_deb_focal.png
        :width: 700

4. **Package Metadata Update:** After adding additional packages to the respective folders, you can click the "Scan and Update" button. This action updates the package mirror metadata, ensuring that your offline environment stays up to date with the latest packages.

By using our plugin, you can seamlessly manage and install Python and DEB packages in offline environments, streamlining your development and deployment processes.

    .. image:: /_static/imgs/administration/marketplace/scan_and_update.png
        :width: 700