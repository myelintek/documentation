###################
Core Concepts
###################

Project
    A :doc:`project <project>` is a collection of all works when you develop DNN models. You can launch either a Jupyter lab (we call them labs) or launch experiments and training iterations (we call them jobs) will be kept and organized.

Dataset
    A :doc:`dataset <dataset>` is a collection of data organized in files and directories.
    Dataset files could be used in labs for model training and validation.

Lab
    A :doc:`lab <lab>` is a Web IDE (based on `JupyterLab <https://jupyter.org/>`_ with MLSteam's add-on functionalities) that organizes files and datasets.
    You may design ML models and make experiments in a lab.
    When the development is done, you may convert a lab into a :doc:`template <template>` for reuse in other labs, :ref:`pipelines <core-concept-pipeline>` or deployment.

.. _core-concept-pipeline:

Pipeline
    A :doc:`pipeline <pipeline>` is a repeatable procedure consisting of actions for running ML tasks.
    You may define a pipeline for a subset of common ML tasks.
    You may even define an end-to-end pipeline to fulfill `MLOps <https://en.wikipedia.org/wiki/MLOps>`_ that
    retrains and evaluates the model for new model designs or dataset
    and finally deploys the ML application to an experimental or production site.

Track
    A :doc:`WebApp <webapp>` enables deployment of a Web-based ML applications in a simple way.

Model
    TODO: model

WebApp
    A :doc:`WebApp <webapp>` enables deployment of a Web-based ML applications in a simple way.

Template
    A :doc:`template <template>` is a creator of a
    :doc:`lab <lab>`, :doc:`pipeline action <pipeline>`, or :doc:`WebApp <webapp>`
    with predefined programs, datasets, models, or other settings.

Flavor
    A flovor is the hardware settings for a Lab or a Job, describes how much resources (CPUs, GPUs) are allocated.

Image
    Docker image management with portus.