
# GET : {apiKey}/resources/{schemaName} 

### *Description:* 
Asynchronously retrieves previously created dynamic resources from the system. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***embed*** - Optional (string). Comma separated list of resources to be contained within the current representation. 


- ***sort*** - Optional (string). A string used to set the dynamic resource property to sort the result collection by. For complete list of
             available properties, see the JSON representation of dynamic resource object under the Available Object
             Definitions section. 


- ***rpp*** - Optional (integer). A value used to limit the size of result set per page. 


- ***page*** - Optional (integer). A value used to set the page size, i.e. to retrieve certain dynamic resource subset from the storage. 


- ***searchQuery*** - Optional (string). A string referencing dynamic resource properties using the phrase or query search. 


- ***schemaName*** - Required (string). Name of dynamic schema whose dynamic resources need to be retrieved. 


* * *
### *Response Codes:*


- ***200  OK*** 

 Dynamic entry resources are successfully retrieved from the system. 
 ***Please check the [Available Object Definitions](#available-object-definitions) documentation part for more details on the available embeds!*** 

```
 {
  "required": [],
  "properties": {
    "embed": [
      "item"
    ],
    "item": {
      "type": "array",
      "items": {
        "$ref": "Available Object Definitions / dynamicREST"
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

 Specified dynamic entry resources do not exist in the system. 


- ***500  Internal Server Error*** 

 A generic error has occurred on the system. 



* * *
### *Available Object Definitions:*

***dynamicREST***

```
 {
    "required": [],
    "properties": {
      "embed": {
        "type": "array",
        "items": {
          "type": "string"
        }
      },
      "id": {
        "type": "string"
      }
    }
 }
```
* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

-  *** Search Details***
  
   -- See the JSON representation of dynamic resource object under the Available Object Definitions section for
      complete list of dynamic resource properties. Note that some properties may not be searchable.
   -- Allowed Search Types:
   1. Query string can be specified using the BQL (Baasic Query Language) which searches through available
      dynamic resources by using the basic SQL syntax. For more information on available SQL operators and
      examples see: [https://msdn.microsoft.com/en-us/library/ms174986.aspx](https://msdn.microsoft.com/en-us/library/ms174986.aspx). This type of search is case-sensitive.
   2. In contrast to the query string, phrase string should contain expected dynamic resource property. Only
      dynamic resource whose property matches the search keyword will be listed. This type of search is case-insensitive. 
sitive. 
