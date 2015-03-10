
# POST : {apiKey}/recover-password 

### *Description:* 
Asynchronously initiates a password recovery process for the specified user. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***passwordRecoveryParams*** - Required (object). A password recovery object which contains parameters required for the password retrieval request: challenge identifier, challenge response, username and recovery url. 

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

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; A password recovery process has been successfully initiated. 


- ***400  Bad Request*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested action could not be understood by the system. 


- ***401  Unauthorized*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested action requires authentication. This response code will be returned if current user doesn&#39;t have required UPDATE permissions and tries to initiate a password recovery process for user without meeting one of the bellow requirements: 
 1. Challenge identifier or response is not specified or 
 2. Captcha challenge request has failed, i.e. challenge response in not valid. 
 3. User is not approved. 


- ***403  Forbidden*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; System refuses to fulfill the requested action. 


- ***404  Not Found*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Specified user does not exist in the system. 


- ***409  Conflict*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested action could not be carried out because of a conflict in the system. 


- ***500  Internal Server Error*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; A generic error has occurred on the system. 



* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

-  If request succeeds, a password retrieval request will be initiated which will send a confirmation link to the email address associated with the specified user. 
