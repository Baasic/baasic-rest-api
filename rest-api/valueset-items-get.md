
# GET : {apiKey}/value-sets/{setId}/items/{id} 

### *Description:* 
Asynchronously retrieves previously created value set item resource from the system. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***id*** - Required (string). Value which uniquely identifies value set item resource that needs to be retrieved. 


- ***setId*** - Required (string). Value set name whose item needs to be retrieved. 


* * *
### *Response Codes:*


- ***200  OK*** 

 Value set item resource is successfully retrieved from the system. 

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

 Requested action could not be understood by the system. 


- ***401  Unauthorized*** 

 Requested action requires authentication. 


- ***403  Forbidden*** 

 System refuses to fulfill the requested action. 


- ***404  Not Found*** 

 Specified value set item resource does not exist in the system. 


- ***500  Internal Server Error*** 

 A generic error has occurred on the system. 



* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

