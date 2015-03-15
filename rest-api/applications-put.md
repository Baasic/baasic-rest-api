
# PUT : {apiKey}/applications 

### *Description:* 
Asynchronously updates previously created application resource. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***application*** - Required (object). An application object used to update existing application settings. 

```
 {
  "required": [
    "applicationTitle"
  ],
  "properties": {
    "allowAnyOrigin": {
      "type": "boolean"
    },
    "allowUserRegistration": {
      "type": "boolean"
    },
    "applicationTitle": {
      "type": "string"
    },
    "identifier": {
      "type": "string"
    },
    "isActive": {
      "type": "boolean"
    },
    "mailFromAddress": {
      "type": "string"
    },
    "origins": {
      "type": "array",
      "items": {
        "type": "string"
      }
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


- ***200  OK*** 

 Application resource has been successfully updated. 


- ***400  Bad Request*** 

 Requested action could not be understood by the system. 


- ***401  Unauthorized*** 

 Requested action requires authentication. 


- ***403  Forbidden*** 

 System refuses to fulfill the requested action. 


- ***404  Not Found*** 

 Required application resource does not exist in the system. 


- ***409  Conflict*** 

 Requested action could not be carried out because of a conflict in the system. 


- ***500  Internal Server Error*** 

 A generic error has occurred on the system. 


* * *
### *Code Examples:*



***CURL***
  
 ```
  curl 
   -H Authorization:"forms token"
   -H Content-Type:application/json  
   -X PUT 
   -d '{"allowAnyOrigin":true,"allowUserRegistration":true,"applicationTitle":"My application","identifier":"apiKey","isActive":true,"mailFromAddress":"myApp@domain.com","origins":[]}' 
   -v 
   https://api.baasic.com/v1/apiKey/applications/
  ```   

* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

