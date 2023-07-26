:original_name: vpcep_04_0000.html

.. _vpcep_04_0000:

Configuring a VPC Endpoint for Communication Across VPCs
========================================================

Scenarios
---------

VPCEP enables you to privately connect your VPC to a VPC endpoint service (a cloud service or your private service) in another VPC, providing higher access efficiency and networking security compared with EIPs.

This section describes how to invoke APIs described in :ref:`Creating a VPC Endpoint Service <vpcep_06_0201>` and :ref:`Creating a VPC Endpoint <vpcep_06_0303>` to connect a VPC endpoint to a VPC endpoint service. For details, see :ref:`Calling APIs <vpcep_03_0000>`.

.. note::

   The token obtained from IAM is valid for only 24 hours. If you want to use one token for authentication, you can cache it to avoid frequently calling the IAM API.

Prerequisites
-------------

You have planned the region where you want to create a VPC endpoint and obtained the endpoint required for API calls. For details, see :ref:`Endpoints <vpcep_01_0003>`.

Creating a VPC Endpoint Service
-------------------------------

The following is an example request of creating an interface VPC endpoint service for an ECS:

.. note::

   Before creating a VPC endpoint service, obtain necessary information such as values of parameters **vpc_id** and **port_id**. For details, see :ref:`Creating a VPC Endpoint Service <vpcep_06_0201>`.

.. code-block::

   {
     "port_id": "4189d3c2-8882-4871-a3c2-d380272eed88",
     "vpc_id": "4189d3c2-8882-4871-a3c2-d380272eed80",
     "approval_enabled":false,
     "service_type":"interface",
     "server_type":"VM",
     "ports":
              [
                {
                  "client_port":8080,
                  "server_port":80,
                  "protocol":"TCP"
                },
                {
                  "client_port":8081,
                  "server_port":80,
                  "protocol":"TCP"
                }
               ]
   }

-  **port_id**: indicates the ID for identifying the backend service of a VPC endpoint service. For example, when you create a VPC endpoint service for an ECS, set this parameter to the NIC ID of the ECS's IP address.
-  **vpc_id**: indicates the ID of the VPC where the backend resource is located.
-  **approval_enabled**: indicates whether approval is required when a VPC endpoint connects to a VPC endpoint service. For example, if this parameter is set to **false**, no approval is required.
-  **service_type**: indicates the type of the VPC endpoint service. For example, if this parameter is set to **interface**, the created VPC endpoint service is of the interface type.
-  **server_type**: indicates the type of the backend resource. For example, if this parameter is set to **VM**, the backend resource is an ECS.
-  **ports.client_port**: indicates the port provided by the VPC endpoint, allowing you to access the VPC endpoint service.
-  **ports.server_port**: indicates the port provided by the backend resource to provide services.
-  **ports.protocol**: indicates the protocol used for the port mapping.

Creating a VPC Endpoint
-----------------------

The following is an example request for creating a VPC endpoint, and creating a private domain name is supported.

.. note::

   Before creating a VPC endpoint, obtain necessary information, such as values of parameters **vpc_id** and **subnet_id** and the VPC endpoint service ID returned in the previous step. For details, see :ref:`Creating a VPC Endpoint <vpcep_06_0303>`.

.. code-block::

   {
     "subnet_id": "4189d3c2-8882-4871-a3c2-d380272eed81",
     "vpc_id": "4189d3c2-8882-4871-a3c2-d380272eed82",
     "endpoint_service_id":"4189d3c2-8882-4871-a3c2-d380272eed83",
     "enable_dns":true
   }

-  **subnet_id**: indicates the ID of the subnet where the VPC endpoint is created.
-  **vpc_id**: indicates the ID of the VPC where the VPC endpoint is created.
-  **endpoint_service_id**: indicates the ID of the VPC endpoint service.
-  **enable_dns**: indicates whether to create a private domain name for the VPC endpoint. For example, if this parameter is set to **true**, a private domain name is created for the VPC endpoint.

After the VPC endpoint is created, ECSs in the VPC where the VPC endpoint is located can access VPC endpoint service **4189d3c2-8882-4871-a3c2-d380272eed83** using this endpoint.
