
# POST : {apiKey}/articles 

### *Description:* 
Asynchronously inserts new article resource into the system. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***article*** - Required (object). An article object that needs to be inserted into the system. 
***Please check the [Available Object Definitions](#available-object-definitions) documentation part for more details on expected structure of objects referred by the current parameter!***

```
 {
  "required": [],
  "properties": {
    "allowComments": {
      "type": "boolean"
    },
    "archiveDate": {
      "type": "ISO 8601 Format"
    },
    "author": {
      "type": "Available Object Definitions / author"
    },
    "authorId": {
      "type": "UID"
    },
    "comments": {
      "type": "array",
      "items": {
        "$ref": "Available Object Definitions / comment"
      }
    },
    "content": {
      "type": "string"
    },
    "publishDate": {
      "type": "ISO 8601 Format"
    },
    "ratings": {
      "type": "array",
      "items": {
        "$ref": "Available Object Definitions / rating"
      }
    },
    "slug": {
      "type": "string"
    },
    "status": {
      "type": "integer"
    },
    "tags": {
      "type": "array",
      "items": {
        "$ref": "Available Object Definitions / tag"
      }
    },
    "title": {
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
    "embed": [
      "author",
      "comments",
      "ratings",
      "tags"
    ]
  }
} 

```

* * *
### *Response Codes:*


- ***201  Created*** 

 New article resource has been successfully saved into the system. 
 ***Please check the [Available Object Definitions](#available-object-definitions) documentation part for more details on the available embeds!*** 

```
 {
  "required": [],
  "properties": {
    "allowComments": {
      "type": "boolean"
    },
    "archiveDate": {
      "type": "ISO 8601 Format"
    },
    "author": {
      "type": "Available Object Definitions / author"
    },
    "authorId": {
      "type": "UID"
    },
    "comments": {
      "type": "array",
      "items": {
        "$ref": "Available Object Definitions / comment"
      }
    },
    "content": {
      "type": "string"
    },
    "publishDate": {
      "type": "ISO 8601 Format"
    },
    "ratings": {
      "type": "array",
      "items": {
        "$ref": "Available Object Definitions / rating"
      }
    },
    "slug": {
      "type": "string"
    },
    "status": {
      "type": "integer"
    },
    "tags": {
      "type": "array",
      "items": {
        "$ref": "Available Object Definitions / tag"
      }
    },
    "title": {
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
    "embed": [
      "author",
      "comments",
      "ratings",
      "tags"
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

***author***

```
 {
    "required": [
      "id"
    ],
    "properties": {
      "displayName": {
        "type": "string"
      },
      "id": {
        "type": "UID"
      },
      "dateCreated": {
        "type": "ISO 8601 Format"
      },
      "dateUpdated": {
        "type": "ISO 8601 Format"
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
***comment***

```
 {
    "required": [],
    "properties": {
      "articleId": {
        "type": "UID"
      },
      "author": {
        "type": "string"
      },
      "comment": {
        "type": "string"
      },
      "email": {
        "type": "string"
      },
      "isApproved": {
        "type": "boolean"
      },
      "isSpam": {
        "type": "boolean"
      },
      "userId": {
        "type": "UID"
      },
      "website": {
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
***rating***

```
 {
    "required": [],
    "properties": {
      "articleId": {
        "type": "UID"
      },
      "rating": {
        "type": "integer"
      },
      "userId": {
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
      "embed": {
        "type": "array",
        "items": {
          "type": "string"
        }
      }
    }
 }
```
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

p://stateless.co/hal_specification.html).

