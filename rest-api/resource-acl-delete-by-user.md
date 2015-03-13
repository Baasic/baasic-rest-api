
# DELETE : {apiKey}/resources/{schemaName}/{id}/permissions/actions/{accessAction}/users/{user} 

### *Description:* 
Asynchronously deletes ACL policy assigned to the specified user and dynamic entry resource. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***user*** - Required (string). A value which uniquely identifies user for which ACL policy needs to be removed. 


- ***accessAction*** - Required (string). Action abbreviation which identifies ACL policy assigned to the specified user and dynamic entry resource.
            System supports basic CRUD ACL policies: &quot;Create&quot;, &quot;Delete&quot;, &quot;Read&quot; and &quot;Update&quot;. 


- ***id*** - Required (string). Specifies dynamic entry resource whose security privileges need to be retrieved and updated. 


- ***schemaName*** - Required (string). Name of dynamic schema which provides unique identification of the specified dynamic entry resource. 


* * *
### *Response Codes:*


- ***204  No Content*** 

 Requested ACL policy has been successfully removed. 


- ***400  Bad Request*** 

 Requested action could not be understood by the system. 


- ***401  Unauthorized*** 

 Requested action requires authentication. 


- ***403  Forbidden*** 

 System refuses to fulfill the requested action because of insufficient privileges. 


- ***404  Not Found*** 

 Specified dynamic schema or dynamic type resource does not exist in the system. 


- ***500  Internal Server Error*** 

 A generic error has occurred on the system. 



* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

