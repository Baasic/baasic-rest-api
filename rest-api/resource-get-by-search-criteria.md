
# GET : {apiKey}/resources/{resourceName} 

### *Description:* 
Asynchronously retrieves previously created dynamic entry resources from the system. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***embed*** - Optional (string). Comma separated list of resources to be contained within the current representation. 


- ***sort*** - Optional (string). A string used to set the dynamic entry property to sort the result collection by. 


- ***rpp*** - Optional (integer). A value used to limit the size of result set per page. 


- ***page*** - Optional (integer). A value used to set the page size, i.e. to retrieve certain dynamic entry subset from the storage. 


- ***searchQuery*** - Optional (string). A string value used to identify dynamic entry resources in the system. 


- ***resourceName*** - Required (string). Name of dynamic schema whose dynamic entry resources need to be retrieved. 


* * *
### *Response Codes:*


- ***200  OK*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Dynamic entry resources are successfully retrieved from the system. 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ***Please check the [Available Object Definitions](#available-object-definitions) documentation part for more details on the available embeds!***

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
        "$ref": "Available Object Definitions / dynamicRESTModel"
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

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested action has been successfully processed, but the response is intentionally blank. 


- ***400  Bad Request*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested action could not be understood by the system. 


- ***401  Unauthorized*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested action requires authentication. 


- ***403  Forbidden*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; System refuses to fulfill the requested action. 


- ***404  Not Found*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Specified dynamic entry resources do not exist in the system. 


- ***500  Internal Server Error*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; A generic error has occurred on the system. 



* * *
### *Available Object Definitions:*

***dynamicRESTModel***

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
        "type": "object"
      }
    }
 }
```
* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

-  Search Types (Search is case-sensitive): 
  1. Query string can be specified using the BQL (Baasic Query Language) which searches through available dynamic entry resources by using the basic SQL syntax. For more information on available SQL operators and examples see: [https://msdn.microsoft.com/en-us/library/ms174986.aspx](https://msdn.microsoft.com/en-us/library/ms174986.aspx).
  2. In contrast to the query string, phrase string should contain expected dynamic entry identifier. Only dynamic entry resource whose id field matches the search keyword will be listed. 
