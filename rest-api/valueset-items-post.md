
# POST : {apiKey}/value-sets/{setId}/items 

### *Description:* 
Asynchronously inserts new value set item resource into the system. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***valueSetItem*** - Required (object). A value set item object that needs to be inserted into the system. 

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
    "embed": []
  }
} 

```

- ***setId*** - Required (string). Name of value set that needs to be updated with new item. 


* * *
### *Response Codes:*


- ***201  Created*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; New value set item resource has been successfully saved into the system. The response contains the result of the action. 

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
    "embed": []
  }
} 

```

- ***400  Bad Request*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested action could not be understood by the system. 


- ***401  Unauthorized*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested action requires authentication. 


- ***403  Forbidden*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; System refuses to fulfill the requested action. 


- ***404  Not Found*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Specified value set resource does not exist in the system. 


- ***409  Conflict*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested action could not be carried out because of a conflict in the system. 


- ***500  Internal Server Error*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; A generic error has occurred on the system. 



* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

