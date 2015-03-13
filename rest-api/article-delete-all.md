
# DELETE : {apiKey}/articles/purge 

### *Description:* 
Asynchronously deletes all previously created article resources from the system. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


* * *
### *Response Codes:*


- ***204  No Content*** 

 All article resources are successfully deleted from the system. 


- ***400  Bad Request*** 

 Requested action could not be understood by the system. 


- ***401  Unauthorized*** 

 Requested action requires authentication. 


- ***403  Forbidden*** 

 System refuses to fulfill the requested action. 


- ***404  Not Found*** 

 Article resources could not be found. 


- ***409  Conflict*** 

 Requested action could not be carried out because of a conflict in the system. 


- ***500  Internal Server Error*** 

 A generic error has occurred on the system. 



* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

