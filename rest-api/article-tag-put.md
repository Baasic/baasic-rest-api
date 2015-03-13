
# PUT : {apiKey}/article-tags/{id} 

### *Description:* 
Asynchronously updates previously created article tag resource. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***tag*** - Required (object). Aa article tag object used to update specified article tag resource. 

```
 {
  "required": [
    "tag"
  ],
  "properties": {
    "slug": {
      "type": "string"
    },
    "sortOrder": {
      "type": "integer"
    },
    "tag": {
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

- ***id*** - Required (string). Article slug which uniquely identifies article tag resource that needs to be updated. 


* * *
### *Response Codes:*


- ***200  OK*** 

 Existing article tag resource has been successfully updated. The response contains the result of the action. 

```
 {
  "required": [
    "tag"
  ],
  "properties": {
    "slug": {
      "type": "string"
    },
    "sortOrder": {
      "type": "integer"
    },
    "tag": {
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

- ***400  Bad Request*** 

 Requested action could not be understood by the system. 


- ***401  Unauthorized*** 

 Requested action requires authentication. 


- ***403  Forbidden*** 

 System refuses to fulfill the requested action. 


- ***404  Not Found*** 

 Specified article tag resource does not exist in the system. 


- ***409  Conflict*** 

 Requested action could not be carried out because of a conflict in the system. 


- ***500  Internal Server Error*** 

 A generic error has occurred on the system. 



* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

