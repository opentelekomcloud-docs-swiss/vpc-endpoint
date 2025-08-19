:original_name: vpcep_03_0401.html

.. _vpcep_03_0401:

Key Operations Recorded by CTS
==============================

Scenarios
---------

With Cloud Trace Service (CTS), you can record VPC Endpoint operation logs for later query, audit, and backtracking.

Constraints
-----------

You have enabled CTS.

Key VPC Endpoint Operations Recorded by CTS
-------------------------------------------

.. table:: **Table 1** VPC Endpoint operations recorded by CTS

   +------------------------------------------------------------------+----------------------+---------------------------+
   | Operation                                                        | Resource Type        | Trace                     |
   +==================================================================+======================+===========================+
   | Creating a VPC endpoint service                                  | EndpointService      | createEndpointService     |
   +------------------------------------------------------------------+----------------------+---------------------------+
   | Modifying a VPC endpoint service                                 | EndpointService      | modifyEndpointService     |
   +------------------------------------------------------------------+----------------------+---------------------------+
   | Deleting a VPC endpoint service                                  | EndpointService      | deleteEndpointService     |
   +------------------------------------------------------------------+----------------------+---------------------------+
   | Rejecting or accepting a VPC endpoint service connection request | EndpointService      | serviceConnectionsAction  |
   +------------------------------------------------------------------+----------------------+---------------------------+
   | Adding or removing a whitelist record                            | EndpointService      | servicePermissionAction   |
   +------------------------------------------------------------------+----------------------+---------------------------+
   | Creating a VPC endpoint                                          | vpcEndpoint          | createEndpoint            |
   +------------------------------------------------------------------+----------------------+---------------------------+
   | Modifying a VPC endpoint                                         | vpcEndpoint          | modifyEndpoint            |
   +------------------------------------------------------------------+----------------------+---------------------------+
   | Deleting a VPC endpoint                                          | vpcEndpoint          | deleteEndpoint            |
   +------------------------------------------------------------------+----------------------+---------------------------+
   | Modifying routes associated with a VPC endpoint                  | vpcEndpoint          | modifyEndpointRouteTables |
   +------------------------------------------------------------------+----------------------+---------------------------+
   | Modifying resource tags in batches                               | vpcEndpointOrService | batchModifyTag            |
   +------------------------------------------------------------------+----------------------+---------------------------+
