# Baasic REST API

Baasic REST API Documentation provides detailed information for all Baasic [REST API](https://api.baasic.com/v1/) end-points.

## Baasic Modules

Baasic back-end contains various built-in modules that can be easily consumed through the Baasic REST API. Below you can find detailed information about all the modules supported by the REST API.

* [Core](https://github.com/Baasic/baasic-rest-api/wikis/_sidebar#core)
* [Membership](https://github.com/Baasic/baasic-rest-api/wikis/_sidebar#membership)
* [Application Module](https://github.com/Baasic/baasic-rest-api/wikis/_sidebar#application)
* [Key Value Module](https://github.com/Baasic/baasic-rest-api/wikis/_sidebar#key-value)
* [Value Set Module](https://github.com/Baasic/baasic-rest-api/wikis/_sidebar#value-set)
* [Dynamic Resources Module](https://github.com/Baasic/baasic-rest-api/wikis/_sidebar#dynamic-type)
* [Article Module](https://github.com/Baasic/baasic-rest-api/wikis/_sidebar#article)

## Supported features

This section will describe what features are supported on all REST API end-points.

### HTTP formats support
- JSON (application/json)
- HAL JSON (application/hal+json)

It's important to know that Baasic supports and recommends HAL+JSON format as default one. Baasic SDKs will have HAL+JSON set as default http format for the back-end communication. You can find out more about HAL format [here](http://stateless.co/hal_specification.html).  

##### HAL 

Resources returned from Baasic in HAL format look similar to this:

```javascript
{
    "key": "your-key",
    "value": "your-value",
    "dateCreated": "2015-01-01T14:24:56.795849Z",
    "dateUpdated": "2015-01-01T14:24:56.795849Z",
    "id": "kZyiWLUzz8dqAjHiO1gxXK",
    "_links": {
        "self": {
            "href": "https://api.baasic.local/v1/your-app-id/key-values/your-key",
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

The preferred way of accessing Bassic back-end is through use of HAL links. To manually access the predefined links one should use *_links* property from the returned resource:

```javascript
_links.put.href
_links.delete.href
```

To reduce the number of round-trips to back-end you can use HAL embeds, available embeds can be found in the *_embedded* property and they look similar to this:

```javascript
"_embedded": {
	"author": { },
	"comments": [ ],
	"ratings": [ ],
	"tags": [ ]
}
```

**Note:** They are returned as empty objects or arrays until you explicitly request them through the _embed_ query parameter.

## Issue reporting

Before you create a new issue, please make sure it hasn't already been reported. In case it already exists simply add a quick _"+1"_ or _"I have the same problem"_ to the existing issue thread.

##### Other

* Help us write the documentation
* Looking for something else to do? Get in touch..
