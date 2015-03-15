
# POST : {apiKey}/recover-password 

### *Description:* 
Asynchronously initiates a password recovery process for the specified user. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***passwordRecoveryParams*** - Required (object). A password recovery object which contains parameters required for the password retrieval request: challenge
            identifier, challenge response, username and recovery url. 

```
 {
  "required": [
    "recoverUrl",
    "userName"
  ],
  "properties": {
    "challengeIdentifier": {
      "type": "string"
    },
    "challengeResponse": {
      "type": "string"
    },
    "recoverUrl": {
      "type": "string"
    },
    "userName": {
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

* * *
### *Response Codes:*


- ***201  Created*** 

 A password recovery process has been successfully initiated. 


- ***400  Bad Request*** 

 Requested action could not be understood by the system. 


- ***401  Unauthorized*** 

 Requested action requires authentication. 


- ***403  Forbidden*** 

 System refuses to fulfill the requested action. 


- ***404  Not Found*** 

 Specified user does not exist in the system. 


- ***409  Conflict*** 

 Requested action could not be carried out because of a conflict in the system. 


- ***500  Internal Server Error*** 

 A generic error has occurred on the system. 



* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

-  If request succeeds, a password retrieval request will be initiated which will send a confirmation link to
  the email address associated with the specified user. 
