
# GET : {apiKey}/schemas/{schemaName} 

### *Description:* 
Asynchronously retrieves previously created dynamic schema resource from the system. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***embed*** - Optional (string). Comma separated list of resources to be contained within the current representation. 


- ***schemaName*** - Required (string). Name which uniquely identifies dynamic schema resource that needs to be retrieved. 


* * *
### *Response Codes:*


- ***200  OK*** 

 Dynamic schema resource is successfully retrieved from the system. 
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

- ***204  No Content*** 

 Requested action has been successfully processed, but the response is intentionally blank. 


- ***400  Bad Request*** 

 Requested action could not be understood by the system. 


- ***401  Unauthorized*** 

 Requested action requires authentication. 


- ***403  Forbidden*** 

 System refuses to fulfill the requested action. 


- ***404  Not Found*** 

 Specified dynamic schema resource does not exist in the system. 


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

