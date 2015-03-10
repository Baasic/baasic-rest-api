
# GET : {apiKey}/article-settings 

### *Description:* 
Asynchronously retrieves article settings from the system. 



* * *
### *Parameters:*


- ***apiKey*** - Required (string). A value that uniquely identifies user&#39;s application on the system. 


* * *
### *Response Codes:*


- ***200  OK*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Article settings are successfully retrieved from the system. 

```
 {
  "required": [],
  "properties": {
    "allowArchive": {
      "type": "boolean"
    },
    "allowComments": {
      "type": "boolean"
    },
    "allowRating": {
      "type": "boolean"
    },
    "allowSubscription": {
      "type": "boolean"
    },
    "allowTags": {
      "type": "boolean"
    },
    "allowUploads": {
      "type": "boolean"
    },
    "autoSaveDraft": {
      "type": "boolean"
    },
    "autoSaveDraftPeriod": {
      "type": "integer"
    },
    "commentAllowSubscription": {
      "type": "boolean"
    },
    "commentEnableSPAMDetection": {
      "type": "boolean"
    },
    "commentNotifyPostAuthor": {
      "type": "boolean"
    },
    "commentNotifyPostAuthorCC": {
      "type": "string"
    },
    "commentNotifyRequireModeration": {
      "type": "boolean"
    },
    "commentRequireModeration": {
      "type": "boolean"
    },
    "defaultContentFormat": {
      "type": "string"
    },
    "logSubscriptionNotifications": {
      "type": "boolean"
    },
    "notifyAuthorOnNewSubscriptions": {
      "type": "boolean"
    },
    "notifyAuthorOnNewSubscriptionsCC": {
      "type": "string"
    },
    "uploadAllowedExtensions": {
      "type": "string"
    },
    "uploadLogNotifications": {
      "type": "boolean"
    },
    "uploadNotifyRequireModeration": {
      "type": "boolean"
    },
    "uploadNotifyRequireModerationCC": {
      "type": "string"
    },
    "uploadRequireModeration": {
      "type": "boolean"
    },
    "dateCreated": {
      "type": "ISO 8601 Format"
    },
    "dateUpdated": {
      "type": "ISO 8601 Format"
    },
    "id": {
      "type": "UID"
    },
    "embed": []
  }
} 

```

- ***204  No Content*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested action has been successfully processed, but the response is intentionally blank. 


- ***400  Bad Request*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested action could not be understood by the system. 


- ***401  Unauthorized*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested action requires authentication. 


- ***403  Forbidden*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; System refuses to fulfill the requested action. 


- ***404  Not Found*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requested article settings do not exist in the system. 


- ***500  Internal Server Error*** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; A generic error has occurred on the system. 



* * *
### *Notes:* 
- Each object contains ***Links*** array property where each item in the array is a link description object which describes the link relations of the instances. The link relations are described by the ***href*** and ***templated*** properties. For more details on the HAL conventions see: [Hypertext Application Language] (http://stateless.co/hal_specification.html).

