# Invoice Action

The following API will create demand for the requesting office. Only registered clients have the access to create customers and demand. 
### Important fields:
To create a demand for an existing office the following fields information are important.
- `invoice_number`
- `invoice_date`
- `payment_due_date`
- `tds`
- `subtotal`
- `cgst_amount`
- `igst_amount`
- `sgst_amount`
- `total`
- `timezone`
- `buyer`
  - `gst_number`
- `seller`
  - `gst_number`
- `po_number`
- `grn`
  - `grn_no`
  - `grn_date`
  - `doc_ref`
- `payment`
  - `utr_number`
  - `payment_method`
  - `payment_date`
  -  `amount`
- `stage_completed`
- `irn`
- `narration`
- `moratium`



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

### Request
```json
{
  "invoice_number": "ADS742-10237439612qq1234",
  "invoice_date": 1660791539574,
  "payment_due_date": 1660791539574,
  "tds": 2,
  "subtotal": 1000,
  "cgst_amount": 180,
  "igst_amount": 180,
  "sgst_amount": 0,
  "total": 1360,
  "timezone": "Asia/Kolkata",
  "buyer": {
    "gst_number": "33AAECT8346F1ZB"
  },
  "seller": {
    "gst_number": "07BOXPS1970R1ZM"
  },
  "po_number": "",
  "grn": {
    "grn_no": "",
    "grn_date": 234324234,
    "doc_ref": ""
  },
  "payment": {
    "utr_number": "UTR",
    "payment_method": "METHOD",
    "payment_date": 3244234,
    "amount": 2334
  },
  "stage_completed": null,
  "irn": "",
  "narration": "",
  "moratium": 2
}
```




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
