:original_name: en-us_topic_0131645182.html

.. _en-us_topic_0131645182:

Creating a VPC Endpoint Service
===============================

Scenarios
---------

There are two types of VPC endpoint services: gateway and interface.

-  Gateway VPC endpoint services are created only for cloud services.
-  Interface VPC endpoint services can be created for both cloud services and your private services. All VPC endpoint services for cloud services are created by default while those for private services need to be created by users themselves.

This section describes how to configure a private service into an interface VPC endpoint service.

Constraints
-----------

-  VPC endpoint services are region-level resources. Select a region and project when you create such a service.
-  Each tenant can create a maximum of 20 VPC endpoint services.
-  The following private services can be configured into VPC endpoint services:

   -  **Elastic load balancer**: Backend resources of this type suit services that receive high access traffic and demand high reliability and disaster recovery (DR) performance.
   -  **ECS**: Backend resources of this type serve as servers.

-  One VPC endpoint service corresponds to only one backend resource.

Prerequisites
-------------

There are available backend resources in the same VPC.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the required region and project.

#. Choose **Service List** > **Networking** > **VPC Endpoint**.

#. In the navigation pane on the left, choose **VPC Endpoint** > **VPC Endpoint Services**, and click **Create VPC Endpoint Service**.

   The **Create VPC Endpoint Service** page is displayed.


   .. figure:: /_static/images/en-us_image_0000001187847156.png
      :alt: **Figure 1** Create VPC Endpoint Service

      **Figure 1** Create VPC Endpoint Service

#. Configure parameters by referring to :ref:`Table 1 <en-us_topic_0131645182__en-us_topic_0132331143_table20351132821713>`.

   .. _en-us_topic_0131645182__en-us_topic_0132331143_table20351132821713:

   .. table:: **Table 1** Required parameters

      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                                                                        |
      +===================================+====================================================================================================================================================================================================================================================================================+
      | Region                            | Specifies the region where the VPC endpoint service is deployed.                                                                                                                                                                                                                   |
      |                                   |                                                                                                                                                                                                                                                                                    |
      |                                   | Resources in different regions cannot communicate with each other over internal networks. Select the nearest region for lower network latency and faster access to resources.                                                                                                      |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Name                              | This parameter is optional.                                                                                                                                                                                                                                                        |
      |                                   |                                                                                                                                                                                                                                                                                    |
      |                                   | Specifies the name of the VPC endpoint service.                                                                                                                                                                                                                                    |
      |                                   |                                                                                                                                                                                                                                                                                    |
      |                                   | The name can contain a maximum of 16 characters, including letters, digits, underscores (_), and hyphens (-).                                                                                                                                                                      |
      |                                   |                                                                                                                                                                                                                                                                                    |
      |                                   | -  If you do not enter a name, the system automatically generates a name in the *region*.\ *service_id* format                                                                                                                                                                     |
      |                                   | -  If you enter a name, the system automatically generates a name in the *region*.\ *Name*.\ *service_id* format                                                                                                                                                                   |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | VPC                               | Specifies the VPC where the VPC endpoint service is deployed.                                                                                                                                                                                                                      |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Service Type                      | Specifies the type of the VPC endpoint service. The type can only be **Interface**.                                                                                                                                                                                                |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Connection Approval               | Specifies whether the connection between a VPC endpoint and a VPC endpoint service requires approval from the owner of the VPC endpoint service.                                                                                                                                   |
      |                                   |                                                                                                                                                                                                                                                                                    |
      |                                   | You can determine whether to enable or disable the connection approval.                                                                                                                                                                                                            |
      |                                   |                                                                                                                                                                                                                                                                                    |
      |                                   | If connection approval is enabled, any VPC endpoint for connecting to the VPC endpoint service needs to be approved. For details, see :ref:`Managing Connections of a VPC Endpoint Service <vpcep_03_0104>`.                                                                       |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Port Mapping                      | Specifies the protocol and ports used for communications between the VPC endpoint service and VPC endpoint. The protocol is TCP.                                                                                                                                                   |
      |                                   |                                                                                                                                                                                                                                                                                    |
      |                                   | -  **Service Port**: A service port is provided by the backend service bound to the endpoint service.                                                                                                                                                                              |
      |                                   | -  **Terminal Port**: A terminal port is provided by the VPC endpoint, allowing you to access the VPC endpoint service.                                                                                                                                                            |
      |                                   |                                                                                                                                                                                                                                                                                    |
      |                                   | The service and terminal port numbers range from **1** to **65535**. A maximum of 50 port mappings can be added at a time.                                                                                                                                                         |
      |                                   |                                                                                                                                                                                                                                                                                    |
      |                                   | .. note::                                                                                                                                                                                                                                                                          |
      |                                   |                                                                                                                                                                                                                                                                                    |
      |                                   |    Accessing a VPC endpoint service from a VPC endpoint is to access the service port from the associated terminal port.                                                                                                                                                           |
      |                                   |                                                                                                                                                                                                                                                                                    |
      |                                   |    After a port mapping is added, it cannot be modified or deleted.                                                                                                                                                                                                                |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Backend Resource Type             | Specifies the type of the backend resource that provides services to be accessed.                                                                                                                                                                                                  |
      |                                   |                                                                                                                                                                                                                                                                                    |
      |                                   | The following backend resources are supported:                                                                                                                                                                                                                                     |
      |                                   |                                                                                                                                                                                                                                                                                    |
      |                                   | -  **Elastic load balancer**: Backend resources of this type suit services that receive high access traffic and demand high reliability and disaster recovery (DR) performance.                                                                                                    |
      |                                   | -  **ECS**: Backend resources of this type serve as servers.                                                                                                                                                                                                                       |
      |                                   |                                                                                                                                                                                                                                                                                    |
      |                                   | Example: **Elastic load balancer**                                                                                                                                                                                                                                                 |
      |                                   |                                                                                                                                                                                                                                                                                    |
      |                                   | .. note::                                                                                                                                                                                                                                                                          |
      |                                   |                                                                                                                                                                                                                                                                                    |
      |                                   |    For the security group associated with the backend resource configured for the VPC endpoint service, add an inbound rule, with the source IP address set to 198.19.128.0/17. For details, see section "Adding a Security Group Rule" in the *Virtual Private Cloud User Guide*. |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Load Balancer                     | When **Backend Resource Type** is set to **Elastic load balancer**, select the load balancer that provides services from the drop-down list.                                                                                                                                       |
      |                                   |                                                                                                                                                                                                                                                                                    |
      |                                   | .. note::                                                                                                                                                                                                                                                                          |
      |                                   |                                                                                                                                                                                                                                                                                    |
      |                                   |    If an elastic load balancer is used as the backend resource, the source IP address received by the VPC endpoint service is not the real address of the client.                                                                                                                  |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | ECS List                          | When **Backend Resource Type** is set to **ECS**, select the ECS that provides services from the ECS list.                                                                                                                                                                         |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Tag                               | This parameter is optional.                                                                                                                                                                                                                                                        |
      |                                   |                                                                                                                                                                                                                                                                                    |
      |                                   | Specifies the VPC endpoint service tag, which consists of a key and a value. You can add a maximum of 10 tags to each VPC endpoint service.                                                                                                                                        |
      |                                   |                                                                                                                                                                                                                                                                                    |
      |                                   | Tag keys and values must meet requirements listed in :ref:`Table 2 <en-us_topic_0131645182__en-us_topic_0132331143_table539113432713>`.                                                                                                                                            |
      |                                   |                                                                                                                                                                                                                                                                                    |
      |                                   | .. note::                                                                                                                                                                                                                                                                          |
      |                                   |                                                                                                                                                                                                                                                                                    |
      |                                   |    If a predefined tag has been created on TMS, you can directly select the corresponding tag key and value.                                                                                                                                                                       |
      |                                   |                                                                                                                                                                                                                                                                                    |
      |                                   |    For details about predefined tags, see `Predefined Tag Overview <https://docs.sc.otc.t-systems.com/usermanual/tms/en-us_topic_0056266269.html>`__.                                                                                                                              |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _en-us_topic_0131645182__en-us_topic_0132331143_table539113432713:

   .. table:: **Table 2** Tag requirements for VPC endpoint services

      +-----------------------------------+--------------------------------------------------------------------------------------+
      | Parameter                         | Requirement                                                                          |
      +===================================+======================================================================================+
      | Tag key                           | -  Cannot be left blank.                                                             |
      |                                   | -  Must be unique for each resource.                                                 |
      |                                   | -  Can contain a maximum of 36 Unicode characters.                                   |
      |                                   | -  Can contain only digits, letters, hyphens (-), underscores (_), and at signs (@). |
      +-----------------------------------+--------------------------------------------------------------------------------------+
      | Tag value                         | -  Cannot be left blank.                                                             |
      |                                   | -  Can contain a maximum of 43 Unicode characters.                                   |
      |                                   | -  Can contain only digits, letters, hyphens (-), underscores (_), and at signs (@). |
      +-----------------------------------+--------------------------------------------------------------------------------------+

#. Click **Create Now**.

#. Click **Back to VPC Endpoint Service List** to view the newly-created VPC endpoint service.


   .. figure:: /_static/images/en-us_image_0000001179942878.png
      :alt: **Figure 2** VPC endpoint service list

      **Figure 2** VPC endpoint service list

.. |image1| image:: /_static/images/en-us_image_0289945877.png
