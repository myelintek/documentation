*************
Release notes
*************

3.8.24
======

Feature
+++++++
* Show lab disk usage (#2334)
* Add labs status check in health API (#2350)

Bugfix
+++++++

* Fix auditlog show multiple stop while stopping labs (#2338)
* Fix agent installation error (#2339)
* Fix scheduler didn't recalculate resources after restart issue (#2340)
* Fix https certificate upgrade issue (#2343)
* Fix dataset upload file token timeout issue (#2345, #2349)
* Fix file extraction timeout issue (#2349)


3.8.23
======

Features
++++++++

* Admin device monitoring change to history metrics charts (#2278)
* Use NFSv4 for internal datastore service (#2293)
* Add system preserved resources info in admin/resources API (#2291)
* Add lab ssh feature for QC theme (#2328)
* Add AMD GPU detection support (#2299, experimental)
* Add MLFlow support (#2330, experimental)

BugFix
++++++

* Fix QC theme web title to 'QuantumCloud AI/ML' (#2280)
* Fix agent upgrade may fail due to pip issue (#2290)
* Fix vulnerability cve-2020-11022, cve-2020-11023 by upgrading jQuery from v3.4.1 to v3.6.0 (#2297)
* Fix ssh key auto download when page refresh issue (#2297)
* Fix vulnerability CVE-2016-10540, CVE-2019-10744, CVE-2020-8203, CVE-2018-16487, CVE-2019-10744, CVE-2020-1971, CVE-2021-3449, CVE-2021-28092 (#2301)
* Fix failed to manually create template from env.yml issue (#2307)
* Change API project delete and user delete to asynchronous, prevent API timeout and performance issue (#2292)
* Remove cuda dependency on MLSteam container (#2305)
* Fix error message no popup issue (#2318)
* Fix timeout issue for importing large docker image (#2320)
* Fix dataset delay in slowing directories issue (#2322)
* Fix users can see flavors event beyond their resource plan in terminal Lab page (#2321)
* Fix dataset file disappear issue (#2332)
* Refactor Dockerfile, separate build and install into two stages; Fetch templates from Internet (#2333)


v3.9.20
=======

Features
++++++++

* Upgrade netdata to 1.29.0 (#2234)
* Add system reset (cleanup) button (#2226)
* Auto-configure features based on license content (#2228)
* Add 'document_url' parameter in mlsteam.ini (#2232)
* Support connecting 3rd party Harbor as registry server (#2222)
* Remember login users during system restart (#2216)

Bugfix
++++++

* Fix unable to mount no password CIFS issue (#2239)
* Remove image information from Lab page on QC theme (#2233)
* UI change for QC theme (#2235)
* Fix fail to mount purestorage NFS issue (#2230)
* Auto install nvidia driver if kernel upgraded (#2224)
* Secure minio default user as read-only user (#2223)


v3.8.19
=======

Feature
+++++++

* Add user notification page for standard version of MLSteam (#2206)
* Add stop GPU Lab warning for non-reserved plan users if there are CPU Labs running (#2198)

Bugfix
++++++

* Popup warning when clicking SSH keygen button if the Lab has no sshd service (#2212)
* Fix webhooks send the Lab stop events twice issue (#2208)
* Fix 'server_path' error when deleting a user account (#2204)
* Add default log rotation for CVAT service (#2211)
* Fix permission check for dataset file extraction API (#2200)
* Fix Lab cannot start issue when the disk quota full (#2199)
* Improve API query speed (#2197)
* Fix project image list cannot loading issue triggered by image builder naming (#2196,#2184)
* Fix stress testing failed to start lab if vcpu larger than 2 (#2192)
* Fix Lab dataset dynamic update during collaboration (#2193,#2186)
* Remove change password for user authenticated from LDAP (#2191,#2187)


v3.8.18
=======

Feature
+++++++

* Support Active Directory authentication (#2183)
* API for personal pop up message notification (#2179)

Bugfix
++++++

* Remove about and logout for QC theme (#2190)
* Fix license update issue (#2178)
* Fix container limitation no applied issue (#2142)


v3.8.16
=======

Feature
+++++++

N/a

Bugfix
++++++

* Project image list not updated when uploaded or deleted images (#2106)
* Fix agent version API error handling (#2118)
* Fix running labs cannot been connected after system upgraded (#2104)
* Fix resources not reclaim during stress testing (#2090)
* Fix building Dockerfile shows image_tag undefined (#2109)
* Fix Labs stuck at INIT due to CVAT services issue (#2086)


v3.8.15
=======

Feature
+++++++

* Fix webhooks message format
* Add version in license file
* Add force GPU option in plan to force users to use the CPU lab along with GPU labs (#2081)
* Optimize CPU training performance by CPU affinity (#2087)

Bugfix
++++++

* Fix LDAP login disconnect from server issue (#2083)
* Improve project page performance (#2096)


v3.8.13
=======

Feature
+++++++

* Add YOLOv4 template
* Add squash warning and cleaning if the Lab image layers exceed 110 layers
* Change default image to python-gpu:16.01, add machine-learning-tutorials code

Bugfix
++++++

* change system out of resource and user reached limits warning messages
* Fix web page loading fonts issue and icons moving issue
* Remove deprecated templates, data-augmentation, cross validation templates.
* Update code in templates for YOLOv3, pytorch-cifar10 and classification
* Fix cluster init error (#2031)
* Fix Nginx config issue (#2026)
* Fix agent may disconnect with master issue


v3.8.12
=========

Feature
+++++++

* support maintenance redirect url
* support non-stop upgrade

Bugfix
++++++

* fix warning message wording
* fix naming rules wording
* fix mount cifs/nfs issue
* add uid in LDAP setting (#2020)

v3.8.10
=======

Feature
+++++++
* Add GPU alias in admin panel. (#1966)
* Add lab proxy for Rest API service (#1968)
* Support MIG config in mlsteam_agent.ini (#1982)
* Dataset support Samba/cifs as external storage (#1984)
* Change Lab dataset attach path from 'mlsteam/input' to 'mlsteam/data' (#1944)
* User login to home page for poject list instead of current project page (#1989)
* Add Lab/Project/Image naming rules in each create dialog (#1991)
* Upload docker saved images to projects (#1993)

Bugfix
++++++

* Fix dataset tooltips not show issue
* Fix quantumcloud theme error messages
* Fix admin tasks dashboard not show num_gpu
* Sort project list from new to old order
* Change overview 'Finish' tasks to 'Stopped'
* Fix repository create failed issue


v3.8.8
======


Features
++++++++

* Upgrade CVAT to 1.1.0

BugFixes
++++++++

* Fix theme change issue
* Solve problem that EXEC process left in container (#1917)
* Fix Flavor check fail when user with preserved plan want to change flavor for lab


v3.8.7
======


Features
++++++++

* option to preserve(booking) resources for users
* support user data migration (export/import)

BugFixes
++++++++

* fix api query tasks return 'NonType' has no serialize issue
* fix lab terminal wont show if re-open browser


v3.8.6
======

BugFixes
++++++++

* Fix terminal lab cannot update flavor issue
* Fix CVAT can not restart issue


v3.8.5
======


BugFixes
++++++++

* Fix files download name with dataset uuid as prefix
* Fix project members can not restart lab issue


v3.8.4
======

Features
++++++++

* Multiple file selection for dataset files upload

BugFixes
++++++++

* Fix out of resource message
* Fix special characters issue during dataset files extraction


v3.8.3
======

Features
++++++++

* add dataset downloader

BugFixes
++++++++

* change dataset name length up to 40 characters
* fix lab terminal support over https
* fix error handling when the agent initialization failed
* fix agent installer can not get ip addresses for bonding interfaces


v3.8.2
======

Features
++++++++

* Change create lab flavor name to GPU numbers on QCI theme

BugFixes
++++++++

* Fix stop lab response success but actually failed issue
* Fix error message 'Imagename' to 'Image name'
* Fix disk quota full Labs can not stop and start issue
* Fix create lab should display 'Out of GPU resource,...' when GPUs are unavailable
* Fix dataset extract zip file with unknown character sets
* Fix certificates backup and restore issue
* Fix disable buttons when uploading files are selected


v3.8.1
======

Features
++++++++

* Add flavor and plan for tasks and users resource allocations
* Add user account and billing URLs in mlsteam.ini config options
* Add Lab create with terminal option
* Add port forward option in terminal labs
* Add dataset files uploading cancel button

BugFixes
++++++++

* Fix dataset button has to toolip issue
* Fix certificate files not backup issue
* Fix https redirect to http issue
* Fix labs may occupy double resources when users click start and stop buttons quickly
* Fix dataset create with invalid characters issue

.. v3.6.1
.. ======


.. Features
.. ++++++++

.. * Refactor dataset page
.. * Make lab ssh, dockerfile build and CVAT configurable in admin page
.. * Add home page for project

.. BugFixes
.. ++++++++

.. * Close commit & run menu when click 'start'
.. * Fix image list page sometime shows 404 error
.. * Fix i18n translations
.. * Fix pie chart shows running tasks
.. * Bugfixes


.. v3.6.0
.. ======


.. Features
.. ++++++++

.. * UI/UX refactoring
.. * Add user storage space quota setting
.. * Add create/update timestamp in image table
.. * Add # of gpu setting when click "commit & run" in lab page
.. * Upport attaching multiple datasets in a lab


.. v3.5.2
.. ======

.. BugFixes
.. ++++++++

.. * Fix usage time api


.. v3.5.1
.. ======

.. BugFixes
.. ++++++++

.. * Fix time zone issue for query user usage API
.. * Fix can't delete image issue
.. * Security fixes


.. v3.5.0
.. ======

.. Features
.. ++++++++

.. * Show available disk space in dataset page
.. * Simplified lab page

.. BugFixes
.. ++++++++

.. * Fix cookie timeout not redirect to logout page issue
.. * Fix auditlog timezone incorrect issue
.. * Fix lab attach dataset may error issue
.. * Fix certificate doesn't backup issue


.. v3.4.2
.. ======

.. Features
.. ++++++++

.. * Add calculate users usage time API

.. BugFixes
.. ++++++++

.. * Fix MLSteam upgrade nginx not reload issue
.. * Fix frequently login system cause instability issue
.. * Add saving state in Lab when stopping, fix stop/restart timeout issue
.. * Add repository create timeout issue
.. * Fix https certificate won't automatically renew issue


.. v3.4.1
.. ======

.. BugFixes
.. ++++++++

.. * Fix entry.ipynb not found issue
.. * Fix MLSteam service startup failed issue (wtforms upgrade)
.. * Fix public dataset permission error for normal users issue
.. * Fix error when mlsteam.yml missing param_definition field
.. * Fix restart Lab looks like hanging issue


.. v3.4.0
.. ======

.. Features
.. ++++++++

.. * Add augmentation template
.. * Add dockerfile build page in project
.. * Add system restart button for administration
.. * Add fullscreen button in labs
.. * Make lab in full page
.. * Add datasets overview in admin dashboard

.. BugFixes
.. ++++++++

.. * Fix device info doesn't show issue
.. * Fix project table overlap issue
.. * Fix background color in project member setting dropdown list


.. v3.3.2
.. ======

.. Features
.. ++++++++

.. * Launch lab can choose no GPU environment
.. * Better ssh config layout at Lab

.. BugFixes
.. ++++++++

.. * fix right menu at lab collapse issue
.. * fix host status incorrect issue when host changed IP
.. * fix duplicated docker images in projects


.. v3.3.1
.. ======

.. Features
.. ++++++++

.. * add auditlog api
.. * lab dataset changed to dropdown list

.. Bugfixes
.. ++++++++

.. * fix certificate expire date
.. * fix nfs delete files issue when using NFSv4


.. v3.3.0
.. ======

.. Features
.. ++++++++

.. * Image management per project  
.. * Save Labs environment when stop/restart a lab
.. * Self hosted image repository (optional)
.. * User groups management
.. * Adjust project page layout
.. * [Classification template]: move tfrecord generation to training stage
.. * Add Iris Flower template
.. * Add admin API for list projects and tasks
.. * Auto restart lab when attaching dataset

.. Bugfixes
.. ++++++++


.. * Fix cancel uploading datasets issue
.. * Fix labs crash if yaml file format incorrect issue
.. * Fix blank when loading lab page issue
.. * Fix elapsed time start from waiting issue
.. * Fix NFS cannot delete issue
.. * Fix jupyterlab header hidden issue
.. * minor bug fixes

.. v3.2.2
.. ======

.. Features
.. ++++++++

.. * session expire extends from 1hour to 5 hours

.. Bugfixes
.. ++++++++


.. * Fix unclick gpu limit check not working issue.
.. * Fix can't find hostid for licensing issue

.. v3.2.1
.. ======

.. Features
.. ++++++++

.. * Add certificate setting page in admin page

.. Bugfixes
.. ++++++++

.. * Show clear NFS mount error message
.. * Fix create user without roles defined error
.. * Minor bugfixs

.. v3.2.0
.. ======

.. Features
.. ++++++++

.. * Refactor top-right menu
.. * Admin role and developer role become exclusive. Admin role users can do same things as developer role.

.. v3.1.1
.. ======

.. Features
.. ++++++++

.. * Add owner in system tasks list
.. * Add GPU and Disk monitor
.. * Add Chinese language

.. Bugfixes
.. ++++++++

.. * Fix jupyterlab starts in blank screen issue
.. * Fix allocated GPU unreleased issue

.. v3.1.0
.. ======

.. Features
.. ++++++++

.. * Add example code for default jupyterlab page

.. Bugfixes
.. ++++++++


.. * Fix NFS mount affects fstab issue
.. * Fix upload large amount of files hang issue
.. * Minor bugs fix

.. v3.0.0
.. ======

.. * Python3 version, refactor code.
.. * Fix dataset yolo annotations file works in relative path
.. * Add lab params syntax check
.. * In production mode
.. * Fix nfs not unmount when delete nfs dataset.





