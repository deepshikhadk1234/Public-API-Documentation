# Create Demand

The following API will create demand for the requesting office. Only registered clients have the access to create customers and demand. 
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
## Header

**Method : PUT**

```
Authorization: Basic {{token}}
Content-Type: application/json
  ```
| Key | Value | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
| `Authorization` | Basic {{token}} | String | Token generated from login |
|`Content-Type `| Application/json | String | application/json |

----
----
## Body

### Request (Code View)
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
            "value": 205000
        },
        "sgst": {
            "type": "number",
            "value": 2500
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
            "value": 2500
        },
        "moratium": {
            "type": "number",
            "value": 0
        },
        "igst": {
            "type": "number",
            "value": 0
        }
    },
    "office": "SEHRAWAT TRANSPORT SERVICE"
}
```
-------

### Form View
- Share

| Key | Value | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
|`share` | empty | array | |

- Time Stamp

| Key | Value | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
|`timestamp` | 1683971979663 | number | time of the creation |

- Template

| Key | Value | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
|`template` | demand | String | structure of the API call, here Demand/customer |


- Schedule

| Key | Value (default) | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
|`schedule` |  | array | schedule  |

- Venue 

| Key | Value (default) | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
|`venue` |  | array |   |


- attachements

| Key | Value (default) | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
| `sgst` | 0 | number/int/float | value of the sgst to be applied depending upon the gst number of the buyer and seller |
| `tds` | 0 | number/int/float | value of the tds |
| `irn` | can be empty | String | invoice referrence number |
| `dueDate` | 1687804200000 | String | due date for payment |
| `cgst` | 0 | number/int/float | value of the cgst to be applied depending upon the gst number of the buyer and seller |
| `igst` | 9900 | number/int/float | value of the igst to be applied |
| `billingDate` | 0 | number/int/float | date of the |
| `totalAmount` | 64900 | number | total amount on the invoice |
| `billingCustomer` | 22AACCB1450G1ZD | gst number | gst number of the billing customer/buyer |
| `moratium` | 0 | number/int/float |  |
| `narration` | can be empty | String | |
| `billingBranch` | 27AAQFK7480A1Z4 | gst-office | gst number of the requesting office/seller |
| `name` | KC/23-24/305123123 | String | vendor code |

- office

| Key | Value (default) | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
|`office` | KAVYA COSMETICS | String | name of the requesting office  |

------

### Response

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

### Please refer for more detailed errors list ([click here](./errors.md#create)).


