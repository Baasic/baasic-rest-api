# Baasic REST SDK

Baasic REST SDK Documentation provides detailed information for all Baasic [REST API](https://api.baasic.com) end-points.

## Usage

This section will describe how to add the Baasic AngularJS Core library to your project. It's important to know that Baasic AngularJS SDK uses HAL+JSON format for the back-end communication. You can find out more about HAL format [here](http://stateless.co/hal_specification.html).  

If you prefer learning by example please skip to [Demo Section](#demo).

### Adding the Library to your Project

Please add the following lines of code after the AngularJS include:

```html
<script src='//cdn.net/js/hal-parser.js'></script>
<script src='//cdn.net/js/uritemplate-min.js'></script>
<script src='//cdn.net/js/baasic-angular-1.0.0.min.js'></script>
```

The recommended way of serving the library is through a [CDN](http://en.wikipedia.org/wiki/Content_delivery_network) but note that this is not a requirement. If you prefer adding library files directly to your project instead, please modify the includes accordingly.


### Initialization

To be able to use the library you will need to add the Baasic (_baasic.api_) dependency to your AngularJS module. This will allow you to use library services described in [Modules Section](#baasic-modules).

```javascript
angular.module('my-module', ["baasic.api"])
```

### Application Configuration

Baasic AngularJS library allows you to use multiple Baasic applications in your AngularJS modules. To initialize a Baasic application you will need to add the following code to you module configuration:

```javascript
module.config(["baasicAppProvider",
    function (baasicAppProvider) {
        var app = baasicAppProvider.create("my-app-identifier", {
            apiRootUrl: "api.baasic.com",
            apiVersion: "v1"
        });
    }]);
```

**Note:** _To obtain a Baasic Application Identifier please create your application on [Baasic Registration](https://dashboard.baasic.com/register/) page._

## Baasic Modules

Baasic back-end contains various built-in modules that can be easily consumed through the Baasic AngularJS library. Below you can find detailed information about all the core modules supported by the library.

* [Security service](https://github.com/Baasic/baasic-sdk-angularjs-security)
* [Membership service](https://github.com/Baasic/baasic-sdk-angularjs-membership)
* [Application settings service](https://github.com/Baasic/baasic-sdk-angularjs-app-settings)
* [Key Value module service](https://github.com/Baasic/baasic-sdk-angularjs-key-value)
* [Value Set module service](https://github.com/Baasic/baasic-sdk-angularjs-value-set)
* [Dynamic Resources module service](https://github.com/Baasic/baasic-sdk-angularjs-dynamic-resource)
* [Article module service](https://github.com/Baasic/baasic-sdk-angularjs-articles)
* General services, directives etc.

### Baasic Module Architecture

To get a better understanding of Baasic AngularJS services bellow are the details of the main architecture to which all the library services conform to.

##### Core Services

* __baasicApp__ service is used to manage Baasic application instances. Multiple AngularJS application instances can be created and coexist at the same time (each will communicate with its corresponding Baasic application)
    *  create an application
    ```javascript
    module.controller("MyCtrl", ["baasicApp",
        function MyCtrl(baasicApp) {
            var app = baasicApp.create("my-app-identifier", {
                apiRootUrl: "api.baasic.com",
                apiVersion: "v1"
            });
        }]);
    ```
    * get the default application
    ```javascript
    module.controller("MyCtrl", ["baasicApp",
        function MyCtrl(baasicApp) {
            var app = baasicApp.get();
        }]);
    ```
    * application object has the following methods
    ```javascript
    var apiKey = app.get_apiKey();
    var apiURI = app.get_apiUrl();
    var accessToken = app.get_accessToken();
    app.update_accessToken(accessToken);
    var currentUser = app.get_user();
    app.set_user(userDetails, accessToken);
    var currentLanguage = app.get_currentLanguage();
    var defaultLanguage = app.get_defaultLanguage();
    ```
* __baasicApiHttp__

    Baasic HTTP service is used to perform low level communication with the Baasic back-end.

    This service handles:
    * authentication tokens
    * HAL parsing

* __baasicApiService__

    This service is used to perform low level model or option transformations before they are sent to the Baasic back-end.

    The following transformations are supported:

    * Resource collection fetch transformation
    * Single resource fetch transformation
    * Create resource transformation
    * Update resource transformation
    * Delete resource transformation

* __baasicConstants__

Baasic constants contain values such as _id_ property name and _model_ property name parameters that can be used in case manual model or option transformation is needed.


##### Route Services

* every service has a route service used to wrap REST service URL discovery
* route service parses the REST service URL and prepares the URL for expansion
* route services contain the following routes
    * `find` - used to fetch a collection of resources that can be filtered, paged, sorted
    * `get` - used to fetch a single resource
    * `create` - used to create a new resources
* supported route parameters:
    * `find` route supports the following parameters:
        * `searchQuery` - used to build simple filters or complex queries (read more about Baasic Query Language in Baasic User Manual)
        * `page` - used to define the current page
        * `rpp` - used to define the number of resources per page
        * `sort` - used to define sorting expression applied to the returned resources. Sorting expressions use the following format: `fieldName|asc`, `field1Name|asc,field2Name|desc`
        * `embed` - used to embed additional resources
        * `fields` - used to define the list of fields returned by the service  
    * `get` route supports the following parameters:
        * `embed` - used to embed additional resources
        * `fields` - used to define list of fields returned by the service
    * `create` route in most cases has no parameters
* `parse` is an utility method used to parse custom URIs (_Note: parse will not return a route_)

##### Module Services

* Baasic module services are built on top of AngularJS services
* module services depend upon route services as they are used for REST service URL discovery (Note: every service exposes route service through the _routeService_ property)
* every service has the `find`, `get`, `create`, `update` and `remove` functions used to communicate with the Baasic back-end
* all services accept _data_ object as a function parameter

##### HAL links

Resources returned from Baasic are by default in HAL format and they look similar to this:
```javascript
{
    "key": "your-key",
    "value": "your-value",
    "dateCreated": "2015-01-01T14:24:56.795849Z",
    "dateUpdated": "2015-01-01T14:24:56.795849Z",
    "id": "4f788120-7cf8-44e1-bf81-a33e012c94ee",
    "_links": {
        "self": {
            "href": "http://api.baasic.local/v1/your-app-id/key-values/your-key",
            "templated": false
        },
        "post": {
            "href": "http://api.baasic.local/v1/your-app-id/key-values",
            "templated": false
        },
        "put": {
            "href": "http://api.baasic.local/v1/your-app-id/key-values/your-key",
            "templated": false
        },
        "delete": {
            "href": "http://api.baasic.local/v1/your-app-id/key-values/your-key",
            "templated": false
        }
    },
    "_embedded": { }
}
```

**Note**: The preferred way of accessing Bassic back-end is through use of AngularJS SDK services. For manual access to the back-end URL's you can use this (or similar) code:

```javascript
data.links('put').href
data.links('delete').href
```

You can for example also create your own `update` function by using Baasic core services:

```javascript
update: function (data) {
    var params = baasicApiService.updateParams(data);
    var url = params[baasicConstants.modelPropertyName].links('put').href;
    var model = params[baasicConstants.modelPropertyName];
    return baasicApiHttp.put(url, model);
},
```


##### Extending models

Baasic built-in models can be extended with custom properties by simply setting property values.

```javascript
article.myProperty = 1;
article.myPropertyObject = {
    firstProp: 1,
    secondProp: 2
}

update: function (article) {
    return articleService.update(article);
}
```

This powerful feature allows you to extend all built-in models with custom properties which allows modules like Article to fully suit your needs.

##### recaptchaService

TBA.

##### recaptchaDirective

TBA.

## Demo

* [Agency Demo](http://demo.baasic.com/AngularJS/Agency)

## Build Process

1. Install [NodeJs](http://nodejs.org/download/)
2. Open Shell/Command Prompt in the Baasic AngularJS folder
3. Run `npm install`
4. Install gulp globally: `npm install -g gulp`
5. Run `gulp`

## Contributing

##### Pull requests are always welcome

We appreciate pull requests you make, and we'll do our best to process them as quickly as we can. Even if it's just a typo you found or any small or large issue you fixed - please do it! It will help us a lot.

If your pull request is not accepted on your first try, don't be discouraged! If there's a problem with your implementation, hopefully you received feedback on what to improve.

##### Issue reporting

Before you create a new issue, please make sure it hasn't already been reported. In case it already exists simply add a quick _"+1"_ or _"I have the same problem"_ to the existing issue thread.

##### Other

* Help us write the documentation
* Create interesting apps using SDK
* Looking for something else to do? Get in touch..
