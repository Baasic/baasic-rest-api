
# GET : {apiKey}/lookups 

### *Description:* 
Asynchronously retrieves previously created lookup schema resource from the system. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***embed*** - Optional (string). Comma separated list of related resources to be contained within the current representation. 


* * *
### *Response Codes:*


- ***200  OK*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Lookup schema resource is successfully retrieved from the system. 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ***Please check the [Available Object Definitions](#available-object-definitions) documentation part for more details on the available embeds!***

```
 {
  "required": [],
  "properties": {
    "accessAction": {
      "type": "array",
      "items": {
        "$ref": "Available Object Definitions / accessActionModel"
      }
    },
    "accessSection": {
      "type": "array",
      "items": {
        "$ref": "Available Object Definitions / accessSectionModel"
      }
    },
    "role": {
      "type": "array",
      "items": {
        "$ref": "Available Object Definitions / roleModel"
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
      "accessAction",
      "accessSection",
      "role"
    ]
  }
} 

```

- ***400  Bad Request*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested action could not be understood by the system. 


- ***401  Unauthorized*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested action requires authentication. 


- ***403  Forbidden*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; System refuses to fulfill the requested action. 


- ***500  Internal Server Error*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; A generic error has occurred on the system. 



* * *
### *Available Object Definitions:*

***accessActionModel***

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
      "id": {
        "type": "UID"
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
      "embed": {
        "type": "array",
        "items": {
          "type": "string"
        }
      }
    }
 }
```
***accessSectionModel***

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
      "id": {
        "type": "UID"
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
      "embed": {
        "type": "array",
        "items": {
          "type": "string"
        }
      }
    }
 }
```
***roleModel***

```
 {
    "required": [],
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

