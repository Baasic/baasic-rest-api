
# GET : {apiKey}/article-ratings 

### *Description:* 
Asynchronously retrieves previously created article rating resource by specified article rating&#39;s author. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***embed*** - Optional (string). Comma separated list of resources to be contained within the current representation. 


- ***sort*** - Optional (string). A string used to set the article rating property to sort the result collection by. For complete list of
            available properties, see the JSON representation of article rating object under the Response Codes section. 


- ***rpp*** - Optional (integer). A value used to limit the size of result set per page. 


- ***page*** - Optional (integer). A value used to se the page size, i.e. to retrieve certain article rating subset from the storage. 


- ***username*** - Required (string). A value that uniquely identifies a user which has created an article rating. 


* * *
### *Response Codes:*


- ***200  OK*** 

 Article rating subset is successfully retrieved from the system. 
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

- ***204  No Content*** 

 Requested action has been successfully processed, but the response is intentionally blank. 


- ***400  Bad Request*** 

 Requested action could not be understood by the system. 


- ***401  Unauthorized*** 

 Requested action requires authentication. 


- ***403  Forbidden*** 

 System refuses to fulfill the requested action. 


- ***404  Not Found*** 

 Specified article rating resource does not exist in the system. 


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

