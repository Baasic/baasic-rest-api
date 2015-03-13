
# GET : {apiKey}/value-sets 




* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***embed*** - Optional (string).  


- ***sort*** - Optional (string).  


- ***rpp*** - Optional (integer).  


- ***page*** - Optional (integer).  


- ***searchQuery*** - Optional (string).  


* * *
### *Response Codes:*


- ***200  OK*** 

 Value set resource subset is successfully retrieved from the system. 
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
        "$ref": "#/definitions/valueSet"
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
    "valueSet": {
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

 Specified value set resource subset does not exist in the system. 


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

s. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

