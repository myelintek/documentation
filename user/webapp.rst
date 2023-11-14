#########
WebApp
#########

A WebApp enables deployment of a Web-based ML applications in a simple way.
Services for project users may also be provided as a WebApp.

For example, the *YOLOv5 Inference* WebApp detects the objects and their boundaries
in a user-provided image.

.. image:: /_static/imgs/user/webapp/view_web_app_2.png
    :width: 700

Create a WebApp
===============

To create a WebApp:

#) In the WebApp page, click on the *NEW* button.
#) Select the WebApp template.
#) Fill in the settings.

    .. note::

        The settings vary with the selected template.

        For example, the *YOLOv5 Inference* template has settings for
        the WebApp name, flavor, bind port, WebApp protocol, and model.
        *YOLOv5 Inference* requires a model containing a weights file
        named *yolov5.pt* in the model's root directory.

        .. image:: /_static/imgs/user/webapp/add_webapp_1.png
            :width: 480

#) Click on the *CREATE* button.

To access a WebApp:

#) Start the WebApp if it has not been in the *Running* state.
#) Click on the *open* button.

    .. image:: /_static/imgs/user/webapp/view_web_app_1.png
        :width: 480

#) The WebApp will be opened in a new tab or window.

Webapp Static Port
--------------------

When creating a Webapp, exposed port number can be specified by user. Please reference to the
:ref:`Yolov7 Tutorial <tutorial_yolov7_training>` for more detail example.

    .. image:: /_static/imgs/user/webapp/webapp_bind_port.png
        :width: 700


Create a Compose Webapp
=======================

#) Create a Docker compose template

    * Create those files and upload to a empty folder:

        * docker-compose.yml

            .. code-block::

                services:
                  web: 
                    build:
                      context: .
                      target: builder
                    stop_signal: SIGINT
                    ports:
                      - '${PORT}:8000'


        * Dockerfile

            .. code-block::

                FROM --platform=$BUILDPLATFORM python:3.10-alpine AS builder
                WORKDIR /app
                RUN --mount=type=cache,target=/root/.cache/pip \
                    pip3 install flask
                COPY app.py /app
                ENTRYPOINT ["python3"]
                CMD ["app.py"]
                FROM builder as dev-envs
                RUN <<EOF
                apk update
                apk add git
                EOF
                RUN <<EOF
                addgroup -S docker
                adduser -S --shell /bin/bash --ingroup docker vscode
                EOF
                # install Docker tools (cli, buildx, compose)
                COPY --from=gloursdocker/docker / /


        * app.py

            .. code-block::

                from flask import Flask
                app = Flask(__name__)
                @app.route('/')
                def hello():
                        return "Hello World!"
                if __name__ == '__main__':
                        app.run(host='0.0.0.0', port=8000)


        * .env

            .. code-block::

                PORT=${web_port}

#) Click "*NEW*" and then "*From composed*" button on template page

    .. image:: /_static/imgs/user/webapp/compose_template_1.png
        :width: 480

#) Fill in the Name and Version
#) Click the "*+*" button

    .. image:: /_static/imgs/user/webapp/compose_template_2.png
        :width: 480

#) We can see the Folder list of this project, double Click the one we just created.

    .. image:: /_static/imgs/user/webapp/compose_template_3.png
        :width: 480

#) The "*Save Path*" only available if current path contains any file with ".yml" ".yaml" extension.
#) Click the "*Save Path*", go back the form and the yaml files are listed.

    .. image:: /_static/imgs/user/webapp/compose_template_4.png
        :width: 480

#) Choose the needed yaml file, in this case, is "*docker-compsoe.yml*", just click the "*+*" in tail of the row. If you want to check the content, just click "*...*" in the content column.
#) The .env file show in the Step.3 section, and you can edit it.

    .. image:: /_static/imgs/user/webapp/compose_template_5.png
        :width: 480

#) Arguments in .env will list in the "*Parameters*" section autocompletely.
#) The URL Parameters is a extra link for website, input "http://${IP}:${web_port}", IP is a placeholder value and will be replaced by host IP address .
#) Click "*Create*" button to create a compose webapp task.

    .. image:: /_static/imgs/user/webapp/compose_template_6.png
        :width: 480

#) Go Webapp Page, Click the "*New*" button, and choose the template just created.

    .. image:: /_static/imgs/user/webapp/compose_webapp_1.png
        :width: 480

#) Fill in the Name and web_port, click "*Create*", the web_port must specify a free port.

    .. image:: /_static/imgs/user/webapp/compose_webapp_2.png
        :width: 480

#) Webapp is running now, and click the external link button will go to the website.

    .. image:: /_static/imgs/user/webapp/compose_webapp_3.png
        :width: 480

#) Click detail button will see the log and ternimal console.

    .. image:: /_static/imgs/user/webapp/compose_webapp_4.png
        :width: 480

#) The website page

    .. image:: /_static/imgs/user/webapp/compose_webapp_5.png
        :width: 480


Delete a WebApp
===============

To delete a WebApp:

#) Click on the *stop* button if the WebApp is still in the *Running* state.

    .. image:: /_static/imgs/user/webapp/stop_webapp.png
        :width: 480

#) Click on the *delete* button.

    .. image:: /_static/imgs/user/webapp/del_webapp.png
        :width: 480

Webapp Detail
=============

Once you create a running webapp, you can click the Webapp and view the log and login to the terminal Interface

    .. image:: /_static/imgs/user/webapp/webapp_detail.png
        :width: 700


Setup Label Studio
==================

`Label Studio <https://labelstud.io/>`_ is a data annotation tool,
available as a WebApp in MLSteam. To setup Label Studio:

#) :ref:`Create a project-scoped folder <create-and-manage-project-scoped-folder>`,
   ``yolo-sample`` as example here, and add an ``output`` directory in the folder.

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_1.png
        :width: 700

#) Create a Label Studio WebApp with folder ``yolo-sample``

    * Mount folder: ``yolo-sample``

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_2.png
        :width: 480

#) Open the Label Studio WebApp.
#) Create a new account with your email address and a new password.

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_3.png
        :width: 480

#) Click on the *Create Project* button.
#) In the dialog, fill in the following fields, and click on the *Save* button:

    * Project name tab:

        * Project name: the project name
        * Description: a brief description (optional)

        .. image:: /_static/imgs/user/webapp/setup_labelstudio_4.png
            :width: 480

    * Labeling setup tab:

        * Select *Object Detection with Bounding Boxes*.
        * Define the labels.

        .. image:: /_static/imgs/user/webapp/setup_labelstudio_5.png
            :width: 480

        .. image:: /_static/imgs/user/webapp/setup_labelstudio_6.png
            :width: 480

#) In the project page, click on the *Settings* button.

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_7.png
        :width: 700

#) In the *Cloud Storage* section, click on the *Add Source Storage* button.

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_8.png
        :width: 700

#) In the dialog, fill in the following fields, and click on the *Add Storage* button.

    * Storage type: ``Local files``
    * Storage title: a storage title (optional)
    * Absolute path: path to the images to label
      (for the *yolo-sample* dataset, this would be ``/data/ds1/training_data/yolo/images``)
    * File filter regex: image file filter in regular expressions (optional)
      (for the *yolo-sample* dataset, this would be ``.*jpg``)
    * Treat every bucket object as a source file: ``enabled``

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_9.png
        :width: 480

#) Back to the project settings page, click on the *Sync Storage* button.

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_10.png
        :width: 700

#) Back to the project main page by clicking on the top navbar.

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_11.png
        :width: 480

#) Select an image to label, add the bounding boxes for the corresponding classes,
   and click on the *Submit* button.

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_12.png
        :width: 700

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_13.png
        :width: 700

#) Repeat the previous step until all the images are labelled.
#) Back to the project settings page, click on the *Add Target Storage* button.

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_14.png
        :width: 700

#) In the dialog, fill in the following fields, and click on the *Add Storage* button.

    * Storage type: ``Local files``
    * Storage title: a storage title (optional)
    * Absolute local path: the output path created in the mounted project-scoped folder
      (For example, ``/data/output``)

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_15.png
        :width: 480

#) Back to the project settings page, click on the *Sync Storage* button.

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_16.png
        :width: 700

#) Back to the folder page, the labelling data will be saved in the output directory.

    .. image:: /_static/imgs/user/webapp/setup_labelstudio_17.png
        :width: 700

Setup CVAT
==========

`CVAT <https://cvat.org/>`_ is a data annotation tool,
available as a WebApp in MLSteam. To setup CVAT:

#) :ref:`Create a project-scoped folder <create-and-manage-project-scoped-folder>`

#) Create a CVAT WebApp from template.

    .. image:: /_static/imgs/user/webapp/setup_cvat_1.png
        :width: 700

#) Input name and select desired folder from the dropdown, then press "Create". Notice default credentials.

    .. image:: /_static/imgs/user/webapp/setup_cvat_2.png
        :width: 700

#) When the webapp is running press "External link" button to open CVAT.

    .. image:: /_static/imgs/user/webapp/setup_cvat_3.png
        :width: 700
    
    .. note::
        While CVAT status is running it might take few minutes for system to fully setup and create accaunt.
        You can check start up progress by checking the logs

    .. image:: /_static/imgs/user/webapp/setup_cvat_9.png
        :width: 700
    
    .. image:: /_static/imgs/user/webapp/setup_cvat_8.png
        :width: 700


#) In the CVAT tab input default credentials ``admin/cvat@mlsteam``
#) Press "Create new task" button
#) Fill the task creation form fields. To use project dataset for annotation click "Connected file share" expand directory tree and sellect needed files.


    .. image:: /_static/imgs/user/webapp/setup_cvat_4.png
        :width: 700

    .. warning::
        Don't include ``.cvat`` directory. It will result in error.

#) Open task after submit

    .. image:: /_static/imgs/user/webapp/setup_cvat_5.png
        :width: 700

#) Open job

    .. image:: /_static/imgs/user/webapp/setup_cvat_6.png
        :width: 700

#) Do the labeling (labeling process is not covered here)

#) To use annotations, download them first then unzip and upload annotation file to MLSteam dataset. To download unnotations press "Menu"->"Dump annotations" then select desired format.

    .. image:: /_static/imgs/user/webapp/setup_cvat_7.png
        :width: 700
