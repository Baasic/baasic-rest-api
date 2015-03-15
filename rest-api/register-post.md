
# POST : {apiKey}/register 

### *Description:* 
Asynchronously inserts new user account resource into the system, i.e. creates new user in the current application. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***createUserParams*** - Required (object). A user account object that needs to be inserted into the system. 

```
 {
  "required": [
    "activationUrl",
    "challengeIdentifier",
    "challengeResponse",
    "confirmPassword",
    "email",
    "password",
    "userName"
  ],
  "properties": {
    "activationUrl": {
      "type": "string"
    },
    "challengeIdentifier": {
      "type": "string"
    },
    "challengeResponse": {
      "type": "string"
    },
    "confirmPassword": {
      "type": "string"
    },
    "email": {
      "type": "string"
    },
    "password": {
      "type": "string"
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
    "embed": []
  }
} 

```

* * *
### *Response Codes:*


- ***200  OK*** 

 New user account resource has been successfully saved into the system. 
 ***Please check the [Available Object Definitions](#available-object-definitions) documentation part for more details on the available embeds!*** 

```
 {
  "required": [],
  "properties": {
    "creationDate": {
      "type": "ISO 8601 Format"
    },
    "dashboardSettings": {
      "type": "object"
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
    "id": {
      "type": "UID"
    },
    "dateCreated": {
      "type": "ISO 8601 Format"
    },
    "dateUpdated": {
      "type": "ISO 8601 Format"
    },
    "embed": [
      "roles"
    ]
  }
} 

```

- ***400  Bad Request*** 

 Requested action could not be understood by the system. Please check Captcha challenge request. 


- ***401  Unauthorized*** 

 Requested action requires authentication. 


- ***403  Forbidden*** 

 System refuses to fulfill the requested action. If User Registration is not enabled for the current application, requested action will be refused. 


- ***409  Conflict*** 

 Requested action could not be carried out because of a conflict in the system. 


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

