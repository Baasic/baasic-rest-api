
# GET : {apiKey}/users 

### *Description:* 
Asynchronously retrieves user resources that match the specified criteria. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***embed*** - Optional (string). Comma separated list of resources to be contained within the current representation. 


- ***sort*** - Optional (string). A string used to set the user property to sort the result collection by. For complete list of available
             properties, see the JSON representation of user object under the Response Codes section. 


- ***rpp*** - Optional (integer). A value used to limit the size of result set per page. 


- ***page*** - Optional (integer). A value used to se the page size, i.e. to retrieve certain user subset from the storage. 


- ***searchQuery*** - Optional (string). A string referencing user properties using the phrase or query search. 


* * *
### *Response Codes:*


- ***200  OK*** 

 User resource subset is successfully retrieved from the system. 
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
        "$ref": "#/definitions/appUser"
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
    "appUser": {
      "required": [],
      "properties": {
        "creationDate": {
          "type": "ISO 8601 Format"
        },
        "email": {
          "type": "string"
        },
        "isApproved": {
          "type": "boolean"
        },
        "isLockedOut": {
          "type": "boolean"
        },
        "name": {
          "type": "string"
        },
        "roles": {
          "type": "array",
          "items": {
            "$ref": "Available Object Definitions / role"
          }
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
        "embed": [
          "roles"
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

 Specified user resource subset does not exist in the system. 


- ***500  Internal Server Error*** 

 A generic error has occurred on the system. 



* * *
### *Available Object Definitions:*

***role***

```
 {
    "required": [
      "name"
    ],
    "properties": {
      "description": {
        "type": "string"
      },
      "name": {
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
  
   -- See the JSON representation of user object under the Response Codes section for
      complete list of user properties. Note that some properties may not be searchable.
   -- Allowed Search Types:
   1. Query string can be specified using the BQL (Baasic Query Language) which searches through available
      user resources by using the basic SQL syntax. For more information on available SQL operators and
      examples see: [https://msdn.microsoft.com/en-us/library/ms174986.aspx](https://msdn.microsoft.com/en-us/library/ms174986.aspx). This type of search is case-sensitive.
   2. In contrast to the query string, phrase string should contain expected user resource property. Only
      user resource whose property matches the search keyword will be listed. This type of search is case-insensitive. 
sitive. 
