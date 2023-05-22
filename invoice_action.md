# Invoice Action

The following API will create demand for the requesting office. Only registered clients have the access to create customers and demand. 
### Important fields:
To create a demand for an existing office the following fields information are important.
- `invoice_number`
- `invoice_date`
- `payment_due_date`
- `tds`
- `subtotal`
- (`cgst_amount` & `igst_amount`) / `sgst_amount` - depending upon the GST number of buyer and seller
- `total`
- `timezone`
- `buyer`
  - `gst_number`
- `seller`
  - `gst_number`
- `grn`
  - `grn_date`
- `payment`
  - `utr_number`
  - `payment_method`
  - `payment_date`
  -  `amount`



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
----
### Body Parameters

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
### Attributes

| Key | Value | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
| `invoice_number` | ADS742-10237439612qq1234 | string | invoice number 
| `invoice_date` | 1660791539574 | number | date of the invoice created
| `payment_due_date` | 1660791539574 | number | due date of the invoice 
| `tds` | 2 | number | tds to be applied
| `subtotal` | 1000 | int/float/number | sub-total of the amount 
| `cgst_amount` | 180 | int/float/number | cgst amount to be applied
| `igst_amount` | 180 | int/float/number | igst to be applied
| `sgst_amount` | 0 | int/float/number | sgst to be applied
| `total` | 1360 | int/float/number | total amount 
| `timezone` | Asia/Kolkata | string | timezone 

- `buyer`

| Key | Value | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
| `gst_number` | 33AAECT8346F1ZB | string | gst number of the buyer

- `seller`

| Key | Value | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
| `gst_number` | 07BOXPS1970R1ZM | string | gst number of the seller

| Key | Value | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
| `po_number` | | string | |

- `grn` 

| Key | Value | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
| `grn_no` | | | |
| `grn_date` | 234324234 | int/float/number | |
| `doc_ref` | | string | |

- `payment`

| Key | Value | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
| `utr_number` | UTR | string | |
| `payment_method` | METHOD | string | |
| `payment_date` | 3244234 | int/float/number | |
| `amount` | 2334 | int/float/number | |

| Key | Value | Data Type | Description |
| ----------- | ----------- | ------------| ----------- |
| `stage_completed` | | | |
| `irn` | | | |
| `narration` | | | |
| `moratium` | 2 | | |

-----
## Response Example

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

- **403 - Forbidden** 
```json
{
    "message": "Customer with GST is already exists with this Office",
    "success": false,
    "code": 403
}
```

### Please refer for more detailed errors list ([click here](./errors.md#create)).
