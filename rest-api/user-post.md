
# POST : {apiKey}/users 

### *Description:* 
Asynchronously inserts new user resource into the system. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***createUserParams*** - Required (object). An user object that needs to be inserted into the system. 
***Please check the [Available Object Definitions](#available-object-definitions) documentation part for more details on expected structure of objects referred by the current parameter!***

```
 {
  "required": [
    "confirmPassword",
    "email",
    "password",
    "userName"
  ],
  "properties": {
    "autoCreatePassword": {
      "type": "boolean"
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
    "sendEmailNotification": {
      "type": "boolean"
    },
    "userName": {
      "type": "string"
    },
    "allowDashboardAccess": {
      "type": "boolean"
    },
    "dashboardSettings": {
      "type": "object"
    },
    "creationDate": {
      "type": "ISO 8601 Format"
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

* * *
### *Response Codes:*


- ***201  Created*** 

 New user resource has been successfully saved into the system. 
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

- ***400  Bad Request*** 

 Requested action could not be understood by the system. 


- ***401  Unauthorized*** 

 Requested action requires authentication. 


- ***403  Forbidden*** 

 System refuses to fulfill the requested action. 


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

tion.html).

