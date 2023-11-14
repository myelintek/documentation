############################################
Log
############################################

Activities
==========

The *Activities* tab lists the logged auditlog record. A record includes the following information:

#) Time stamp: log create time
#) Level: logging level
#) User: username (for a user log) or *SYSTEM* (for a system log)
#) Type: log type, could be *User* (user log) or *System* (system log)
#) Message: log message

The log could be filtered by entering the search terms, log level and log user.
How many log records were show per page can be configured by a dropdown list on the right.

.. image:: /_static/imgs/administration/event/view_auditlog.png
    :width: 700

To download all log files, click on the *Diagnosis* button on the top right corner.
A *diagnosis.zip* file will be downloaded.

.. image:: /_static/imgs/administration/event/auditlog_download.png
    :width: 700

Notification
============

**Add a Webhook**

The *Notification* tab lists the notifications receivers (Webhooks).
A Webhook is triggered on the occurrences of the following events:

#) Lab start, stop, restart, or deletion
#) Pipeline start, stop, restart, or deletion
#) Webapp start, stop, restart, or deletion

.. image:: /_static/imgs/administration/event/view_notification.png
    :width: 700

A generic Webapp sends a POST request to the specified URL with the data in the format below.

.. code-block:: text

    {
        "username": "peter",
        "timestamp": "2022-03-23T06:05:45Z",
        "action": "start",
        "task": {
            "type": "lab",
            "uuid": "u28b9760"
        },
        "flavor": "{'id': 1, 'order': 3, 'name': 'small', 'cpu': 2, 'gpu': 1, 'gpu_type': 'Any', 'categories': [], 'memory': 4096, 'cpu_lab': False, 'info': '(vCPUs: 2, RAM: 4GB, GPU: 1)'}",
        "result": "success"
    }

To add a generic Webhook for receiving notifications:

#) Click on the *CREATE* button.

    .. image:: /_static/imgs/administration/event/add_notification_1.png

#) Input the Webhook's name and URL.
#) Click on the *CREATE* button.

    .. image:: /_static/imgs/administration/event/add_notification_2.png
        :width: 480

#) The Webhook added will be in the list. Reload the page if the list has not been updated.

..
    To add a Slack channel Webhook:

    TODO: TBD
