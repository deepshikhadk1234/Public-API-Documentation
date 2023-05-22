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
## Request Example

### Header

**Method : PUT**
```json
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
### Body Parameters


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
            "value": "deepika_rajwar@gmail.com"
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
            "value": 0
        },
        "moratium": {
            "type": "number",
            "value": 0
        },
        "firstContactName": {
            "type": "string",
            "value": "Deepika Rajwar"
        },
        "earlyPaymentRate": {
            "type": "number",
            "value": 50
        },
        "firstContact": {
            "type": "phoneNumber",
            "value": "+917668235469"
        },
        "vendorCode": {
            "type": "string",
            "value": "Deepshikha Packaging Solutions Private Limited"
        }
    }
}
```


### Attributes

- Time Stamp

| Key | Value | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
|`timestamp` | 1683971721265 | number | time of the creation |

- Venue

| Key | Value (default) | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
|`venueDescriptor` | Customer Office | String | requesting client office |
| `geopoint` | | | |
| `location` | | String | Location of the requesting client office |
| `address` | | String | Address of the requesting client office |


- Schedule

| Key | Value (default) | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
|`schedule` | can be empty | array | schedule  |


- office

| Key | Value (default) | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
|`office` | KAVYA COSMETICS | String | name of the requesting client office  |


- share

| Key | Value (default) | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
|`share` | can be empty | array |   |


- template

| Key | Value (default) | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
|`template` | customer | string | structure of the API call, here Demand/customer |


- attachements

| Key | Value (default) | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
| `firstConatctEmail` | deepika_rajwar@gmail.com| String | email id of the customer |
| `gstNumber` | 08ATVPB5427E1ZL | gst (String) | valid gst number of the customer |
| `supplierAddress` | empty | String | Address of the customer |
| `tds` | 0 | number/int/float | tds to be applied |
| `moratium` | 0 | number/int/float | |
| `firstConatctName` | Deepika Rajwar | String | Name/office name of the customer |
| `earlyPaymentRate` | 50 | number/int/float | |
| `firstContact` | +917668235469 | phone number | phone number of the customer |
| `vendorCode` | Deepshikha Packaging Solutions Private Limited | String | vendor code given by the requesting client office |



## Response Example

Upon successful execution of the Create Customer API, the API will return a response containing the newly created customer's `activityID` or any other relevant information associated with the customer.

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