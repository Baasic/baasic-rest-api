
# POST : {apiKey}/schemas/generate 

### *Description:* 
Asynchronously generates dynamic schema from the specified JSON object. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***jsonObject*** - Required (object). Unordered collection of key value pairs used to specify dynamic schema definition. 

```
 {
  "required": [],
  "properties": {}
} 

```

* * *
### *Response Codes:*


- ***201  Created*** 

 JSON based dynamic schema has been successfully generated. 

```
 {
  "required": [],
  "properties": {}
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

