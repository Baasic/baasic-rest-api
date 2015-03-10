
# GET : {apiKey}/articles 

### *Description:* 
Asynchronously retrieves article resources that match the specified criteria. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***embed*** - Optional (string). Comma separated list of resources to be contained within the current representation. 


- ***sort*** - Optional (string). A string used to set the article property to sort the result collection by. 


- ***rpp*** - Optional (integer). A value used to limit the size of result set per page. 


- ***page*** - Optional (integer). A value used to se the page size, i.e. to retrieve certain article subset from the storage. 


- ***tags*** - Optional (string). A value used to restrict the search to article resources with these tags. Multiple tags should be comma separated. 


- ***statuses*** - Optional (string). Comma separated list of article statuses that specify where search should be done (Allowed statuses:
            Published, Draft and Archived). 


- ***endDate*** - Optional (ISO 8601 Format). A value used to specify the article creation date until (and including) which article resource collection
            should be returned. 


- ***startDate*** - Optional (ISO 8601 Format). A value used to specify the article creation date starting from which article resource collection should be returned. 


- ***searchQuery*** - Optional (string). A string referencing article rating properties using the phrase or query search. 


* * *
### *Response Codes:*


- ***200  OK*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Article subset is successfully retrieved from the system. 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ***Please check the [Available Object Definitions](#available-object-definitions) documentation part for more details on the available embeds!***

```
 {
  "required": [],
  "properties": {
    "statistics": {
      "type": "Available Object Definitions / stats"
    },
    "embed": [
      "statistics"
    ],
    "item": {
      "type": "array",
      "items": {
        "$ref": "#/definitions/article"
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
    "article": {
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
            "$ref": "Available Object Definitions / commentModel"
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
            "$ref": "Available Object Definitions / ratingModel"
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
            "$ref": "Available Object Definitions / tagModel"
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
  }
} 

```

- ***204  No Content*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested action has been successfully processed, but the response is intentionally blank. 


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

***stats***

```
 {
    "required": [],
    "properties": {
      "archiveCount": {
        "type": "integer"
      },
      "draftCount": {
        "type": "integer"
      },
      "publishedCount": {
        "type": "integer"
      },
      "tagStats": {
        "type": "array",
        "items": {
          "type": "object"
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
***commentModel***

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
***ratingModel***

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
***tagModel***

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

-  Search Types (Search is case-sensitive): 
  1. Query string can be specified using the BQL (Baasic Query Language) which searches through available article resources by using the basic SQL syntax. For more information on available SQL operators and examples see: [https://msdn.microsoft.com/en-us/library/ms174986.aspx](https://msdn.microsoft.com/en-us/library/ms174986.aspx).
  2. In contrast to the query string, phrase string should contain keyword or exact sentence. Only articles that contain phrase string in at least one of the search fields will be listed. Search fields are: article author and article name. 
