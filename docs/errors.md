# Errors

The beginning of an awesome article...

### HTTP Errors

The table below contains a list of other HTTP Errors you may encounter with the API.

Error Code | Short Message | Interpretation 
---------|----------|---------
 415 | Unsupported Media Type | You have not set the Content-Type header to "application/json"
 401 | Unauthorized | API Key was not provided. To clear this error, set Authorization Header to  Bearer {{your-api-key}}.
 405 | Method Not Allowed | You are sending request with the wrong HTTP METHOD


#### Sample HTTP Error Response
HTTP Errors are returned as JSON objects with following structure

```json
{
    "errorCode": 404,
    "errorMessage": "Requested resource not available or may have been moved"
}
```


 ### Sync Errors
Sync Errors are returned when you encounter errors not related to your request but the content you have submitted to the API:

 Error Code | Short Message | Interpretation 
---------|----------|---------
 CE1000 | Empty Fields | One or more required fields have not been submitted or were sent empty
 CE1001 | Invalid Fields | One or more fields contains an invalid data type
 CE1100 | Invalid Field | The referenced field contains an invalid data type
 CE1102 | Invalid Field | The length of data is either too long or too short
   CE1103 | Unregistered Originator | The originator (numeric or alphanumeric) being used has not been registered
  CE1104 | Unapproved Originator | The originator (numeric or alphanumeric) being used is pending approval

#### Sample Sync Error Response

```json
{
    "code": "CE1100",
    "error": "Invalid Receiver. Receiver should be of format +2348050209037"
}
```
