
# DELETE : {apiKey}/permissions/sections/{sectionAbrv}/actions/{actionAbrv}/roles/{role} 

### *Description:* 
Asynchronously deletes an access policy assigned to the specified role and section. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***role*** - Required (string). A value which uniquely identifies role for which access policy needs to be removed. 


- ***actionAbrv*** - Required (string). Action abbreviation which identifies access policy assigned to the specified role and section. System
            supports basic CRUD access policies: &quot;Create&quot;, &quot;Delete&quot;, &quot;Read&quot; and &quot;Update&quot;. 


- ***sectionAbrv*** - Required (string). Section abbreviation which identifies part of the application for which security privileges can be retrieved
            and managed. Following section abbreviations are supported:
            - &quot;KeyValueStore&quot;,
            - &quot;ValueSetStore&quot;,
            - &quot;ArticleModule&quot;,
            - &quot;ArticleArchiveModule&quot;,
            - &quot;ArticleRatingModule&quot;,
            - &quot;ResourceSchema&quot;,
            - &quot;DynamicNameResourceSchema&quot;,
            - &quot;Users&quot;,
            - &quot;Roles&quot; and
            - &quot;ApplicationSettings&quot;. 


* * *
### *Response Codes:*


- ***204  No Content*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested access policy has been successfully removed. 


- ***400  Bad Request*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested action could not be understood by the system. Make sure that the following requirements are fulfilled: 
 - role parameter is specified, 
 - provided section abbreviation is valid, 
 - provided access action abbreviation is valid and 
 - specified role exists in the system. 


- ***401  Unauthorized*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested action requires authentication. 


- ***403  Forbidden*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; System refuses to fulfill the requested action, i.e. current user doesn&#39;t have DELETE permissions for the specified section. 


- ***404  Not Found*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Required access policy entry does not exist in the system. 


- ***500  Internal Server Error*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; A generic error has occurred on the system. 



* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

