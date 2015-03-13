
# GET : {apiKey}/login 

### *Description:* 
Asynchronously retrieves the account information of the user who is currently logged in. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***embed*** - Optional (string). Comma separated list of resources to be contained within the current representation. 


* * *
### *Response Codes:*


- ***200  OK*** 

 User account information is successfully retrieved from the system. 

```
 {
  "required": [],
  "properties": {
    "displayName": {
      "type": "string"
    },
    "email": {
      "type": "string"
    },
    "permissions": {
      "type": "object",
      "description": "Represents a collection of key and value pairs. Within a collection, the keys are section abbreviations which identify separate parts of the application, while the values are represented by predetermined access policies, i.e list of action abbreviations."
    },
    "roles": {
      "type": "array",
      "items": {
        "type": "string"
      }
    },
    "userName": {
      "type": "string"
    },
    "dateCreated": {
      "type": "ISO 8601 Format"
    },
    "dateUpdated": {
      "type": "ISO 8601 Format"
    },
    "id": {
      "type": "UID"
    },
    "embed": [
      "permissions"
    ]
  }
} 

```

- ***400  Bad Request*** 

 Requested action could not be understood by the system. 


- ***401  Unauthorized*** 

 Requested action requires authentication. 


- ***403  Forbidden*** 

 System refuses to fulfill the requested action. 


- ***404  Not Found*** 

 Required account information cannot be found in the system. 


- ***500  Internal Server Error*** 

 A generic error has occurred on the system. 



* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

