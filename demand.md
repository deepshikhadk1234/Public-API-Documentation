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
|`template` | demand | String |  |

<!-- - Venue

| Key | Value (default) | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
|`venueDescriptor` | Customer Office | String | |
| `geopoint` | | | |
| `location` | | String | Location of the customer office |
| `address` | | String | Address of the customer office | -->


- Schedule

| Key | Value (default) | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
|`schedule` |  | array | schedule  |

- Venue 

| Key | Value (default) | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
|`venue` |  | array |   |

<!-- 

- share

| Key | Value (default) | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
|`share` | can be empty | array |   |


- template

| Key | Value (default) | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
|`template` | customer | string |   | -->


- attachements

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

- office

| Key | Value (default) | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
|`office` | KAVYA COSMETICS | String | name of the requesting office  |

------

### Response
- 201 - Created 
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
- 400 - Bad Request
```json
{
    "message": "the field of type 'gst-office' must belong to the requesting office only",
    "success": false,
    "code": 400
}
```


