
# GET : {apiKey}/permissions/sections/{sectionAbrv} 

### *Description:* 
Asynchronously retrieves access action resources that match the specified search criteria. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***embed*** - Optional (string). Comma separated list of resources to be contained within the current representation. 


- ***sort*** - Optional (string). A string used to set the access action property to sort the result collection by. For complete list of
            available properties, see the JSON representation of access action object under the Response Codes section. 


- ***searchQuery*** - Optional (string). A string value used to identify access action resources in the system. Only access actions whose name
            abbreviation matches a search string will be listed (search is case-insensitive). 


- ***sectionAbrv*** - Required (string). Section abbreviation which identifies part of the application for which security privileges can be retrieved
            and managed. Supported values are:
	- "MediaVault"
	- "ApplicationSettings"
	- "ArticleRatingModule"
	- "ValueSetStore"
	- "ArticleModule"
	- "ArticleArchiveModule"
	- "KeyValueStore"
	- "ResourceSchema"
	- "MediaCenterSecurity"
	- "Roles"
	- "MediaCenter"
	- "Users"



* * *
### *Response Codes:*


- ***200  OK*** 

 Access action resource subset is successfully retrieved from the system. 

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
        "$ref": "#/definitions/accessAction"
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
    "accessAction": {
      "required": [],
      "properties": {
        "abrv": {
          "type": "string"
        },
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
        "embed": []
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

 Specified access action resource subset does not exist in the system. 


- ***500  Internal Server Error*** 

 A generic error has occurred on the system. 



* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

-  System supports basic CRUD access policies: "Create", "Delete", "Read" and "Update". 
