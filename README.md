# Nathan James Full Stack Developer - Work Sample

A PHP project to integrate with the external ordering system and external warehouse system using REST API.

## Background of the task

This integration is the first step towards full integration with multiple warehouses and ordering systems. We would like to build a reliable system that integrates with multiple, external ordering systems and be able to evaluate those orders against available inventory in our warehouse(s) and determine if the orders can be accepted based on the requested ship date contained in the orders. We want to fetch the item availability from the warehouse system and orders from the ordering system several times per day.

## Requirements

The goal of the work sample is to create an integration with WAREHOUSE_X warehouse system and ORDERING_Y ordering system.

Fetch all orders with status "new" from the API. If the order is valid, update the order status to "processed". If the order is not valid, the order status is set to "failed".

The order is valid if the order item quantities are satisfied with warehouse item quantities and if our warehouse items are available (`availableFromDate`) before the planned order shipping date (`shippingDate`).

## External systems

### External warehouse system (WAREHOUSE_X)

The external warehouse system has provided us with the following publicly available endpoint:

1) GET https://5f591c568040620016ab8de2.mockapi.io/api/v1/warehouse-items

### External ordering system (ORDERING_Y)

The external ordering system has provided us with the following publicly available endpoints:

1) GET https://5f591c568040620016ab8de2.mockapi.io/api/v1/version20201022orders
2) PUT https://5f591c568040620016ab8de2.mockapi.io/api/v1/version20201022orders/:orderId
