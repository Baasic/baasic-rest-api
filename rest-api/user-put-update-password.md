
# PUT : {apiKey}/users/{username}/change-password 

### *Description:* 
Asynchronously updates user&#39;s password selection. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***recoveryParams*** - Required (object). A password recovery object used to update specified user&#39;s password selection. 

```
 {
  "required": [
    "newPassword"
  ],
  "properties": {
    "newPassword": {
      "type": "string"
    },
    "sendMailNotification": {
      "type": "boolean"
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

- ***username*** - Required (string). A login name which uniquely identifies an application user whose password selection needs to be updated. 


* * *
### *Response Codes:*


- ***200  OK*** 

 User&#39;s password selection has been successfully updated. 


- ***400  Bad Request*** 

 Requested action could not be understood by the system. 


- ***401  Unauthorized*** 

 Requested action requires authentication. 


- ***403  Forbidden*** 

 System refuses to fulfill the requested action. 


- ***404  Not Found*** 

 Specified user resource does not exist in the system. 


- ***409  Conflict*** 

 Requested action could not be carried out because of a conflict in the system. 


- ***500  Internal Server Error*** 

 A generic error has occurred on the system. 



* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

