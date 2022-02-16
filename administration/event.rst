#####
Event
#####

View Auditlog
-------------

The *Auditlog* tab lists the logged events. An event includes the following information:

#) Time stamp: event reporting time
#) Level: logging level
#) User: username (for a user event) or `SYSTEM` (for a system event)
#) Type: event type, could be `User` (user event) or `System` (system event)
#) Message: event message

The events could be filtered by entering the search terms.

.. image:: /_static/imgs/administration/event/view_auditlog.png
    :width: 600

Add a Webhook
-------------

The *Notification* tab lists the notifications receivers (Webhooks). A Webhook is triggered on the occurrences of the following events:

#) Lab start, stop, restart, or deletion
#) Pipeline start, stop, restart, or deletion
#) Webapp start, stop, restart, or deletion

.. image:: /_static/imgs/administration/event/view_notification.png
    :width: 600

A generic Webapp sends a POST request to the specified URL with the data in the format below.

.. code-block:: text

  {
    "username": "admin", 
    "timestamp": "2021-02-01 06:54:11.375141",
    "action": "lab_start", 
    "uuid": "u52ca065", 
    "flavor": "{
                  'id': 2, 
                  'name': 'micro', 
                  'cpu': 2, 
                  'gpu': 0, 
                  'gpu_type': 'Any', 
                  'memory': 2048, 
                  'cpu_lab': True, 
                  'info': '(vCPUs: 2, RAM: 2GB, GPU: 0)'
                }"
  }

FIXME: update the post data (with the correct JSON format)

To add a generic Webhook for receiving notifications:

#) Click on the *CREATE* button.

    .. image:: /_static/imgs/administration/event/add_notification_1.png
        :width: 600

#) Input the Webhook's name and URL. Click on the *CREATE* button.

    .. image:: /_static/imgs/administration/event/add_notification_2.png
        :width: 600

#) The Webhook added will be in the list. Reload the page if the list has not been updated.

    .. image:: /_static/imgs/administration/event/add_notification_3.png
        :width: 600

To add a Slack channel Webhook:

TODO: TBD
