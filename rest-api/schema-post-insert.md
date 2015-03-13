
# POST : {apiKey}/schemas 

### *Description:* 
Asynchronously inserts new dynamic schema resource into the system. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***schema*** - Required (object). A dynamic schema object that needs to be inserted into the system. 
***Please check the [Available Object Definitions](#available-object-definitions) documentation part for more details on expected structure of objects referred by the current parameter!***

```
 {
  "required": [
    "name",
    "schema"
  ],
  "properties": {
    "description": {
      "type": "string"
    },
    "enforceSchemaValidation": {
      "type": "boolean"
    },
    "name": {
      "type": "string"
    },
    "owner": {
      "type": "Available Object Definitions / owner"
    },
    "ownerId": {
      "type": "UID"
    },
    "schema": {
      "type": "object"
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
      "owner"
    ]
  }
} 

```

* * *
### *Response Codes:*


- ***200  OK*** 

 New dynamic schema resource has been successfully saved into the system. 
 ***Please check the [Available Object Definitions](#available-object-definitions) documentation part for more details on the available embeds!*** 

```
 {
  "required": [
    "name",
    "schema"
  ],
  "properties": {
    "description": {
      "type": "string"
    },
    "enforceSchemaValidation": {
      "type": "boolean"
    },
    "name": {
      "type": "string"
    },
    "owner": {
      "type": "Available Object Definitions / owner"
    },
    "ownerId": {
      "type": "UID"
    },
    "schema": {
      "type": "object"
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
      "owner"
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

***owner***

```
 {
    "required": [
      "id"
    ],
    "properties": {
      "displayName": {
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

