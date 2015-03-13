
# DELETE : {apiKey}/articles/{articleId}/tags 

### *Description:* 
Asynchronously deletes all article tag resources that have been established for the specified article. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***articleId*** - Required (string). Value which uniquely identifies article whose tag resources need to be deleted. 


* * *
### *Response Codes:*


- ***200  OK*** 

 Specified article tag resources are successfully deleted from the system. Response contains total number of article tags that have been deleted by this action. 


- ***400  Bad Request*** 

 Requested action could not be understood by the system. 


- ***401  Unauthorized*** 

 Requested action requires authentication. 


- ***403  Forbidden*** 

 System refuses to fulfill the requested action. 


- ***404  Not Found*** 

 Specified article resource does not exist in the system. 


- ***500  Internal Server Error*** 

 A generic error has occurred on the system. 



* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

