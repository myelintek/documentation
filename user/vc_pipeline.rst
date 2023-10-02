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
  ``needs`` specify the dependent steps.
  A step is considered ready to run if all the dependent steps are completed.
  It is defined in either way below

  * **Null**:
    A ``null`` value specifies no dependent steps.
    Such a step will be the first one to execute in a workflow.
    A workflow should contain **exactly one** step with null dependency.
  * **Previous step**:
    A ``pre`` value specifies the dependency of the preceding step in the list.
  * **Dependent steps**:
    An array of all dependent steps specified by the step names (case-insensitive).
    All mentioned steps should be defined before this step in the list.

  .. note::
    Requiring all dependencies should be pre-defined not only simplifies the parser
    but also ensures the steps to have a chronological order and thus they form a
    `directed acyclic graph <https://en.wikipedia.org/wiki/Directed_acyclic_graph>`_ (DAG).

* Step-specific properties

.. note::
  To simplify the demonstration, the examples in the following step elements will
  only contain step-specific properties and a subset of other step properties.
  **Complete step specification** is required in writing a workflow file.

.. _vc-workflow-spec-step-checkout:

Checkout Step
~~~~~~~~~~~~~

A checkout step (with type ``checkout``) checkouts contents from version control services.
It is a dictionary defining:

* **Git**:
  ``git`` specifies checking out from a git repository.
  By default, it checks out from
  
  * the same git ref (a branch, tag, or commit) specified in checking out the VC workflow file, and
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
      By default, it checkouts the ``main`` (or falls back to ``master``) branch.

* **DVC**:
  ``dvc`` specifies checking out from the DVC remote.
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
      ``targets`` specify an array of DVC checkout targets.
      By default, all tracked data from DVC will be targeted during DVC checkout.
      This option is to narrow down the DVC targets to checkout and only meaningful when DVC checkout happens.
      A DVC target could be a *path to a file* or a *directory within workspace*.
      When a directory is provided, all included files or directories will be recursively checked out.

* **Location**:
  ``location`` specifies the checkout location, a path relative to workspace directory.
  By default, it is the workspace directory itself.

This simplest form checks out files from the same git ref in the associated git repository
and from all the tracked files from the DVC remote.

.. code-block:: yaml

  type: checkout

This checks out files from the git ``release`` branch
and from the tracked files under the ``data`` directory from the DVC remote.
The files are saved under the ``<WORKSPACE>/src`` directory.

.. code-block:: yaml

  type: checkout
  git: release
  dvc:
    targets: ["data"]
  location: src

.. _vc-workflow-spec-step-docker-run:

Docker-Run Step
~~~~~~~~~~~~~~~

A docker-run step (with type ``docker_run``) runs commands in a Docker container.
It is a dictionary defining:

* **Image**: 
  ``image`` specifies the docker image tag to run container.
  It is ommitable if ``defaults.image`` is provided.

  .. note::

    * If :ref:`MLSteam-managed image registry <core-concept-image>` is enabled,
      the image should exist in the registry and specified with the registry prefix,
      such as ``${MLSTEAM_IMAGE_REGISTRY}/namespace/image:tag``
      (see `built-in pipeline variables <vc-workflow-builtin-vars>`_).
    * Otherwise, the image could be any valid image tag accessible in project.

* **Flavor** (*no variable substitution*):
  ``flavor`` specifies the MLSteam flavor (case-insensitive) to run container.
  It is ommitable if ``defaults.flavor`` is provided. Flavors do not support variable.

  .. _vc-workflow-spec-property-flavor:

* **Folders**:
  ``folders`` specify the :ref:`MLSteam folders <core-concept-folder>` to mount.
  It is an array of folders with each item defined in either way below

  * **Folder name only**:
    ``<folder_name>`` specifies mounting a folder beloning to the current project
    at ``/mlsteam/data/<folder_name>``.
  * **Full folder settings**:
    ``<folder_name>:<mount_path>`` specifies mounting a folder beloning to the current project
    at the specified mount path.

* **Run** (*required*):
  ``run`` specifies the commands to run. POSIX shell (*/bin/sh*) is used to run the commands.

This prepares data for model training, assuming the requirments file
and the preprocessing script are available through a previous checkout step.

.. code-block:: yaml

  type: docker_run
  image: python:3.8
  flavor: micro
  folders: ["my-coco128"]
  run: |
    pip3 -r requirements.txt
    python3 preproc.py "/mlsteam/data/my-coco128"

This retrains a model with an image in MLSteam-managed image registry, assuming the
relavant files are available through a previous checkout step.

.. code-block:: yaml

  type: docker_run
  image: ${MLSTEAM_IMAGE_REGISTRY}/pytorch:1.8
  flavor: medium
  run: |
    python3 train.py

.. _vc-workflow-spec-step-template-run:

Template-Run Step
~~~~~~~~~~~~~~~~~

A template-run step (with type ``template_run``) runs tasks from an MLSteam :ref:`template <core-concept-template>`.
It is a dictionary defining:

* **Task name**:
  ``task_name`` specifies the task name.
  By default, the name is derived from the pipeline name and step name,
  which is stable among pipeline executions if the pipeline settings remain unchanged.
* **Force remove** (*no variable substitution*):
  ``force_remove`` is a boolean value specifying removing existing task(s) with the same task name.
  By default, it is ``true``.
* **Template** (*required*):
  ``template`` specifies the template to run. It is a dictionary defining:

  * **Name** (*required*):
    ``name`` specifies the template name.
  * **Version**:
    ``version`` specifies the template version. By default, it is the latest version.
  * **Type**:
    ``type`` specifies the template type. It does not support variable substitution.
    Currently, the only valid value is ``webapp``.

* **Parameters**:
  ``params`` specifies the parameters to run template.
  It is a dictionary whose keys are parameter names and values are parameter values.
  Formats for various parameter types:

  * **Simple types** (*string*, *integer*, *float*, *boolean*, and *enum*):
    Fill in the values directly.
  * **Model type**:
    A model-type parameter is a dictionary defining:

    * **Name or id** (*required*):
      Either ``name`` or ``id`` is required to specify the :ref:`model <core-concept-model>`.
    * **Version** (*required*):
      ``version`` specifies the model version. Only plaintext model versions are supported.
    * **Mount point** (*required*):
      ``mountPoint`` specifies the model mount path, E.g., ``/working``.

* **Flavor** (*no variable substitution*):
  ``flavor`` specifies the MLSteam flavor (case-insensitive) to run the task.
  It is ommitable if ``defaults.flavor`` is provided. Flavors do not support variable.
* **Ports** (*no variable substitution*):
  ``ports`` specify the network ports to access the task.
  It is an array of ports with each item defined in either way below

  * **Internal port only**:
    ``<internal_port_number>`` specifies a system-assigned public port associated with a specific internal port.
  * **Full port settings**:
    ``<internal_port_number>:<public_port_number>`` specifies a user-assigned public port associated with a apecific internal port.

  .. note::
    Specifiying an internal port not covered in template may be skipped in some templates.

* **Folders**:
  ``folders`` specify the :ref:`MLSteam folders <core-concept-folder>` to mount.
  Refer to `folders <vc-workflow-spec-property-flavor>`_ in docker-run step for more detail.

Variable Substitution
---------------------

Source of Variables
~~~~~~~~~~~~~~~~~~~

1. User-defined pipeline :ref:`variables <vc-workflow-spec-vars>`.

  .. _vc-workflow-builtin-vars:

2. MLSteam built-in pipeline variables

  * ``${MLSTEAM_IMAGE_REGISTRY}``: URL prefix for the :ref:`MLSteam-managed image registry <core-concept-image>`
  * ``${MLSTEAM_PIPELINE_EXECUTION_ID}``: pipeline execution ID
  * ``${MLSTEAM_BUILD_TIME}``: alias for ``${MLSTEAM_BUILD_TIME_UTC}``
  * ``${MLSTEAM_BUILD_TIME_UTC}``: build time (UTC) in ``YYYYmmddHHMMSS`` format, such as ``202307051730``

Scope of substitution
~~~~~~~~~~~~~~~~~~~~~

1. These step properties have no variable substitution:

  * ``name``, ``type``, and ``needs``

2. Other step properties basically have variable substitution unless it is explicitly excluded in specification.

Substitution rules
~~~~~~~~~~~~~~~~~~

1. Substitution is specified by ``$SUBSTITUTION_IDENTIFIER`` or ``${SUBSTITUTION_IDENTIFIER}``.
   A substitution-identifier is a variable name (case-sensitive)
   or the ones defined by `special substitution <vc-workflow-special-substitution>`_.
2. **Literal substitution**:
   Substitution is done before step execution.
   During step execution, only the substitions are seen rather than the variable names.

   .. _vc-workflow-special-substitution:

3. **Special substitution**:

   * Only supported in brace substitution form ``${SUBSTITUTION_IDENTIFIER}``.
   * For a user-defined pipeline variable ``VAR_X`` of **folder type**:

     * ``${VAR_X}`` will be subsituted for the folder name.
     * ``${VAR_X.NAME}`` will be subsituted for the folder name (same as ``${VAR_X}``).

   * For a user-defined pipeline variable ``VAR_X`` of model_version type:

     * ``${VAR_X}`` will be subsituted for ``<model_name>:<model_version_name>``.
     * ``${VAR_X.MODEL_NAME}`` will be subsituted for the model name.
     * ``${VAR_X.VERSION_NAME}`` will be subsituted for the model version name.
