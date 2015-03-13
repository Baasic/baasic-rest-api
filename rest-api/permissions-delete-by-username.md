
# DELETE : {apiKey}/permissions/sections/{sectionAbrv}/actions/{actionAbrv}/users/{userName} 

### *Description:* 
Asynchronously deletes an access policy assigned to the specified user and section. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***userName*** - Required (string). A value which uniquely identifies user for which access policy needs to be removed. 


- ***actionAbrv*** - Required (string). Action abbreviation which identifies access policy that can be assigned to the specified user and section.
            System supports basic CRUD access policies: &quot;Create&quot;, &quot;Delete&quot;, &quot;Read&quot; and &quot;Update&quot;. 


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


- ***204  No Content*** 

 Requested access policy has been successfully removed. 


- ***400  Bad Request*** 

 Requested action could not be understood by the system. 


- ***401  Unauthorized*** 

 Requested action requires authentication. 


- ***403  Forbidden*** 

 System refuses to fulfill the requested action, i.e. current user doesn&#39;t have DELETE permissions for the specified section. 


- ***404  Not Found*** 

 Required access policy entry does not exist in the system. 


- ***500  Internal Server Error*** 

 A generic error has occurred on the system. 



* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

