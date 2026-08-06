:original_name: en-us_topic_0131645189.html

.. _en-us_topic_0131645189:

Creating a VPC Endpoint
=======================

Scenarios
---------

VPC endpoints are secure and private channels for connecting VPCs to VPC endpoint services.

You can create a VPC endpoint to connect a resource in your VPC to a VPC endpoint service in another VPC of the same region.

A VPC endpoint comes with a VPC endpoint service. VPC endpoints vary depending on the type of the VPC endpoint services that they can access.

-  VPC endpoints for accessing interface VPC endpoint services are elastic network interfaces that have private IP addresses.
-  VPC endpoints for accessing gateway VPC endpoint services are gateways, with routes configured to distribute traffic to the associated VPC endpoint services.

You can create an interface or a gateway VPC endpoint based the type of the associated VPC endpoint service.

-  :ref:`Creating a VPC Endpoint for Accessing Interface VPC Endpoint Services <en-us_topic_0131645189__section339372615535>`
-  :ref:`Creating a VPC Endpoint for Accessing Gateway VPC Endpoint Services <en-us_topic_0131645189__section3281125041216>`

Constraints
-----------

-  VPC endpoints are region-level resources. Select a region and project when you create such a VPC endpoint.
-  Each tenant can create a maximum of 50 VPC endpoints.
-  When you create a VPC endpoint, ensure that the associated VPC endpoint service is deployed in the same region as the VPC endpoint.

.. _en-us_topic_0131645189__section339372615535:

Creating a VPC Endpoint for Accessing Interface VPC Endpoint Services
---------------------------------------------------------------------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the required region and project.

#. Click **Service List** and choose **Networking** > **VPC Endpoint**.

#. On the **VPC Endpoints** page, click **Create VPC Endpoint**.

#. On the **Create VPC Endpoint** page, configure the parameters.


   .. figure:: /_static/images/en-us_image_0000001179796800.png
      :alt: **Figure 1** Create VPC Endpoint (**Service Category** set to **Cloud services**)

      **Figure 1** Create VPC Endpoint (**Service Category** set to **Cloud services**)


   .. figure:: /_static/images/en-us_image_0000001179798828.png
      :alt: **Figure 2** Create VPC Endpoint (**Service Category** set to **Find a service by name**)

      **Figure 2** Create VPC Endpoint (**Service Category** set to **Find a service by name**)

   .. table:: **Table 1** VPC endpoint parameters

      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                        |
      +===================================+====================================================================================================================================================================================================================+
      | Region                            | Specifies the region where the VPC endpoint is to be located. Resources in different regions cannot communicate with each other over an intranet. For lower latency and quicker access, select the nearest region. |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Service Category                  | There are two options:                                                                                                                                                                                             |
      |                                   |                                                                                                                                                                                                                    |
      |                                   | -  **Cloud services**: Select this value if the target VPC endpoint service is a cloud service.                                                                                                                    |
      |                                   | -  **Find a service by name**: Select this value if the target VPC endpoint service is a private service of your own.                                                                                              |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Service List                      | This parameter is available only when you select **Cloud services** for **Service Category**.                                                                                                                      |
      |                                   |                                                                                                                                                                                                                    |
      |                                   | The VPC endpoint service has been created by the O&M personnel and you can directly use it.                                                                                                                        |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | VPC Endpoint Service Name         | This parameter is available only when you select **Find a service by name** for **Service Category**.                                                                                                              |
      |                                   |                                                                                                                                                                                                                    |
      |                                   | In the VPC endpoint service list, locate the VPC endpoint service, copy its name in the **Name** column, paste it to the **VPC Endpoint Service Name** text box, and click **Verify**.                             |
      |                                   |                                                                                                                                                                                                                    |
      |                                   | -  If "Service name found." is displayed, proceed with subsequent operations.                                                                                                                                      |
      |                                   | -  If "Service name not found." is displayed, check whether the region is the same as that of the VPC endpoint service or whether the name entered is correct.                                                     |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Create a Private Domain Name      | If you want to access a VPC endpoint using a domain name, select **Create a Private Domain Name**.                                                                                                                 |
      |                                   |                                                                                                                                                                                                                    |
      |                                   | This parameter is mandatory when the VPC endpoint will be used to access an interface VPC endpoint service.                                                                                                        |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | VPC                               | Specifies the VPC where the VPC endpoint is to be deployed.                                                                                                                                                        |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Subnet                            | This parameter is available when you want to access an interface VPC endpoint service.                                                                                                                             |
      |                                   |                                                                                                                                                                                                                    |
      |                                   | Specifies the subnet where the VPC endpoint is to be located.                                                                                                                                                      |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Private IP Address                | This parameter is available when you want to access an interface VPC endpoint service.                                                                                                                             |
      |                                   |                                                                                                                                                                                                                    |
      |                                   | Specifies the private IP address of the VPC endpoint. The addresses can be automatically assigned or manually specified.                                                                                           |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Tag                               | This parameter is optional.                                                                                                                                                                                        |
      |                                   |                                                                                                                                                                                                                    |
      |                                   | Specifies the VPC endpoint tag, which consists of a key and a value. You can add up to 10 tags to each VPC endpoint.                                                                                               |
      |                                   |                                                                                                                                                                                                                    |
      |                                   | Tag keys and values must meet requirements listed in :ref:`Table 2 <en-us_topic_0131645189__table37259471306>`.                                                                                                    |
      |                                   |                                                                                                                                                                                                                    |
      |                                   | .. note::                                                                                                                                                                                                          |
      |                                   |                                                                                                                                                                                                                    |
      |                                   |    If a predefined tag has been created on TMS, you can directly select the corresponding tag key and value.                                                                                                       |
      |                                   |                                                                                                                                                                                                                    |
      |                                   |    For details about predefined tags, see `Predefined Tag Overview <https://docs.sc.otc.t-systems.com/usermanual/tms/en-us_topic_0056266269.html>`__.                                                              |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _en-us_topic_0131645189__table37259471306:

   .. table:: **Table 2** Tag requirements for VPC endpoints

      +-----------------------------------+--------------------------------------------------------------------------------------+
      | Parameter                         | Requirement                                                                          |
      +===================================+======================================================================================+
      | Tag key                           | -  Cannot be left blank.                                                             |
      |                                   | -  Must be unique for each resource.                                                 |
      |                                   | -  Can contain a maximum of 36 characters.                                           |
      |                                   | -  Can contain only digits, letters, hyphens (-), underscores (_), and at signs (@). |
      +-----------------------------------+--------------------------------------------------------------------------------------+
      | Tag value                         | -  Cannot be left blank.                                                             |
      |                                   | -  Can contain a maximum of 43 characters.                                           |
      |                                   | -  Can contain only digits, letters, hyphens (-), underscores (_), and at signs (@). |
      +-----------------------------------+--------------------------------------------------------------------------------------+

#. Confirm the specifications and click **Create Now**.

   -  If all of the specifications are correct, click **Submit**.
   -  If any of the specifications are incorrect, click **Previous** to return to the previous page and modify the parameters as needed, and click **Submit**.

.. _en-us_topic_0131645189__section3281125041216:

Creating a VPC Endpoint for Accessing Gateway VPC Endpoint Services
-------------------------------------------------------------------

#. Log in to the management console.

#. Click |image2| in the upper left corner and select the required region and project.

#. Click **Service List** and choose **Networking** > **VPC Endpoint**.

#. On the **VPC Endpoints** page, click **Create VPC Endpoint**.

#. On the **Create VPC Endpoint** page, configure the parameters.


   .. figure:: /_static/images/en-us_image_0000001180118582.png
      :alt: **Figure 3** Create VPC Endpoint (**Service Category** set to **Cloud services**)

      **Figure 3** Create VPC Endpoint (**Service Category** set to **Cloud services**)

   .. table:: **Table 3** VPC endpoint parameters

      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                        |
      +===================================+====================================================================================================================================================================================================================+
      | Region                            | Specifies the region where the VPC endpoint is to be located. Resources in different regions cannot communicate with each other over an intranet. For lower latency and quicker access, select the nearest region. |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Service Category                  | There are two options:                                                                                                                                                                                             |
      |                                   |                                                                                                                                                                                                                    |
      |                                   | -  **Cloud services**: Select this value if the target VPC endpoint service is a cloud service.                                                                                                                    |
      |                                   | -  **Find a service by name**: Select this value if the target VPC endpoint service is a private service of your own.                                                                                              |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Service List                      | This parameter is available only when you select **Cloud services** for **Service Category**.                                                                                                                      |
      |                                   |                                                                                                                                                                                                                    |
      |                                   | In the VPC endpoint service list, select the VPC endpoint service whose type is gateway.                                                                                                                           |
      |                                   |                                                                                                                                                                                                                    |
      |                                   | The VPC endpoint service has been created by the O&M personnel and you can directly use it.                                                                                                                        |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | VPC Endpoint Service Name         | This parameter is available only when you select **Find a service by name** for **Service Category**.                                                                                                              |
      |                                   |                                                                                                                                                                                                                    |
      |                                   | Enter the VPC endpoint service name recorded in :ref:`7 <en-us_topic_0131645182__li955435119157>` and click **Verify**.                                                                                            |
      |                                   |                                                                                                                                                                                                                    |
      |                                   | -  If "Service name found." is displayed, proceed with subsequent operations.                                                                                                                                      |
      |                                   | -  If "Service name not found." is displayed, check whether the region is the same as that of the VPC endpoint service or whether the name entered is correct.                                                     |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | VPC                               | Specifies the VPC where the VPC endpoint is to be deployed.                                                                                                                                                        |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Tag                               | This parameter is optional.                                                                                                                                                                                        |
      |                                   |                                                                                                                                                                                                                    |
      |                                   | Specifies the VPC endpoint tag, which consists of a key and a value. You can add up to 10 tags to each VPC endpoint.                                                                                               |
      |                                   |                                                                                                                                                                                                                    |
      |                                   | Tag keys and values must meet requirements listed in :ref:`Table 4 <en-us_topic_0131645189__table62892050161211>`.                                                                                                 |
      |                                   |                                                                                                                                                                                                                    |
      |                                   | .. note::                                                                                                                                                                                                          |
      |                                   |                                                                                                                                                                                                                    |
      |                                   |    If a predefined tag has been created on TMS, you can directly select the corresponding tag key and value.                                                                                                       |
      |                                   |                                                                                                                                                                                                                    |
      |                                   |    For details about predefined tags, see `Predefined Tag Overview <https://docs.sc.otc.t-systems.com/usermanual/tms/en-us_topic_0056266269.html>`__.                                                              |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _en-us_topic_0131645189__table62892050161211:

   .. table:: **Table 4** Tag requirements for VPC endpoints

      +-----------------------------------+--------------------------------------------------------------------------------------+
      | Parameter                         | Requirement                                                                          |
      +===================================+======================================================================================+
      | Tag key                           | -  Cannot be left blank.                                                             |
      |                                   | -  Must be unique for each resource.                                                 |
      |                                   | -  Can contain a maximum of 36 characters.                                           |
      |                                   | -  Can contain only digits, letters, hyphens (-), underscores (_), and at signs (@). |
      +-----------------------------------+--------------------------------------------------------------------------------------+
      | Tag value                         | -  Cannot be left blank.                                                             |
      |                                   | -  Can contain a maximum of 43 characters.                                           |
      |                                   | -  Can contain only digits, letters, hyphens (-), underscores (_), and at signs (@). |
      +-----------------------------------+--------------------------------------------------------------------------------------+

#. Confirm the specifications and click **Create Now**.

   -  If all of the specifications are correct, click **Submit**.
   -  If any of the specifications are incorrect, click **Previous** to return to the previous page and modify the parameters as needed, and click **Submit**.

.. |image1| image:: /_static/images/en-us_image_0289945877.png
.. |image2| image:: /_static/images/en-us_image_0289945877.png
