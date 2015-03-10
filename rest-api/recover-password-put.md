
# PUT : {apiKey}/recover-password 

### *Description:* 
Asynchronously updates user&#39;s password selection. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***recoveryParams*** - Required (object). Password recovery object used to update user&#39;s current password selection. 

```
 {
  "required": [
    "newPassword",
    "passwordRecoveryToken"
  ],
  "properties": {
    "newPassword": {
      "type": "string"
    },
    "passwordRecoveryToken": {
      "type": "string"
    }
  }
} 

```

* * *
### *Response Codes:*


- ***200  OK*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; User&#39;s password selection has been successfully updated. 


- ***400  Bad Request*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested action could not be understood by the system. 


- ***401  Unauthorized*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested action requires authentication. 


- ***403  Forbidden*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; System refuses to fulfill the requested action. 


- ***409  Conflict*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested action could not be carried out because of a conflict in the system. 


- ***500  Internal Server Error*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; A generic error has occurred on the system. 



* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

