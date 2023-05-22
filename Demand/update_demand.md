# Update Demand 

The following API will update demand for the activity ID provide by requesting office. Only registered clients have the access to create customers and demand. 
### Important fields:
To update a demand the following fields information are important.
- `schedule`
- `activityId`
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
| `Authorization` | Bearer {{token}} | String | Token generated from login |
|`Content-Type `| Application/json | String | application/json |

----
----
### Body Parameters

```json
{
    "share": [],
    "timestamp": 1682899381000,
    "template": "demand",
    "activityId" : "TqfXtxddlWlHqC92Ek9U",
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

### Attributes

| Key | Value | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
|`share` | empty | array | |
|`timestamp` | 1683971979663 | number | time of the creation |
|`template` | demand | String |  |
|`activityId` | K3rsy45zrls0kVANgbkh | String | activity id  |
|`schedule` |  | array | schedule  |
|`venue` |  | array |   |


- `attachements`

    | Key | Value (default) | Data Type | Description |
    | ----------- | ----------- | ------------| ----------- |
    | `sgst` | 0 | number/int/float | value of the sgst |
    | `tds` | 0 | number/int/float | value of the tds |
    | `irn` | can be empty | String |  |
    | `dueDate` | 1687804200000 | String | due date for payment |
    | `cgst` | 0 | number/int/float | value of the cgst |
    | `igst` | 9900 | number/int/float | value of the igst |
    | `billingDate` | 0 | number/int/float | |
    | `totalAmount` | 64900 | number | total amount on the invoice |
    | `billingCustomer` | 22AACCB1450G1ZD | gst number | gst number of the billing customer |
    | `moratium` | 0 | number/int/float |  |
    | `narration` | can be empty | String | |
    | `billingBranch` | 27AAQFK7480A1Z4 | gst-office | gst number of the requesting customer |
    | `name` | KC/23-24/305123123 | String | vendor code |

| Key | Value (default) | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
|`office` | KAVYA COSMETICS | String | name of the requesting office  |

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

### For more detailed errors [*click here*](/Errors/errors.md#update).



