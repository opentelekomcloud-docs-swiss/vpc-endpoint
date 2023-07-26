:original_name: vpcep_08_0003_0.html

.. _vpcep_08_0003_0:

Obtaining a Project ID
======================

Scenarios
---------

A project ID is required for some URLs when an API is called. Therefore, you need to obtain a project ID in advance. Two methods are available:

-  :ref:`Obtain the Project ID by Calling an API <vpcep_08_0003_0__en-us_topic_0121673684_section86806471133>`
-  :ref:`Obtain the Project ID from the Console <vpcep_08_0003_0__en-us_topic_0121673684_section11508201712212>`

.. _vpcep_08_0003_0__en-us_topic_0121673684_section86806471133:

Obtain the Project ID by Calling an API
---------------------------------------

You can obtain the project ID by calling the IAM API used to query project information based on the specified criteria.

The API used to obtain a project ID is GET https://{Endpoint}/v3/projects. {Endpoint} is the IAM endpoint and can be obtained from the administrator\ `Regions and Endpoints <https://docs.sc.otc.t-systems.com/en-us/endpoint/index.html>`__. For details about API authentication, see :ref:`Authentication <vpcep_03_0003>`.

The following is an example response. The value of **id** is the project ID.

.. code-block::

   {
       "projects": [
           {
               "domain_id": "65382450e8f64ac0870cd180d14e684b",
               "is_domain": false,
               "parent_id": "65382450e8f64ac0870cd180d14e684b",
               "name": "project_name",
               "description": "",
               "links": {
                   "next": null,
                   "previous": null,
                   "self": "https://www.example.com/v3/projects/a4a5d4098fb4474fa22cd05f897d6b99"
               },
               "id": "a4a5d4098fb4474fa22cd05f897d6b99",
               "enabled": true
           }
       ],
       "links": {
           "next": null,
           "previous": null,
           "self": "https://www.example.com/v3/projects"
       }
   }

.. _vpcep_08_0003_0__en-us_topic_0121673684_section11508201712212:

Obtain a Project ID from the Console
------------------------------------

To obtain a project ID from the console, perform the following operations:

#. Log in to the management console.

#. Click the username and select **My Credentials** from the drop-down list.

   On the **My Credentials** page, view the project ID (value in the **Project ID** column).


.. figure:: /_static/images/en-us_image_0000001224894125.png
   :alt: **Figure 1** Viewing the project ID

   **Figure 1** Viewing the project ID
