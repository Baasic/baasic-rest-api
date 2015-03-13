
# POST : {apiKey}/resources/{schemaName} 

### *Description:* 
Asynchronously inserts new dynamic resource into the system. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***resource*** - Required (object). A dynamic resource object that needs to be inserted into the system. 

```
 {
  "required": [],
  "properties": {}
} 

```

- ***schemaName*** - Required (string). Name of dynamic schema that needs to be updated with new dynamic resource. 


* * *
### *Response Codes:*


- ***200  OK*** 

 Dynamic entry resource is successfully inserted into the system. 

```
 {
  "required": [],
  "properties": {
    "embed": [],
    "id": {
      "type": "string"
    }
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
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

