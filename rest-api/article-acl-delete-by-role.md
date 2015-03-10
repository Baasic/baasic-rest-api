
# DELETE : {apiKey}/articles/{articleId}/permissions/actions/{accessAction}/roles/{role} 

### *Description:* 
Asynchronously deletes ACL policy assigned to the specified role and article resource. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***role*** - Required (string). A value which uniquely identifies role for which ACL policy needs to be removed. 


- ***accessAction*** - Required (string). Action abbreviation which identifies ACL policy assigned to the specified role and article resource. System
            supports basic CRUD ACL policies: &quot;Create&quot;, &quot;Delete&quot;, &quot;Read&quot; and &quot;Update&quot;. 


- ***articleId*** - Required (UID). Value which uniquely identifies article resource whose security privileges need to be retrieved and updated. 


* * *
### *Response Codes:*


- ***204  No Content*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested ACL policy has been successfully removed. 


- ***400  Bad Request*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested action could not be understood by the system. Make sure that the following requirements are fulfilled: 
 - role parameter is specified, 
 - provided access action abbreviation is valid and 
 - specified role exists in the system. 


- ***401  Unauthorized*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested action requires authentication. 


- ***403  Forbidden*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; System refuses to fulfill the requested action because of insufficient privileges. To delete intended ACL permission, current user needs: 
 1. to be an account owner or 
 2. to be assigned Super Administrators role or 
 3. to have DELETE access permissions for the specified article resource. 


- ***404  Not Found*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Specified article resource does not exist in the system. 


- ***500  Internal Server Error*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; A generic error has occurred on the system. 



* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

