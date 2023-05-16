# Create Customer

The following API will create customer for the requesting office. Only registered clients have the access to create customers and demand. 
### Important fields:
To create a customer/client for an existing office the following fields information are important.
- `office`
- `firstContactEmail`
- `gstNumber`
- `firstContactName`
- `firstContact`


----
## Header
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
- 201 - Created 
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
- 403 - Forbidden 
```json
{
    "message": "Customer with GST is already exists with this Office",
    "success": false,
    "code": 403
}
```


