
# PATCH : {apiKey}/resources/{resourceName}/{id} 

### *Description:* 
Asynchronously updates previously created dynamic entry resource with partial content. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***resource*** - Required (object). Partial dynamic entry object used to update specified dynamic entry resource. 

```
 {
  "required": [],
  "properties": {}
} 

```

- ***id*** - Required (string). A value which uniquely identifies dynamic entry resource that needs to be partially updated. 


- ***resourceName*** - Required (string). Name of dynamic schema whose dynamic entry resource needs to be partially updated. 


* * *
### *Response Codes:*


- ***400  Bad Request*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested action could not be understood by the system. 


- ***401  Unauthorized*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested action requires authentication. 


- ***403  Forbidden*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; System refuses to fulfill the requested action. 


- ***404  Not Found*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Specified dynamic entry resources do not exist in the system. 


- ***409  Conflict*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested action could not be carried out because of a conflict in the system. 


- ***500  Internal Server Error*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; A generic error has occurred on the system. 



* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

