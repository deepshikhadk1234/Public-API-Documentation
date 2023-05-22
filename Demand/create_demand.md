# Create Demand
The API provided below enables the creation of demands for the requesting office. Access to create customers and demands is limited to the offices registered with our platform.

Customer can be either a buyer or seller.

### Important fields:
To create a demand for an existing office the following fields information are important.
- `schedule`
- `dueDate`
- `name`
- `billingDate`
- `totalAmount`
- `billingCustomer`
- `billingBranch`
- `office`


----
## Request Example

### Header

**Method : PUT**

```
curl --location --request PUT 'baseURL' \
--header 'Content-Type: application/json' \
--header 'Authorization: {{token}} \
--data '{"field1":"value1","field2":"value2"}'
  ```

| Key | Value | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
| `Authorization` | Basic {{token}} | String | Token generated from login |
|`Content-Type `| Application/json | String | application/json |

----
----
### Body Parameters

```json
{
    "share": [],
    "timestamp": 1682899381000,
    "template": "demand",
    "schedule": [
        {
            "name": "Invoice Date",
            "startTime": 1682899381000,
            "endTime": 1682899391000
        }
    ],
    "venue": [],
    "attachment": {
        "tds": {
            "type": "number",
            "value": 0
        },
        "irn": {
            "type": "string",
            "value": ""
        },
        "narration": {
            "type": "string",
            "value": ""
        },
        "dueDate": {
            "type": "string",
            "value": "1688124200000"
        },
        "name": {
            "type": "string",
            "value": "BILL/2023/06"
        },
        "billingDate": {
            "type": "number",
            "value": 1682899381000
        },
        "totalAmount": {
            "type": "number",
            "value": 207500
        },
        "sgst": {
            "type": "number",
            "value": 0
        },
        "billingCustomer": {
            "type": "gst",
            "value": "03EOTPS2048P1Z4"
        },
        "billingBranch": {
            "type": "gst-office",
            "value": "07APTPS2670G1ZD"
        },
        "cgst": {
            "type": "number",
            "value": 0
        },
        "moratium": {
            "type": "number",
            "value": 0
        },
        "igst": {
            "type": "number",
            "value": 2500
        }
    },
    "office": "SEHRAWAT TRANSPORT SERVICE"
}
```
-------

### Attributes

| Key | Value | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
|`share` | empty | array | |
|`timestamp` | 1683971979663 | number | time of the creation |
|`template` | demand | String | structure of the API call, here Demand/customer |
|`venue` | empty array | array | venue/address of the requesting office  |
|`office` | KAVYA COSMETICS | String | name of the requesting office  |


- `schedule`

    Sub-Attributes

    | Key | Value (default) | Data Type | Description |
    | ----------- | ----------- | ------------| ----------- |
    |`name` | Invoice Date | string | date of the invoice added  |
    | `startTime` | 1682899381000 | number | time of the invoice creation |
    | `endTime` | 1682899391000 | number | time of the invoice creation |


- `attachements`

    | Key | Value (default) | Data Type | Description |
    | ----------- | ----------- | ------------| ----------- |
    | `sgst` | 0 | number/int/float | value of the sgst to be applied depending upon the gst number of the buyer and seller |
    | `tds` | 0 | number/int/float | tds to be applied |
    | `irn` | can be empty | String | invoice referrence number |
    | `dueDate` | 1687804200000 | String | due date for payment |
    | `cgst` | 0 | number/int/float | value of the cgst to be applied depending upon the gst number of the buyer and seller |
    | `igst` | 2500 | number/int/float | value of the igst to be applied |
    | `billingDate` | 1682899381000 | number/int/float | date of the bills added |
    | `totalAmount` | 207500 | number | total amount on the invoice |
    | `billingCustomer` | 03EOTPS2048P1Z4 | gst number | gst number of the billing customer/buyer |
    | `moratium` | 0 | number/int/float | credit days |
    | `narration` | can be empty | String | comments added |
    | `billingBranch` | 07APTPS2670G1ZD | gst-office | gst number of the requesting office/seller |
    | `name` | BILL/2023/06 | String | vendor code |


------

## Response Example

Upon successful execution of the Create Customer API, the API will return a response containing the newly created customer's unique identifier or any other relevant information associated with the customer.

- **201 - Created**
```json 
{
    "activityId": "wTtWcTBccQDQ8pXRsfLw",
    "message": "",
    "success": true,
    "code": 201
}
```

----
----


## Error Response

In case of errors during the API call, you may receive one of the following error responses:

1. Unauthorized Error: Occurs when the request lacks valid authentication or authorization credentials.

2. Server Error: Indicates an unexpected error on the server side, such as a database connection issue or an unhandled exception.

- **400 - Bad Request**
```json
{
    "message": "the field of type 'gst-office' must belong to the requesting office only",
    "success": false,
    "code": 400
}
```

-----

### Please refer for more detailed errors list ([*click here*](/Errors/errors.md#demand)).


