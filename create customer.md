# Create Customer

The API provided below enables the creation of customers for the requesting office. Access to create customers and demands is limited to the offices registered with our platform.

Customer can be either a buyer or seller.

### Important fields:
To create a customer/client for an existing office the following fields information are important.
- `office`
- `firstContactEmail`
- `gstNumber`
- `firstContactName`
- `firstContact`


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
## Body

### Request
```json
{
    "timestamp": 1683971721265,
    "venue": [
        {
            "venueDescriptor": "Customer Office",
            "geopoint": {
                "latitude": 0,
                "longitude": 0
            },
            "location": "",
            "address": ""
        }
    ],
    "schedule": [],
    "office": "KAVYA COSMETICS",
    "share": [],
    "template": "customer",
    "attachment": {
        "firstContactEmail": {
            "type": "string",
            "value": ""
        },
        "gstNumber": {
            "type": "gst",
            "value": "08ATVPB5427E1ZL"
        },
        "supplierAddress": {
            "type": "string",
            "value": ""
        },
        "tds": {
            "type": "number",
            "value": 10
        },
        "moratium": {
            "type": "number",
            "value": 20
        },
        "firstContactName": {
            "type": "string",
            "value": ""
        },
        "earlyPaymentRate": {
            "type": "number",
            "value": 50
        },
        "firstContact": {
            "type": "phoneNumber",
            "value": ""
        },
        "vendorCode": {
            "type": "string",
            "value": "Deepshikha Packaging Solutions Private Limited"
        }
    }
}
```

- Time Stamp

| Key | Value | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
|`timestamp` | 1683971721265 | number | time of the creation |

- Venue

| Key | Value (default) | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
|`venueDescriptor` | Customer Office | String | |
| `geopoint` | | | |
| `location` | | String | Location of the customer office |
| `address` | | String | Address of the customer office |


- Schedule

| Key | Value (default) | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
|`schedule` | can be empty | array | schedule  |


- office

| Key | Value (default) | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
|`office` | KAVYA COSMETICS | String | name of the requesting office  |


- share

| Key | Value (default) | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
|`share` | can be empty | array |   |


- template

| Key | Value (default) | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
|`template` | customer | string |   |


- attachements

| Key | Value (default) | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
| `firstConatctEmail` | deepshikha@gmail.com | String | email id of the customer |
| `gstNumber` | 08ATVPB5427E1ZL | gst (String) | valid gst number of the customer |
| `supplierAddress` | empty | String | Address of the supplier |
| `tds` | 0 | number/int/float | tds to be applied |
| `moratium` | 0 | number/int/float | |
| `firstConatctName` | Deepika Rajwar | String | Name/office name of the supplier |
| `earlyPaymentRate` | 0 | number/int/float | |
| `firstContact` | +918753733567 | phone number | phone number of the supplier |
| `vendorCode` | can be empty | String | vendor code given by the requesting office |



### Response

Upon successful execution of the Create Customer API, the API will return a response containing the newly created customer's unique identifier or any other relevant information associated with the customer.

- **201 - Created** 
```json 
{
    "activityId": "tCjCYULZVQLVHlXbAGmB",
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
    "message": "The 'firstContactEmail' is Invalid.",
    "success": false,
    "code": 400
}
```

```json
{
    "message": "Invalid value for the field 'gstNumber' in attachment object",
    "success": false,
    "code": 400
}
```

```json
{
    "message": "The 'firstContactName' field should be a non-empty string.",
    "success": false,
    "code": 400
}
```
------

- **403 - Forbidden**
```json
{
    "message": "Customer with GST is already exists with this Office",
    "success": false,
    "code": 403
}
```
-----

### Please refer for more detailed errors list ([click here](./errors.md#create)).