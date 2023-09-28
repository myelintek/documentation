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
It is a dict defining:

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

.. _vc-workflow-spec-step-checkout:

Checkout Step
~~~~~~~~~~~~~

.. _vc-workflow-spec-step-docker-run:

Docker-Run Step
~~~~~~~~~~~~~~~

.. _vc-workflow-spec-step-template-run:

Template-Run Step
~~~~~~~~~~~~~~~~~


Variable Substituion
--------------------
