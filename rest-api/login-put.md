
# PUT : {apiKey}/login 

### *Description:* 
Asynchronously refreshes previously created authentication token. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***updateParams*** - Required (object). Authentication token that needs to be refreshed. 

```
 {
  "required": [
    "token",
    "type"
  ],
  "properties": {
    "token": {
      "type": "string"
    },
    "type": {
      "type": "string"
    }
  }
} 

```

* * *
### *Response Codes:*


- ***200  OK*** 

 Existing authentication token resource has been successfully refreshed. 


- ***400  Bad Request*** 

 Requested action could not be understood by the system. This response code is usually returned due to the invalid or expired authentication token. 


- ***401  Unauthorized*** 

 Requested action requires authentication. 


- ***403  Forbidden*** 

 System refuses to fulfill the requested action. 


- ***404  Not Found*** 

 Specified authentication token does not exist in the system. 


- ***409  Conflict*** 

 Requested action could not be carried out because of a conflict in the system. 


- ***500  Internal Server Error*** 

 A generic error has occurred on the system. 



* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

