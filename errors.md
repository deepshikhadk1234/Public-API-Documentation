# Error Listings for APIs

| ERRORs LISTED | Error Description | Errors in Templates|
|-------------|--------------|---------|
| `${METHOD} is not allowed for the /activities endpoint. Use POST/PUT/PATCH` | For Different Method Type | Demand / customer |
| `The 'timestamp' field is missing from the request body.` | Timestamp is missing | Demand / customer
| `The 'timestamp' field should be a number.` | Timestamp is other than Number (string, etc) | Demand / customer
| `The 'timestamp' in the request body is invalid.` | Timestamp is inValid. | Demand / customer |

## Create/Demand
----
| ERRORs LISTED | Error Description | Errors in Templates|
|-------------|--------------|---------|
|
`The 'template' field is missing from the request body.` | Template is Mandatory in the Request Body. | Demand/Customer 
| `Expected 'template' field to have a value of type 'string'. Found ${typeof body.template}.` | Template should be type String. | Demand / customer
| `The 'gstNumber' field is missing from the request body's attachment.` | gstNumber is Mandatory in Request Body’s Attachment. | Demand / customer
| `The 'gstNumber' field is Invalid.` | gstNumber is invalid | customer
| `The 'firstContactEmail' field is missing from the request body's attachment.` | firstContactEmail is Mandatory in Request Body’s Attachment. | customer |
| `The 'firstContactEmail' is Invalid.` | firstContactEmail contains an Invalid Mail. | customer |
| `The 'firstContactName' field is missing from the request body's attachment.` | firstContactName is Mandatory in Request Body’s Attachment. | customer 
| `The 'firstContactName' field should be a non-empty string.` | firstContactName should be non-Empty. | customer
| `The 'firstContact' field is missing from the request body's attachment.` | firstContact ~ phone is Mandatory in Request Body’s Attachment. | customer
| `'${body.attachment.firstContact}' is Invalid.` | firstContact ~ phone is Invalid. | customer
| `Either SGST, CGST, IGST field is missing from the request body's attachment.` | Taxes, i.e. SGST, CGST, IGST is Mandatory in Request Body’s Attachment. | demand 
| `The 'dueDate' field is missing from the request body's attachment.` | dueDate is Mandatory in Request Body’s Attachment. | demand
| `The 'totalAmount' field is missing from the request body's attachment.` | totalAmount is Mandatory in Request Body’s Attachment. | demand
| `The 'name' field is missing from the request body's attachment.` | Name is Mandatory in Request Body’s Attachment. |demand
| `The 'office' field is missing from the request body.` | Office field is mandatory. | Demand/customer
| `The 'office' field should be a non-empty string. | Office is mandatory. i.e. Contains Office Name | Demand/customer
| `The 'share' field is missing from the request body.` | Share is missing from Request Body. | Demand/customer
| `The field 'attachment' is missing from the request body.` | Attachment is missing from Request Body. | Demand/customer
| The 'share' field in the request body should be an 'array'. | Share field should be in Array Format Containing Numbers. [ Created by Locals ] | Demand/create
| `${phoneNumber} is invalid. Please contact support` | PhoneNumber is not Valid | Demand/create



## Update

| ERRORs LISTED | Error Description | Errors in Templates|
|-------------|--------------|---------|
| `The 'activityId' field is missing from the request body.` | activityId is missing from the Request Body. | Demand
| `The 'activityId' field should be a non-empty string.` | activityId should be non-empty | Demand
|` The request body has no usable fields. Please add at least any of these: , 'schedule', 'venue' or 'attachment' in the request body to make a successful request.` | schedule, venue, attachment is missing from the Request Body. | Demand / customer |










































