
# GET : {apiKey}/articles 

### *Description:* 
Asynchronously retrieves article resources that match the specified criteria. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***embed*** - Optional (string). Comma separated list of resources to be contained within the current representation. 


- ***sort*** - Optional (string). A string used to set the article property to sort the result collection by. For complete list of available
             properties, see the JSON representation of article object under the Response Codes section. 


- ***rpp*** - Optional (integer). A value used to limit the size of result set per page. 


- ***page*** - Optional (integer). A value used to se the page size, i.e. to retrieve certain article subset from the storage. 


- ***tags*** - Optional (string). A value used to restrict the search to article resources with these tags. Multiple tags should be comma separated. 


- ***statuses*** - Optional (string). Comma separated list of article statuses that specify where search should be done (Allowed statuses:
             Published, Draft and Archived). 


- ***endDate*** - Optional (ISO 8601 Format). A value used to specify the article creation date until (and including) which article resource collection
             should be returned. 


- ***startDate*** - Optional (ISO 8601 Format). A value used to specify the article creation date starting from which article resource collection should be returned. 


- ***searchQuery*** - Optional (string). A string referencing article properties using the phrase or query search. 


* * *
### *Response Codes:*


- ***200  OK*** 

 Article subset is successfully retrieved from the system. 
 ***Please check the [Available Object Definitions](#available-object-definitions) documentation part for more details on the available embeds!*** 

```
 {
  "required": [],
  "properties": {
    "embed": [],
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

 Specified article resource does not exist in the system. 


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

-  *** Search Details***
  
   -- See the JSON representation of article object under the Response Codes section for
      complete list of article properties. Note that some properties may not be searchable.
   -- Allowed Search Types:
   1. Query string can be specified using the BQL (Baasic Query Language) which searches through available
      article resources by using the basic SQL syntax. For more information on available SQL operators and
      examples see: [https://msdn.microsoft.com/en-us/library/ms174986.aspx](https://msdn.microsoft.com/en-us/library/ms174986.aspx). This type of search is case-sensitive.
   2. In contrast to the query string, phrase string should contain expected article resource property. Only
      article resource whose property matches the search keyword will be listed. This type of search is case-insensitive. 
search is case-insensitive. 
