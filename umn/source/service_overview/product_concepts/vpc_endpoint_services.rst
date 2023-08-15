:original_name: vpcep_01_0013.html

.. _vpcep_01_0013:

VPC Endpoint Services
=====================

A VPC endpoint service is a cloud service or a private service that can be accessed through a VPC endpoint.

There are two types of VPC endpoint services: gateway and interface.

-  Gateway VPC endpoint services are created only for cloud services.
-  Interface VPC endpoint services can be created for both cloud services and your private services. All VPC endpoint services for cloud services are created by default while those for private services need to be created by users themselves.

Gateway VPC Endpoint Services
-----------------------------

Gateway endpoint services are configured from cloud services by the system. You do not have the permission to configure such services but can select them when creating a VPC endpoint.

.. note::

   Supported cloud services vary in different regions. For details, see the list of services that can be configured on the management console.

.. table:: **Table 1** Supported gateway VPC endpoint services

   +----------------------+---------------+-------------+---------------------------------+---------------------------------------+
   | VPC Endpoint Service | Category      | Type        | Example                         | Description                           |
   +======================+===============+=============+=================================+=======================================+
   | OBS                  | Cloud service | Gateway     | eu-ch2:                         | Access OBS using its private address. |
   |                      |               |             |                                 |                                       |
   |                      |               |             | com.t-systems.otc.sc.eu-ch2.obs |                                       |
   +----------------------+---------------+-------------+---------------------------------+---------------------------------------+

Interface VPC Endpoint Services
-------------------------------

Interface VPC endpoint services are mainly configured from:

-  Cloud services. You do not have the permission to configure such endpoint services, but can select them when creating a VPC endpoint.
-  Your private services

.. note::

   Supported cloud services vary in different regions. For details, see the list of services that can be configured on the management console.

.. table:: **Table 2** Supported interface VPC endpoint services

   +----------------------+------------------------+-------------+-------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+
   | VPC Endpoint Service | Category               | Type        | Example                             | Description                                                                                                                                              |
   +======================+========================+=============+=====================================+==========================================================================================================================================================+
   | DNS                  | Cloud service          | Interface   | eu-ch2:                             | Select the endpoint service ending with **dns** if you want to access DNS over private networks.                                                         |
   |                      |                        |             |                                     |                                                                                                                                                          |
   |                      |                        |             | com.t-systems.otc.sc.eu-ch2.dns     |                                                                                                                                                          |
   +----------------------+------------------------+-------------+-------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+
   | API Gateway          | Cloud service          | Interface   | eu-ch2:                             | Select the endpoint service ending with **api** if you want to access API Gateway using a VPC endpoint.                                                  |
   |                      |                        |             |                                     |                                                                                                                                                          |
   |                      |                        |             | com.t-systems.otc.sc.eu-ch2.api     |                                                                                                                                                          |
   +----------------------+------------------------+-------------+-------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Console              | Cloud service          | Interface   | eu-ch2:                             | Select the endpoint service ending with **console** if you want to access Console using a VPC endpoint.                                                  |
   |                      |                        |             |                                     |                                                                                                                                                          |
   |                      |                        |             | com.t-systems.otc.sc.eu-ch2.console |                                                                                                                                                          |
   +----------------------+------------------------+-------------+-------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Load balancer        | Users' private service | Interface   | None                                | Select a load balancer as the backend resource if your services receive high traffic and demand high reliability and disaster recovery (DR) performance. |
   +----------------------+------------------------+-------------+-------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+
   | ECS                  | Users' private service | Interface   | None                                | VPC endpoint services work as servers.                                                                                                                   |
   +----------------------+------------------------+-------------+-------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+
