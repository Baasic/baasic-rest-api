
# GET : {apiKey}/value-sets/{id} 

### *Description:* 
Asynchronously retrieves previously created value set resource from the system. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***embed*** - Optional (string). Comma separated list of resources to be contained within the current representation. 


- ***id*** - Required (string). Name which uniquely identifies value set resource that needs to be retrieved. 


* * *
### *Response Codes:*


- ***200  OK*** 

 Value set resource is successfully retrieved from the system. 
 ***Please check the [Available Object Definitions](#available-object-definitions) documentation part for more details on the available embeds!*** 

```
 {
  "required": [
    "name"
  ],
  "properties": {
    "values": {
      "type": "array",
      "items": {
        "$ref": "Available Object Definitions / valueSetItem"
      }
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
    "embed": [
      "values"
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

 Specified value set resource does not exist in the system. 


- ***500  Internal Server Error*** 

 A generic error has occurred on the system. 



* * *
### *Available Object Definitions:*

***valueSetItem***

```
 {
    "required": [
      "value"
    ],
    "properties": {
      "setId": {
        "type": "UID"
      },
      "setName": {
        "type": "string"
      },
      "value": {
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

