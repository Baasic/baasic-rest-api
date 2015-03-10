
# GET : {apiKey}/permissions/actions 

### *Description:* 
Asynchronously retrieves access action resources that match the specified search string. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***sort*** - Optional (string). A string used to set the permission property to sort the result collection by. 


- ***searchQuery*** - Optional (string). Only access actions whose name abbreviation matches a search string will be listed. 


* * *
### *Response Codes:*


- ***200  OK*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Access action resource subset is successfully retrieved from the system. 

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
        "$ref": "#/definitions/accessAction"
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
    "accessAction": {
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
        "embed": []
      }
    }
  }
} 

```

- ***204  No Content*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested action has been successfully processed, but the response is intentionally blank. 


- ***400  Bad Request*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested action could not be understood by the system. 


- ***401  Unauthorized*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested action requires authentication. 


- ***403  Forbidden*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; System refuses to fulfill the requested action. 


- ***404  Not Found*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Specified access action resource subset does not exist in the system. 


- ***500  Internal Server Error*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; A generic error has occurred on the system. 



* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

-  System supports basic CRUD access policies: "Create", "Delete", "Read" and "Update". 
