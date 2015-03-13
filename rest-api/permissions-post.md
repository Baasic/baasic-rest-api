
# POST : {apiKey}/permissions 

### *Description:* 
Asynchronously inserts new access policy into the system. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***policy*** - Required (object). An access policy object that needs to be inserted into the system. This object specifies parameters
            necessary for establishing user and/or role set of rights. 
***Please check the [Available Object Definitions](#available-object-definitions) documentation part for more details on expected structure of objects referred by the current parameter!***

```
 {
  "required": [],
  "properties": {
    "actions": {
      "type": "array",
      "items": {
        "$ref": "Available Object Definitions / accessAction"
      }
    },
    "name": {
      "type": "string"
    },
    "role": {
      "type": "string"
    },
    "section": {
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
    "embed": [
      "actions"
    ]
  }
} 

```

* * *
### *Response Codes:*


- ***201  Created*** 

 New access policy has been successfully established for the specified user and/or role. 
 ***Please check the [Available Object Definitions](#available-object-definitions) documentation part for more details on the available embeds!*** 

```
 {
  "required": [],
  "properties": {
    "embed": {
      "type": "string"
    },
    "item": {
      "type": "array",
      "items": {
        "$ref": "#/definitions/accessPolicy"
      }
    },
    "page": {
      "type": "integer"
    },
    "recordsPerPage": {
      "type": "integer"
    },
    "searchQuery": {
      "type": "string"
    },
    "sort": {
      "type": "string"
    },
    "totalRecords": {
      "type": "integer"
    }
  },
  "definitions": {
    "accessPolicy": {
      "required": [],
      "properties": {
        "actions": {
          "type": "array",
          "items": {
            "$ref": "Available Object Definitions / accessAction"
          }
        },
        "name": {
          "type": "string"
        },
        "role": {
          "type": "string"
        },
        "section": {
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
        "embed": [
          "actions"
        ]
      }
    }
  }
} 

```

- ***400  Bad Request*** 

 Requested action could not be understood by the system. 


- ***401  Unauthorized*** 

 Requested action requires authentication. 


- ***403  Forbidden*** 

 System refuses to fulfill the requested action because of insufficient privileges. 


- ***409  Conflict*** 

 Requested action could not be carried out because of a conflict in the system. 


- ***500  Internal Server Error*** 

 A generic error has occurred on the system. 



* * *
### *Available Object Definitions:*

***accessAction***

```
 {
    "required": [],
    "properties": {
      "abrv": {
        "type": "string"
      },
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

