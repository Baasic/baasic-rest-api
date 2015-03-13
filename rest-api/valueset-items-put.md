
# PUT : {apiKey}/value-sets/{setId}/items/{id} 

### *Description:* 
Asynchronously updates previously created value set item resource. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***valueSetItem*** - Required (object). A value set item object used to update specified value set item resource. 

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

- ***id*** - Required (string). Value which uniquely identifies value set item resource that needs to be updated. 


- ***setId*** - Required (string). Name of value set whose item needs to be updated. 


* * *
### *Response Codes:*


- ***204  No Content*** 

 Existing value set item resource has been successfully updated. 


- ***400  Bad Request*** 

 Requested action could not be understood by the system. 


- ***401  Unauthorized*** 

 Requested action requires authentication. 


- ***403  Forbidden*** 

 System refuses to fulfill the requested action. 


- ***404  Not Found*** 

 Specified value set resource does not exist in the system. 


- ***409  Conflict*** 

 Requested action could not be carried out because of a conflict in the system. 


- ***500  Internal Server Error*** 

 A generic error has occurred on the system. 



* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

