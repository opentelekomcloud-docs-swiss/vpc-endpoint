:original_name: vpcep_02_02034.html

.. _vpcep_02_02034:

Step 2: Add a Whitelist Record
==============================

Scenarios
---------

Permission management controls the access of a VPC endpoint in one domain to a VPC endpoint service in another.

After a VPC endpoint service is created, you can add or delete an authorized domain ID to and from the whitelist of the VPC endpoint service.

The following operations describe how to obtain your domain ID and add it to the whitelist of another user's VPC endpoint services.

Prerequisites
-------------

The required VPC endpoint service is available.

Constraints
-----------

-  The VPC endpoint and the VPC endpoint service must be deployed in the same region.
-  Before you configure the whitelist for a VPC endpoint service, obtain the domain ID of the associated VPC endpoint.

Obtain the ID of Your Own Domain
--------------------------------

#. Log in to the management console.

#. Click **My Credentials** under the domain.


   .. figure:: /_static/images/en-us_image_0000001225178125.png
      :alt: **Figure 1** My Credentials

      **Figure 1** My Credentials

   The **My Credentials** page is displayed. You can view the domain ID of VPC 1.


   .. figure:: /_static/images/en-us_image_0000001180097640.png
      :alt: **Figure 2** My Credentials

      **Figure 2** My Credentials

Add Domain IDs to Be Authorized to the Whitelist of a VPC Endpoint Service
--------------------------------------------------------------------------

#. Click |image1| in the upper left corner and select the required region and project.

2. Click **Service List** and choose **Networking** > **VPC Endpoint**.

3. In the navigation pane on the left, choose **VPC Endpoint** > **VPC Endpoint Services**.

4. In the VPC endpoint service list, locate the VPC endpoint service and click its name.

5. On the displayed page, select the **Permission Management** tab and click **Add to Whitelist**.

6. Enter an authorized domain ID in the required format and click **OK**.


   .. figure:: /_static/images/en-us_image_0000001225258021.png
      :alt: **Figure 3** Add to Whitelist

      **Figure 3** Add to Whitelist

   .. note::

      -  Your domain is in the whitelist of your VPC endpoint service by default.

      -  The authorized domain ID is in the **iam:domain::domain_id** format.

         *domain_id* indicates the ID of the authorized domain, for example, **iam:domain::1564ec50ef2a47c791ea5536353ed4b9**

      -  Adding **\*** to the whitelist means that all users can access the VPC endpoint service.

.. |image1| image:: /_static/images/en-us_image_0289945877.png
