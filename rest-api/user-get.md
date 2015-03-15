
# GET : {apiKey}/users/{username} 

### *Description:* 
Asynchronously retrieves previously created user resource from the system. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***embed*** - Optional (string). Comma separated list of resources to be contained within the current representation. 


- ***username*** - Required (string). A login name which uniquely identifies an application user whose account information needs to be updated. 


* * *
### *Response Codes:*


- ***200  OK*** 

 User resource is successfully retrieved from the system. 
 ***Please check the [Available Object Definitions](#available-object-definitions) documentation part for more details on the available embeds!*** 

```
 {
  "required": [],
  "properties": {
    "creationDate": {
      "type": "ISO 8601 Format"
    },
    "email": {
      "type": "string"
    },
    "isApproved": {
      "type": "boolean"
    },
    "isLockedOut": {
      "type": "boolean"
    },
    "name": {
      "type": "string"
    },
    "roles": {
      "type": "array",
      "items": {
        "$ref": "Available Object Definitions / role"
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
      "roles"
    ]
  }
} 

```

- ***204  No Content*** 

 Requested action has been successfully processed, but the response is intentionally blank. 


- ***400  Bad Request*** 

 Requested action could not be understood by the system. 


- ***401  Unauthorized*** 

 Requested action requires authentication. 


- ***403  Forbidden*** 

 System refuses to fulfill the requested action. 


- ***404  Not Found*** 

 Specified user resource does not exist in the system. 


- ***500  Internal Server Error*** 

 A generic error has occurred on the system. 



* * *
### *Available Object Definitions:*

***role***

```
 {
    "required": [
      "name"
    ],
    "properties": {
      "description": {
        "type": "string"
      },
      "name": {
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
      "embed": {
        "type": "array",
        "items": {
          "type": "string"
        }
      }
    }
 }
```
* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

html).

