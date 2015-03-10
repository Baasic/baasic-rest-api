
# GET : {apiKey}/resources/{resourceName}/{id}/permissions 

### *Description:* 
Asynchronously retrieves ACL action resource from the system. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***id*** - Required (string). Specifies dynamic entry resource whose ACL actions need to be retrieved. 


- ***resourceName*** - Required (string). Name of dynamic schema which provides unique identification of the specified dynamic entry resource. 


* * *
### *Response Codes:*


- ***200  OK*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ACL action resource subset is successfully retrieved from the system. 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ***Please check the [Available Object Definitions](#available-object-definitions) documentation part for more details on the available embeds!***

```
 {
  "type": "array",
  "items": {
    "action": {
      "type": "Available Object Definitions / aCLActionModel"
    },
    "role": {
      "type": "Available Object Definitions / aCLRoleModel"
    },
    "user": {
      "type": "Available Object Definitions / aCLUserModel"
    },
    "actionId": {
      "type": "UID"
    },
    "roleId": {
      "type": "UID"
    },
    "userId": {
      "type": "UID"
    },
    "embed": []
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

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; System refuses to fulfill the requested action because of insufficient privileges. To retrieve ACL permissions, current user needs: 
 1. to be an account owner or 
 2. to be assigned Super Administrators role or 
 3. to have READ access permissions for the specified dynamic type resource. 


- ***404  Not Found*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Specified ACL action resource subset does not exist in the system.&lt; 


- ***500  Internal Server Error*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; A generic error has occurred on the system. 



* * *
### *Available Object Definitions:*

***aCLActionModel***

```
 {
    "required": [],
    "properties": {
      "id": {
        "type": "UID"
      },
      "name": {
        "type": "string"
      }
    }
 }
```
***aCLRoleModel***

```
 {
    "required": [],
    "properties": {
      "id": {
        "type": "UID"
      },
      "name": {
        "type": "string"
      }
    }
 }
```
***aCLUserModel***

```
 {
    "required": [],
    "properties": {
      "id": {
        "type": "UID"
      },
      "name": {
        "type": "string"
      }
    }
 }
```
* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

-  System supports basic CRUD ACL policies: "Create", "Delete", "Read" and "Update". 
