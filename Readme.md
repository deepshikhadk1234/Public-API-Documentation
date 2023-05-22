# Public API Documentation
## REVAMPED PUBLIC APIs

Welcome to the API documentation for the Customer Management and Demand Tracking System! This documentation provides detailed information and guidelines for utilizing the following essential APIs:

### Create Customer API

Endpoint: `PUT /activities/create`

Description: This API allows you to create a new customer in the system. Customer represents a client (buyer) or a vendor. It provides a simple way to add customer details such as name, contact information, and other relevant information like credit period and TDS amount. Upon successful execution, the API will return the newly created customer's unique identifier.


### Create Demand API

Endpoint: `PUT /activities/create`

Description: With this API, you can create a new demand record within the system. A demand represents an invoice that was raised by vendor for a particular product or service. By providing the necessary inputs, such as Client GSTIN, Seller GSTIN, Invoice date, Taxable amount, all GST amounts, Total amount, TDS and Due date, you can create a demand entry. The API will return a demand activity ID upon successful execution.



### Update Demand API

Endpoint: `PUT /activities/update`

Description: This API allows you to update an existing demand in the system. By specifying the demand ID in the endpoint URL and providing the necessary updated information, such as partial payment details, full payment details, you can modify the demand as required. This API helps you manage changes and keep demand records up to date.
### Invoice Action API

Endpoint: `PUT /invoice-action`

Description: This API enables you to perform actions related to invoicing. It allows you to generate invoices, update invoice statuses, and handle payment-related operations. By interacting with this API, you can streamline your invoicing process and maintain accurate records of financial transactions.

Please refer to the detailed API documentation for each endpoint to understand the required request structure, response format, and any additional parameters or headers necessary for successful interaction. It is recommended to use appropriate authentication and authorization mechanisms to secure your API requests.

We hope this API documentation helps you effectively integrate and leverage the Customer Management and Demand Tracking System. If you have any questions or need further assistance, please don't hesitate to reach out to our support team. Happy coding!

----
## Streams

- Customer
    - [create_customer](/Customer/create_customer.md) - APIs to create new customer/office 
- Demand
    - [create_demand](/Demand/create_demand.md) - APIs to create new demand
    - [update_demand](/Demand/update_demand.md) - APIs to update any existing demand
- Invoice Action 
    - [invoice_action](/Invoice%20Action/invoice_action.md) - APIs for invoice action
- Errors
    - [errors](/Errors/errors.md) - Error listing and Handling
        
        

----


