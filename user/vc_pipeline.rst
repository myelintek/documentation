###########
VC Pipeline
###########

.. note::
    This section is about an advanced :ref:`pipeline <core-concept-pipeline>` feature
    accessible in :ref:`VC projects <core-concept-vc-project>`.
    Refer to the :doc:`Pipeline <pipeline>` section for the pipeline feature
    in :ref:`basic projects <core-concept-project>`.

Define a Pipeline
=================

A VC pipeline is defined by a workflow file under the ``.mlsteam-ci`` directory in the VC source repository.
A workflow file is a YAML file with the format specified in `VC Workflow File`_.

VC Workflow File
================

The VC workflow file is a `YAML <http://yaml.org/>`_ file defining:

* `Format <vc-workflow-spec-format>`_ (*required*)
* `Name <vc-workflow-spec-name>`_ (*required*)
* `Variables <vc-workflow-spec-vars>`_
* `Defaults <vc-workflow-spec-defaults>`_
* `Steps <vc-workflow-spec-steps>`_ (*required*)

.. _vc-workflow-spec-format:

Format
------

The top-level ``format`` property specifies the workflow file spec version.
Currently, the only valid value is ``v0.1``.

.. _vc-workflow-spec-name:

Name
----

The top-level ``name`` property specifies the workflow name.

.. _vc-workflow-spec-vars:

Variables
---------

The top-level ``vars`` property specifies the workflow variables to use in steps.
It is an array of variable with each item defining:

* **Name** (*required*):
  ``name`` specifies the variable name, used as variable substitution identifier (case-sensitive).
* **Type** (*required*):
  ``type`` specifies the variable type, should be one of ``string``, ``folder``, or ``model_version``.
* **Label**:
  ``label`` specifies the variable label displayed in UI. By default, it has the same value of name.
* **Default**:
  ``default`` specifies the default variable value. By default, it is ``null``.
  The formats for different variable types:

  * String type: a string
  * Folder type: a folder name
  * Model-version type: ``<model_name>:<model_version>``

.. code-block:: yaml

    name: ds_train
    type: folder
    label: Training dataset
    default: yolo-sample

.. code-block:: yaml

    name: attribute_model
    type: model_version
    default: "face:v1"

.. _vc-workflow-spec-defaults:

Defaults
--------

The top-level ``defaults`` property specifies the workflow default settings.
It is a dictionary defining:

* **Image**:
  ``image`` specifies the default image to run a container.
  By default, it is a Ubuntu-based image with
  `mlsteam-client <https://pypi.org/project/mlsteam-client/>`_,
  `mlseam-model-sdk <https://pypi.org/project/mlsteam-model-sdk/>`_,
  `Python 3 <https://www.python.org/>`_,
  and some common Linux commands pre-installed.
* **Flavor**:
  ``flavor`` specifies the default name of flavor (case-insensitive) to run a container.

.. _vc-workflow-spec-steps:

Steps
-----

The top-level ``steps`` property specifies the workflow steps.
It is an array of steps with each item defining:

* **Name** (*required*):
  ``name`` specifies a case-insensitive unique step name, which will be shown in the execution page.
* **Type** (*required*):
  ``type`` specifies the step type, which should be one of:

  * ``checkout`` for `checkout steps <vc-workflow-spec-step-checkout>`_
  * ``docker_run`` for `docker-run steps <vc-workflow-spec-step-docker-run>`_
  * ``template_run`` for `template-run steps <vc-workflow-spec-step-template-run>`_

* **Needs** (*required*):
  ``needs`` specifies the depedent steps.
  A step is considered ready to run if all the dependent steps are completed.
  It is defined in either way below

  * **Null**:
    A ``null`` value specifies no dependent steps.
    Such a step will be the first one to execute in a workflow.
    A workflow should contain **exactly one** step with null dependency.
  * **Previous step**:
    A ``pre`` value species the dependency of the preceding step in the list.
  * **Dependent steps**:
    An array of all dependent steps specified by the step names (case-insensitive).
    All mentioned steps should be defined before this step in the list.

  .. note::
    Requiring all dependencies should be pre-defined not only simplifies the parser
    but also ensures the steps to have a chronological order and thus they form a
    `directed acyclic graph <https://en.wikipedia.org/wiki/Directed_acyclic_graph>`_ (DAG).

* Step-specific properties

.. note::
  To simplifiy the demonstration, the examples in the following step elements will
  only contain step-specific properties and a subset of other step properties.
  **Complete step specification** is required in writing a workflow file.

.. _vc-workflow-spec-step-checkout:

Checkout Step
~~~~~~~~~~~~~

A checkout step (with type ``checkout``) checkouts contents from version control services.
It is a dictionary defining:

* **Git**:
  ``git`` specifies checking out from a git repository.
  By default, it check outs from
  
  * the same git ref (a branch, tag, or commit) specified in checking out the VC workflow file
  * the git repository associated with the current VC project.

  It is defined in either way below

  * **Git ref only**:
    A string value specifies the git ref (a branch, tag, or commit)
    from the git repository associated with the current VC project.
  * **Full git settings**:
    A dictionary defining:

    * **Git repo** (*required*):
      ``repo`` specifies the git repository url.
      Currently, only public git repositories are supported.
    * **Git ref**:
      ``ref`` specifies the git ref to checkout.
      By default, it checkous the ``main`` (or falls back to ``master``) branch.

* **DVC**:
  ``dvc`` species checking out from the DVC remote.
  It is defined in either way below

  * **Enable DVC only**:
    A string value specifies whether to checkout from the DVC remote.
    Its value should be one of

    * ``auto`` (*default*):
      It specifies checking out from the DVC remote iff it's under a VC project.
    * ``yes``:
      It specifies always checking out from the DVC remote.
    * ``no``:
      It specifies never checking out from the DVC remote.
      This option is useful when you only need the source code
      but don't want to download lots of data from the DVC remote.

  * **Full DVC settings**:
    A dictionary defining

    * **Enable DVC**:
      ``enable`` specifies whether to checkout from the DVC remote.
      Refer to the previous section for the valid values.
    * **DVC targets** (*required*):
      ``targets`` specifies an array of DVC checkout targets.
      By default, all tracked data from DVC will be targeted during DVC checkout.
      This option is to narrow down the DVC targets to checkout and only meaningful when DVC checkout happens.
      A DVC target could be a *path to a file* or a *directory within workspace*.
      When a directory is provided, all included files or directories will be recursively checked out.

* **Location**:
  ``location`` species the checkout location, a path relative to workspace directory.
  By default, it is the workspace directory itself.

This simplest form checks out files from the same git ref in the associated git repository
and from all the tracked files from the DVC remote.

.. code-block:: yaml

  type: checkout

This checks out files from the git ``release`` branch
and from the tracked files under the ``data`` directory from the DVC remote.
The files are saved under the ``$WORKSPACE/src`` directory.

.. code-block:: yaml

  type: checkout
  git: release
  dvc:
    targets: ["data"]
  location: src

.. _vc-workflow-spec-step-docker-run:

Docker-Run Step
~~~~~~~~~~~~~~~

.. _vc-workflow-spec-step-template-run:

Template-Run Step
~~~~~~~~~~~~~~~~~


Variable Substituion
--------------------
