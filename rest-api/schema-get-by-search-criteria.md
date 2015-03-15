
# GET : {apiKey}/schemas 

### *Description:* 
Asynchronously retrieves dynamic schema resources that match the specified criteria. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***embed*** - Optional (string). Comma separated list of resources to be contained within the current representation. 


- ***sort*** - Optional (string). A string used to set the dynamic schema property to sort the result collection by. For complete list of
             available properties, see the JSON representation of dynamic schema object under the Response Codes section. 


- ***rpp*** - Optional (integer). A value used to limit the size of result set per page. 


- ***page*** - Optional (integer). A value used to se the page size, i.e. to retrieve certain dynamic schema subset from the storage. 


- ***searchQuery*** - Optional (string). A string referencing dynamic schema properties using the phrase or query search. 


* * *
### *Response Codes:*


- ***200  OK*** 

 Dynamic schema resource subset is successfully retrieved from the system. 
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
        "$ref": "#/definitions/resourceSchema"
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
    "resourceSchema": {
      "required": [
        "name",
        "schema"
      ],
      "properties": {
        "description": {
          "type": "string"
        },
        "enforceSchemaValidation": {
          "type": "boolean"
        },
        "name": {
          "type": "string"
        },
        "owner": {
          "type": "Available Object Definitions / owner"
        },
        "ownerId": {
          "type": "UID"
        },
        "schema": {
          "type": "object"
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
          "owner"
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

 Specified dynamic schema resource subset does not exist in the system. 


- ***500  Internal Server Error*** 

 A generic error has occurred on the system. 



* * *
### *Available Object Definitions:*

***owner***

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

-  *** Search Details***
  
   -- See the JSON representation of dynamic schema object under the Response Codes section for
      complete list of dynamic schema properties. Note that some properties may not be searchable.
   -- Allowed Search Types:
   1. Query string can be specified using the BQL (Baasic Query Language) which searches through available
      dynamic schemas by using the basic SQL syntax. For more information on available SQL operators and
      examples see: [https://msdn.microsoft.com/en-us/library/ms174986.aspx](https://msdn.microsoft.com/en-us/library/ms174986.aspx). This type of search is case-sensitive.
   2. In contrast to the query string, phrase string should contain expected dynamic schema property. Only
      dynamic schema whose property matches the search keyword will be listed. This type of search is case-insensitive. 
