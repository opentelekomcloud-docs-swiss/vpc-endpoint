:original_name: vpcep_02_0000.html

.. _vpcep_02_0000:

API Overview
============

VPC Endpoint provides extended RESTful APIs.

VPC Endpoint APIs allow you to use all VPC Endpoint functions. VPC Endpoint has two types of resources: VPC endpoints and VPC endpoint services.

:ref:`Table 1 <vpcep_02_0000__en-us_topic_0178454981_en-us_topic_0173706804_table420812113211>` describes the APIs provided by VPC Endpoint.

.. _vpcep_02_0000__en-us_topic_0178454981_en-us_topic_0173706804_table420812113211:

.. table:: **Table 1** API overview

   +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | API                               | Description                                                                                                                                                                                                                                                                                     |
   +===================================+=================================================================================================================================================================================================================================================================================================+
   | Version management APIs           | APIs for querying version information of all VPC Endpoint APIs or a specified API.                                                                                                                                                                                                              |
   +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | VPC endpoint service APIs         | APIs for creating, deleting, modifying, or querying a VPC endpoint service, querying, adding, or deleting a whitelist record, and querying the VPC endpoint services, the whitelist records, and the endpoints connected to and those accepted or rejected to connect to a VPC endpoint service |
   |                                   |                                                                                                                                                                                                                                                                                                 |
   |                                   | With these APIs, you can manage VPC endpoint services and set rules based on service conditions to provide services for VPC endpoints.                                                                                                                                                          |
   +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | VPC endpoint APIs                 | APIs for creating, deleting, or querying a VPC endpoint and querying the list of VPC endpoints. With these APIs, you can manage VPC endpoints and use services provided by VPC endpoint services.                                                                                               |
   +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Resource quota API                | API for querying the quota of VPC Endpoint resources                                                                                                                                                                                                                                            |
   +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Tag APIs                          | API for managing VPC Endpoint tags, including querying resources by tag, adding and deleting a tag or tags, and querying resource tags.                                                                                                                                                         |
   +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
