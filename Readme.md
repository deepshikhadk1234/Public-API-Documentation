# Public API Documentation
## REVAMPED PUBLIC APIs

Welcome to the API documentation for the Customer Management and Demand Tracking System! This documentation provides detailed information and guidelines for utilizing the following essential APIs:

### Create Customer API

Endpoint: `PUT /activities/create`

Description: This API allows you to create a new customer in the system. It provides a simple way to add customer details such as name, contact information, and other relevant information. Upon successful execution, the API will return the newly created customer's unique identifier.

### Create Demand API

Endpoint: `PUT /activities/create`

Description: With this API, you can generate a new demand record within the system. A demand represents a request or requirement made by a customer for a particular product or service. By providing the necessary inputs, such as customer ID, product details, and quantities, you can create a demand entry. The API will return a demand ID upon successful execution.


### Update Demand API

Endpoint: `PUT /activities/update`

Description: This API allows you to update an existing demand in the system. By specifying the demand ID in the endpoint URL and providing the necessary updated information, such as revised quantities or product details, you can modify the demand as required. This API helps you manage changes and keep demand records up to date.

### Invoice Action API

Endpoint: `PUT /invoice-action`

Description: This API enables you to perform actions related to invoicing. It allows you to generate invoices, update invoice statuses, and handle payment-related operations. By interacting with this API, you can streamline your invoicing process and maintain accurate records of financial transactions.

Please refer to the detailed API documentation for each endpoint to understand the required request structure, response format, and any additional parameters or headers necessary for successful interaction. It is recommended to use appropriate authentication and authorization mechanisms to secure your API requests.

We hope this API documentation helps you effectively integrate and leverage the Customer Management and Demand Tracking System. If you have any questions or need further assistance, please don't hesitate to reach out to our support team. Happy coding!

----
## Streams
| Name           | Description |
----------------|-------------
|[create customer.md](./create%20customer.md)              | API to create customer for the requesting office |
|[demand.md](./demand.md) | API to create demand |
| [update demand.md](./update%20demand.md) | APIs to update an existing demand |
| [invoice action.md](./invoice%20action.md) | APIs to add invoice |
| [errors.md](./errors.md) | Error Listings |
----


