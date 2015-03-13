
# DELETE : {apiKey}/applications 

### *Description:* 
Asynchronously deletes previously created application resource from the system. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


* * *
### *Response Codes:*


- ***204  No Content*** 

 Application resource is successfully deleted from the system. 


- ***400  Bad Request*** 

 Requested action could not be understood by the system. 


- ***401  Unauthorized*** 

 Requested action requires authentication. 


- ***403  Forbidden*** 

 System refuses to fulfill the requested action. 


- ***404  Not Found*** 

 Required application resource does not exist in the system. 


- ***500  Internal Server Error*** 

 A generic error has occurred on the system. 


* * *
### *Code Examples:*



***CURL***
  
 ```
  curl 
   -H Authorization:"forms token"
   -H Accept:application/json 
   -X DELETE 
   -v 
   https://api.baasic.com/v1/apiKey/applications/
  ```   

* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

