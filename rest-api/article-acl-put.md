
# PUT : {apiKey}/articles/{articleId}/permissions 

### *Description:* 
Asynchronously inserts new ACL policy into the system. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***permissions*** - Required (array). An ACL policy object that needs to be inserted into the system. This object specifies parameters necessary
            for establishing user and/or role set of rights. Allowed parameters are:
            - &quot;UserId&quot;,
            - &quot;RoleId&quot;,
            - &quot;Links&quot;,
            - &quot;Fields&quot;,
            - &quot;Embed&quot; and
            - &quot;ActionId&quot;. 


- ***articleId*** - Required (UID). Value which uniquely identifies article resource for which new ACL policy needs to be established. 


* * *
### *Response Codes:*


- ***201  Created*** 

 New ACL policy has been successfully established for the specified user and/or role. 
 ***Please check the [Available Object Definitions](#available-object-definitions) documentation part for more details on the available embeds!*** 

```
 {
  "type": "array",
  "items": {
    "action": {
      "type": "Available Object Definitions / aCLAction"
    },
    "role": {
      "type": "Available Object Definitions / aCLRole"
    },
    "user": {
      "type": "Available Object Definitions / aCLUser"
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

 Requested action has been successfully processed, but the response is intentionally blank. 


- ***400  Bad Request*** 

 Requested action could not be understood by the system. Make sure that user and/or role parameter are specified. 


- ***401  Unauthorized*** 

 Requested action requires authentication. 


- ***403  Forbidden*** 

 System refuses to fulfill the requested action because of insufficient privileges. 


- ***404  Not Found*** 

 Specified and/or role resource do not exist in the system. 


- ***409  Conflict*** 

 Requested action could not be carried out because of a conflict in the system. 


- ***500  Internal Server Error*** 

 A generic error has occurred on the system. 



* * *
### *Available Object Definitions:*

***aCLAction***

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
***aCLRole***

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
***aCLUser***

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
lete", "Read" and "Update". 
