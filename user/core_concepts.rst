###################
Core Concepts
###################

Project
    A :doc:`project <project>` is a collection of all artificats in developing ML models.
    A project consists of :ref:`folder <core-concept-folder>`,
    :ref:`labs <core-concept-lab>`,
    :ref:`pipelines <core-concept-pipeline>`,
    :ref:`tracks <core-concept-track>`,
    :ref:`models <core-concept-model>`,
    :ref:`WebApps <core-concept-webapp>`,
    :ref:`templates <core-concept-template>`, and
    :ref:`images <core-concept-image>`.

.. _core-concept-folder:

Folder
    A :doc:`folder <folder>` is a collection of data organized in files and directories.
    Files in folder, like dateset, could be used in labs for model training and validation.

.. _core-concept-lab:

Lab
    A :doc:`lab <lab>` is a Web IDE (based on `JupyterLab <https://jupyter.org/>`_ with MLSteam's add-on functionalities) that organizes files and datasets.
    You may design ML models and make experiments in a lab.
    When the development is done, you may convert a lab into a :doc:`template <template>`
    for reuse in other labs, :ref:`pipelines <core-concept-pipeline>` or deployment.

.. _core-concept-pipeline:

Pipeline
    A :doc:`pipeline <pipeline>` is a repeatable procedure consisting of actions for running ML tasks.
    You may define a pipeline for a subset of common ML tasks.
    You may even define an end-to-end pipeline to fulfill `MLOps <https://en.wikipedia.org/wiki/MLOps>`_ that
    retrains and evaluates the model for new model designs or dataset
    and finally deploys the ML application to an experimental or production site.

.. _core-concept-track:

Track
    A :doc:`track <track>` keeps various results of ML training or experiments,
    including the parameters, metrics, console logs, and any logged files or data.
    It also enables visualization of the results with *TensorBoard*.

.. _core-concept-model:

Model
    A :doc:`model <model>` is a collection of files that record a trained ML model.

.. _core-concept-webapp:

WebApp
    A :doc:`WebApp <webapp>` enables deployment of a Web-based ML applications in a simple way.
    Services for project users may also be provided as a WebApp.

.. _core-concept-template:

Template
    A :doc:`template <template>` is a creator of a
    :doc:`lab <lab>`, :doc:`pipeline action <pipeline>`, or :doc:`WebApp <webapp>`
    with predefined programs, datasets, models, or other settings.

.. _core-concept-image:

Image
    An image (Docker image) is used to create a :ref:`template <core-concept-template>`.
    In MLSteam, an image could be obtained from a user uploaded Docker image file,
    a remote registry, or an MLSteam-managed registry.

Flavor
    A flavor describes how many hardware resources (such as CPUs, GPUs, and memory) are to be allocated.
