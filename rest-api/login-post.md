
# POST : {apiKey}/login 

### *Description:* 
Asynchronously handles authentication request according to the specified login type and options. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


- ***options*** - Optional (string). Comma separated list of options used to setup authentication token with cookie session. Supported values
             are: &quot;session&quot; and &quot;sliding&quot;. 


- ***type*** - Optional (string). A Login Type which defines how the user authenticates into the system. Supported values are: &quot;oauth&quot; and &quot;forms&quot;. 


* * *
### *Response Codes:*


- ***201  Created*** 

 Authentication token has been successfully created, i.e user has been successfully logged into the system. Response contains authentication token and timeout information. 

```
 {
  "required": [],
  "properties": {}
} 

```

- ***400  Bad Request*** 

 Requested action could not be understood by the system. 


- ***401  Unauthorized*** 

 Requested action requires valid credentials. 


- ***403  Forbidden*** 

 System refuses to fulfill the requested action. 


- ***409  Conflict*** 

 Requested action could not be carried out because of a conflict in the system. 


- ***500  Internal Server Error*** 

 A generic error has occurred on the system. 



* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

-  Login Types: OAuth - allows third-party access to the Baasic resources without sharing login credentials and
   Forms - requires login credentials for access to the Baasic resources.
  
   Login Options: Session - user gets non session cookie with a timeout and Sliding - user gets session cookie
   with a timeout and sliding expiration renewal. 
