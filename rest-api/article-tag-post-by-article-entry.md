
# POST : {apiKey}/articles/{articleId}/tags 

### *Description:* 
Asynchronously inserts new article tag resource into the system. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***entry*** - Required (object). An article tag object that needs to be inserted into the system. 
***Please check the [Available Object Definitions](#available-object-definitions) documentation part for more details on expected structure of objects referred by the current parameter!***

```
 {
  "required": [],
  "properties": {
    "articleId": {
      "type": "UID"
    },
    "tag": {
      "type": "Available Object Definitions / tag"
    },
    "tagId": {
      "type": "UID"
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
    "embed": [
      "tag"
    ]
  }
} 

```

- ***articleId*** - Required (string). Value which uniquely identifies article that needs to be updated with new article tag resource. 


* * *
### *Response Codes:*


- ***201  Created*** 

 New article tag resource has been successfully saved into the system. 
 ***Please check the [Available Object Definitions](#available-object-definitions) documentation part for more details on the available embeds!*** 

```
 {
  "required": [],
  "properties": {
    "articleId": {
      "type": "UID"
    },
    "tag": {
      "type": "Available Object Definitions / tag"
    },
    "tagId": {
      "type": "UID"
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
    "embed": [
      "tag"
    ]
  }
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
### *Available Object Definitions:*

***tag***

```
 {
    "required": [],
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
      "embed": {
        "type": "array",
        "items": {
          "type": "string"
        }
      }
    }
 }
```
* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

tion.html).

