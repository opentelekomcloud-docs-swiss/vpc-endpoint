:original_name: vpcep_02_02023.html

.. _vpcep_02_02023:

Step 2: Create a VPC Endpoint
=============================

Scenarios
---------

After you create a VPC endpoint service, you also need to create a VPC endpoint to access the VPC endpoint service.

This section describes how to create a VPC endpoint in another VPC of your own.

.. note::

   Select the same region and project as those of the VPC endpoint service.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the required region and project.

#. Click **Service List** and choose **Networking** > **VPC Endpoint**.

#. On the **VPC Endpoints** page, click **Create VPC Endpoint**.

   The **Create VPC Endpoint** page is displayed.


   .. figure:: /_static/images/en-us_image_0000001225177055.png
      :alt: **Figure 1** Create VPC Endpoint (**Service Category** set to **Find a service by name**)

      **Figure 1** Create VPC Endpoint (**Service Category** set to **Find a service by name**)

#. Configure required parameters.

   .. table:: **Table 1** VPC endpoint parameters

      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                    |
      +===================================+================================================================================================================================================================+
      | Region                            | Specifies the region where the VPC endpoint is to be located. This region is the same as that of the VPC endpoint service.                                     |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Service Category                  | There are two options:                                                                                                                                         |
      |                                   |                                                                                                                                                                |
      |                                   | -  **Cloud services**: Select this value if the target VPC endpoint service is a cloud service.                                                                |
      |                                   | -  **Find a service by name**: Select this value if the target VPC endpoint service is a private service of your own.                                          |
      |                                   |                                                                                                                                                                |
      |                                   | In this example, select **Find a service by name**.                                                                                                            |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | VPC Endpoint Service Name         | This parameter is available only when you select **Find a service by name** for **Service Category**.                                                          |
      |                                   |                                                                                                                                                                |
      |                                   | Enter the VPC endpoint service name recorded in :ref:`8 <vpcep_02_02022__li837613314320>` and click **Verify**.                                                |
      |                                   |                                                                                                                                                                |
      |                                   | -  If "Service name found." is displayed, proceed with subsequent operations.                                                                                  |
      |                                   | -  If "Service name not found." is displayed, check whether the region is the same as that of the VPC endpoint service or whether the name entered is correct. |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Create a Private Domain Name      | If you want to access a VPC endpoint using a domain name, select **Create a Private Domain Name**.                                                             |
      |                                   |                                                                                                                                                                |
      |                                   | This parameter is mandatory when the VPC endpoint will be used to access an interface VPC endpoint service.                                                    |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | VPC                               | Specifies the VPC where the VPC endpoint is to be deployed.                                                                                                    |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Subnet                            | This parameter is available when you want to access an interface VPC endpoint service.                                                                         |
      |                                   |                                                                                                                                                                |
      |                                   | Specifies the subnet where the VPC endpoint is to be deployed.                                                                                                 |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Private IP Address                | This parameter is available only when you create a VPC endpoint for connecting to an interface VPC endpoint service.                                           |
      |                                   |                                                                                                                                                                |
      |                                   | Specifies the private IP address of the VPC endpoint. You can select **Automatically assign** or **Manually specify**.                                         |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Tag                               | This parameter is optional.                                                                                                                                    |
      |                                   |                                                                                                                                                                |
      |                                   | Specifies the VPC endpoint tag, which consists of a key and a value. You can add up to 10 tags to each VPC endpoint.                                           |
      |                                   |                                                                                                                                                                |
      |                                   | Tag keys and values must meet requirements listed in :ref:`Table 2 <vpcep_02_02023__table1349117521628>`.                                                      |
      |                                   |                                                                                                                                                                |
      |                                   | .. note::                                                                                                                                                      |
      |                                   |                                                                                                                                                                |
      |                                   |    If a predefined tag has been created on TMS, you can directly select the corresponding tag key and value.                                                   |
      |                                   |                                                                                                                                                                |
      |                                   |    For details about predefined tags, see `Predefined Tag Overview <https://docs.sc.otc.t-systems.com/usermanual/tms/en-us_topic_0056266269.html>`__.          |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _vpcep_02_02023__table1349117521628:

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

#. .. _vpcep_02_02023__li1979812511478:

   Manage the connection of the VPC endpoint.

   If the status of the VPC endpoint changes to **Accepted**, the VPC endpoint is connected to the required VPC endpoint service. If the status is **Pending acceptance**, connection approval is enabled for the VPC endpoint service, ask the owner of the VPC endpoint service to perform the following operations:

   a. In the navigation pane on the left, choose **VPC Endpoint** > **VPC Endpoint Services**.
   b. Locate the VPC endpoint service and click its name.
   c. On the displayed page, select the **Connection Management** tab.

      -  If you allow a VPC endpoint to connect to this VPC endpoint service, locate the VPC endpoint and click **Accept** in the **Operation** column.
      -  If you do not allow a VPC endpoint to connect to this VPC endpoint service, click **Reject** in the **Operation** column.

   d. Go back to the VPC endpoint list and check whether the status of the target VPC endpoint changes to **Accepted**. If yes, the VPC endpoint is connected to the VPC endpoint service.

#. In the VPC endpoint list, click the ID of the target VPC endpoint to view its details.

   After a VPC endpoint is created, a private IP address is assigned.


   .. figure:: /_static/images/en-us_image_0000001180096662.png
      :alt: **Figure 2** Summary of the VPC endpoint

      **Figure 2** Summary of the VPC endpoint

   You can use the private IP address or private domain name to access the VPC endpoint service.

Configuration Verification
--------------------------

Remotely log in to an ECS in VPC 1 and access the private IP address or private domain name of the VPC endpoint. For details, see :ref:`Figure 3 <vpcep_02_02023__fig6736736182318>`.

.. _vpcep_02_02023__fig6736736182318:

.. figure:: /_static/images/en-us_image_0000001657608224.png
   :alt: **Figure 3** Logging in to an ECS to access the VPC endpoint

   **Figure 3** Logging in to an ECS to access the VPC endpoint

.. |image1| image:: /_static/images/en-us_image_0289945877.png
