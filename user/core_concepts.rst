###################
Core Concepts
###################

Project
    A :doc:`project <project>` is a collection of all works when you develop DNN models. You can launch either a jupyterlab (we call them labs) or launch experiments and training iterations (we call them jobs) will be kept and organized.

Dataset
    A :doc:`dataset <dataset>` is any collection of data. You can organize your data into different directories (we call dataset) and modify datasets by web portal. You can preview images and upload/download dataset files on dataset pages. All datasets can be used in your labs.

Lab
    A :doc:`lab <lab>` is a web IDE (based on JupyterLab) organized on a container basis. You can develop DNN models in a lab and start training in the same lab or create another training container (we call job) for keeping records.

Flavor
    Is the hardware setting for a Lab or a Job, describes how much resources (CPUs, GPUs) are allocated.

Template
    A template is an example of a lab with a specific type of DNN model with an already preloaded dataset connected to it. Serves as an example or template for users.

Image
    Docker image management with portus.

TODO: terms for the new UI