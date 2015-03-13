
# GET : {apiKey}/articles/{articleId}/users/{username}/ratings 

### *Description:* 
Asynchronously retrieves article rating resources by specified search criteria. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***embed*** - Optional (string). Comma separated list of resources to be contained within the current representation. 


- ***username*** - Required (string). Author of the article rating resources to be retrieved. 


- ***articleId*** - Required (string). Value which identifies article whose rating resources need to be retrieved. 


* * *
### *Response Codes:*


- ***200  OK*** 

 Article rating resource subset is successfully retrieved from the system. 
 ***Please check the [Available Object Definitions](#available-object-definitions) documentation part for more details on the available embeds!*** 

```
 {
  "required": [],
  "properties": {
    "embed": {
      "type": "string"
    },
    "item": {
      "type": "array",
      "items": {
        "$ref": "#/definitions/articleRating"
      }
    },
    "page": {
      "type": "integer"
    },
    "recordsPerPage": {
      "type": "integer"
    },
    "searchQuery": {
      "type": "string"
    },
    "sort": {
      "type": "string"
    },
    "totalRecords": {
      "type": "integer"
    }
  },
  "definitions": {
    "articleRating": {
      "required": [
        "articleId",
        "rating",
        "userId"
      ],
      "properties": {
        "article": {
          "type": "Available Object Definitions / article"
        },
        "articleId": {
          "type": "UID"
        },
        "ratedOn": {
          "type": "ISO 8601 Format"
        },
        "rating": {
          "type": "integer"
        },
        "user": {
          "type": "Available Object Definitions / author"
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
        "embed": [
          "article",
          "user"
        ]
      }
    }
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

 Specified article and/or user resource do not exist in the system. 


- ***500  Internal Server Error*** 

 A generic error has occurred on the system. 



* * *
### *Available Object Definitions:*

***article***

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
        "type": "object"
      },
      "authorId": {
        "type": "UID"
      },
      "comments": {
        "type": "array",
        "items": {
          "type": "object"
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
          "type": "object"
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
          "type": "object"
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
      "embed": {
        "type": "array",
        "items": {
          "type": "string"
        }
      }
    }
 }
```
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
* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

