#########
Workspace
#########

.. note::
    This section is about an advanced feature accessible in :ref:`VC projects <core-concept-vc-project>`.

A :ref:`workspace <core-concept-workspace>` is a special kind of :ref:`folder <core-concept-folder>` accessible in :ref:`VC projects <core-concept-vc-project>`
that is version controlled and is mounted automatically in VC :ref:`labs <core-concept-lab>`.
In addition to normal folder operations, workspace supports synchronizing with upstream (*remote*) services.

Each project member has their workspace. A workspace for the project owner is created during project creation.
Other project members may :ref:`create their own workspace <create-workspace>` on demand.

.. _create-workspace:

Create a Workspace
==================

To create w workspace:

#) Click on the *Create Workspace* button in the workspace page.

    .. image:: /_static/imgs/user/workspace/create_workspace_1.png
        :width: 700

#) Click on the *Create* button in the confirmation dialog and wait for checking out data.

    .. image:: /_static/imgs/user/workspace/create_workspace_2.png
        :width: 700

Pull Changes from Upstream
==========================

To synchronize changes from upstream services, click on the *Pull* button.

    .. image:: /_static/imgs/user/workspace/pull_upstream_1.png
        :width: 300

Push Changes to Upstream
========================

To synchronize changes to upstream services:

#) Click on the *Push* button.

    .. image:: /_static/imgs/user/workspace/push_upstream_1.png
        :width: 300

#) Check the changes and fill in the commit message.

    .. image:: /_static/imgs/user/workspace/push_upstream_2.png
        :width: 700

#) Click on the *OK* button.

View Upstream info
==================

.. note::
    Workspace simplifies interacting with the upstream servers.
    You can use workspace without knowing the information here.

    Upstream info is useful if you need to manage data by yourself in other places.

To view upstream service info, click on the *Upstream Info* button.

    .. image:: /_static/imgs/user/workspace/view_upstream_info_1.png
        :width: 300

* The *Gitlab* tab shows the access information and commands to clone from the `Git <https://git-scm.com/>`_ remote service.

    .. image:: /_static/imgs/user/workspace/view_upstream_info_2.png
        :width: 300

* The *DVC* tab shows the access information and commands to configure the `DVC <https://dvc.org/>`_ remote service.

    .. image:: /_static/imgs/user/workspace/view_upstream_info_3.png
        :width: 300
