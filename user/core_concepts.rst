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
    You may even define an end-to-end pipeline to fulfill `MLOps <https://en.wikipedia.org/wiki/MLOps>`_ that automatically
    retrain the model on changes of the model design and finally deploy the ML application to a staging or production site.

Track
    TODO: track

Model
    TODO: model

WebApp
    TODO: WebApp

Template
    A template is an example of a lab with a specific type of DNN model with an already preloaded dataset connected to it. Serves as an example or template for users.

Flavor
    A flovor is the hardware settings for a Lab or a Job, describes how much resources (CPUs, GPUs) are allocated.

Image
    Docker image management with portus.