
# GET : {apiKey}/subscriptions/{segment} 

### *Description:* 
Asynchronously checks if the current user is subscribed to a whole segment. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***segment*** - Required (string). Segment is convention based name for parts of the system, modules, cross-cutting modules, etc. This value
            will uniquely identify segment whose subscription status needs to be verified. Supported values are:
	- "article"
	- "article"
	- "articletag"
	- "article/archive"
	- "article"
	- "articletag"
	- "articletag"
	- "article/publish"
	- "article/publish/tag"



* * *
### *Response Codes:*


- ***204  No Content*** 

 Current user is subscribed to the specified segment. 


- ***400  Bad Request*** 

 Requested action could not be understood by the system. 


- ***401  Unauthorized*** 

 Requested action requires authentication. 


- ***403  Forbidden*** 

 System refuses to fulfill the requested action. 


- ***404  Not Found*** 

 Current user is not subscribed to the specified segment. 


- ***500  Internal Server Error*** 

 A generic error has occurred on the system. 



* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

