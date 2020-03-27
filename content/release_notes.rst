*************
Realese notes
*************
V3.3.0
======

Features
++++++++

    * Image management per project  
    * Save Labs environment when stop/restart a lab
    * Self hosted image repository (optional)
    * User groups management
    * Confirm parameters when committing a job
    * Parameter settings in a lab changed from YAML to Form
    * Adjust project page layout
    * [Classification template]: move tfrecord generation to training stage
    * Add Iris Flower template
    * Add admin API for list projects and tasks
    * Custom log path for tensorboard
    * Auto restart lab when attaching dataset

Bugfixes
++++++++


    * Fix Job output missing print messages issue
    * Fix cancel uploading datasets issue
    * Fix labs crash if yaml file format incorrect issue
    * Fix blank when loading lab page issue
    * Fix elapsed time start from waiting issue
    * Fix NFS cannot delete issue
    * Fix jupyterlab header hidden issue
    * minor bug fixes

V3.3.2
======

Features
++++++++

    * session expire extends from 1hour to 5 hours

Bugfixes
++++++++


    * Fix unclick gpu limit check not working issue.
    * Fix jobs elapse time incorrect issue.
    * Fix jobs gpu limit incorrect issue.
    * Fix jobs disappear issue
    * Fix can't find hostid for licensing issue

V3.2.1
======

Features
++++++++

    * Add certificate setting page in admin page

Bugfixes
++++++++


    * Show clear NFS mount error message
    * Fix create user without roles defined error
    * Fix run job from default lab becoming error state
    * Minor bugfixs

V3.2.0
======

Features
++++++++

    * Auto stop Lab or Job while GPU in high temperature (90 celsius)
    * Refactor top-right menu
    * Admin role and developer role become exclusive. Admin role users can do same things as developer role.

V3.1.1
======

Features
++++++++

    * Add owner in system tasks list
    * Add GPU and Disk monitor
    * Add Chinese language

Bugfixes
++++++++

    * Fix jupyterlab starts in blank screen issue
    * Fix allocated GPU unreleased issue

V3.1.0
======

Features
++++++++


    * Display elapsed and estimated time in job page
    * Add tensorboard in job and lab pages
    * Add example code for default jupyterlab page

Bugfixes
++++++++


    * Fix NFS mount affects fstab issue
    * Fix can't stop lab/job issue
    * Fix upload large amount of files hang issue
    * Minor bugs fix

V3.0.0
======

    * Python3 version, refactor code.
    * Introduce Lab, Job and templates.
    * Fix dataset yolo annotations file works in relative path
    * Add log_parser.py support for job metrics
    * Add lab params syntax check
    * In production mode
    * Fix nfs not unmount when delete nfs dataset.





