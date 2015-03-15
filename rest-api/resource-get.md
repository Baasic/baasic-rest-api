
# GET : {apiKey}/resources/{schemaName}/{id} 

### *Description:* 
Asynchronously retrieves previously created dynamic resource from the system. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***embed*** - Optional (string). Comma separated list of resources to be contained within the current representation. 


- ***id*** - Required (string). A value which uniquely identifies dynamic resource that needs to be retrieved. 


- ***schemaName*** - Required (string). Name of dynamic schema whose dynamic resource needs to be retrieved. 


* * *
### *Response Codes:*


- ***200  OK*** 

 Dynamic entry resource is successfully retrieved from the system. 

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


- ***404  Not Found*** 

 Specified dynamic entry resources do not exist in the system. 


- ***500  Internal Server Error*** 

 A generic error has occurred on the system. 



* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

