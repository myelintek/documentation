*************
Realese notes
*************

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
* Fix submit job modal view issue
* Fix error message 'Imagename' to 'Image name'
* Fix disk quota full Labs can not stop and start issue
* Fix create lab should display 'Out of GPU resource,...' when GPUs are unavailable
* Fix some Flavors filtering based on users plan at Labs setting and job submit pages
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

.. * Fix tensorboard buttons not automatically update
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

.. * Add lab/job disk space limitation
.. * Add lab/job cpu, memory and max-openfile to 65535 limitation
.. * Show available disk space in dataset page
.. * Simplified lab page

.. BugFixes
.. ++++++++

.. * Fix cookie timeout not redirect to logout page issue
.. * Fix auditlog timezone incorrect issue
.. * Fix lab attach dataset may error issue
.. * Fix job can't delete while in waiting state
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
.. * Fix auditlog shows duplicate stop lab/job messages
.. * Fix delete job with tensorboard opening cause system crash issue


.. v3.4.0
.. ======

.. Features
.. ++++++++

.. * Add augmentation template
.. * Refactor template yaml format, yaml file will sync with right panels parameters
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
.. * Confirm parameters when committing a job
.. * Parameter settings in a lab changed from YAML to Form
.. * Adjust project page layout
.. * [Classification template]: move tfrecord generation to training stage
.. * Add Iris Flower template
.. * Add admin API for list projects and tasks
.. * Custom log path for tensorboard
.. * Auto restart lab when attaching dataset

.. Bugfixes
.. ++++++++


.. * Fix Job output missing print messages issue
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
.. * Fix jobs elapse time incorrect issue.
.. * Fix jobs gpu limit incorrect issue.
.. * Fix jobs disappear issue
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
.. * Fix run job from default lab becoming error state
.. * Minor bugfixs

.. v3.2.0
.. ======

.. Features
.. ++++++++

.. * Auto stop Lab or Job while GPU in high temperature (90 celsius)
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

.. * Display elapsed and estimated time in job page
.. * Add tensorboard in job and lab pages
.. * Add example code for default jupyterlab page

.. Bugfixes
.. ++++++++


.. * Fix NFS mount affects fstab issue
.. * Fix can't stop lab/job issue
.. * Fix upload large amount of files hang issue
.. * Minor bugs fix

.. v3.0.0
.. ======

.. * Python3 version, refactor code.
.. * Introduce Lab, Job and templates.
.. * Fix dataset yolo annotations file works in relative path
.. * Add log_parser.py support for job metrics
.. * Add lab params syntax check
.. * In production mode
.. * Fix nfs not unmount when delete nfs dataset.





