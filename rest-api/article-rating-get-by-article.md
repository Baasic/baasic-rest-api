
# GET : {apiKey}/articles/{articleId}/ratings 

### *Description:* 
Asynchronously retrieves article rating resources by specified article identifier. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***embed*** - Optional (string). Comma separated list of resources to be contained within the current representation. 


- ***sort*** - Optional (string). A string used to set the article rating property to sort the result collection by. 


- ***rpp*** - Optional (integer). A value used to limit the size of result set per page. 


- ***page*** - Optional (integer). A value used to se the page size, i.e. to retrieve certain article rating subset from the storage. 


- ***articleId*** - Required (string). Value which uniquely identifies article whose rating resources need to be retrieved. 


* * *
### *Response Codes:*


- ***200  OK*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Article rating resource subset is successfully retrieved from the system. 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ***Please check the [Available Object Definitions](#available-object-definitions) documentation part for more details on the available embeds!***

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

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested action could not be understood by the system. 


- ***401  Unauthorized*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested action requires authentication. 


- ***403  Forbidden*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; System refuses to fulfill the requested action. 


- ***404  Not Found*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Specified article resource does not exist in the system. 


- ***500  Internal Server Error*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; A generic error has occurred on the system. 



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

