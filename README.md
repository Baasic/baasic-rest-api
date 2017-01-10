# Baasic REST API

Baasic REST API Documentation provides detailed information for all Baasic [REST API](https://api.baasic.com/v1/) end-points. Documentation can be found on the [Baasic Developer Center](http://dev.baasic.com) section

## Baasic Modules

Baasic back-end contains various built-in modules that can be easily consumed through the Baasic REST API. More details can be found [here](http://dev.baasic.com/docs/).

## Supported features

This section will describe what features are supported on all REST API end-points.

### HTTP format support 
- JSON (application/json)
- HAL JSON (application/hal+json)

It's important to know that Baasic supports and recommends HAL+JSON format as default. Baasic SDKs will have HAL+JSON set as default HTTP format for communication with the back-end. For more details on the HAL+JSON conventions, please visit one of the following resources [JSON Schema Hypermedia](http://json-schema.org/latest/json-schema-hypermedia.html) or [HAL Specification](http://stateless.co/hal_specification.html).

### HAL 

Resources returned from Baasic in HAL format look similar to this:

```javascript
{
    "key": "my-key",
    "value": "my-value",
    "dateCreated": "2015-01-01T14:24:56.795849Z",
    "dateUpdated": "2015-01-01T14:24:56.795849Z",
    "id": "kZyiWLUzz8dqAjHiO1gxXK",
    "_links": {
        "self": {
            "href": "https://api.baasic.com/<version>/<api-key>/key-values/<key>",
            "templated": false
        },
        "post": {
            "href": "https://api.baasic.com/<version>/<api-key>/key-values",
            "templated": false
        },
        "put": {
            "href": "https://api.baasic.com/<version>/<api-key>/key-values/<key>",
            "templated": false
        },
        "delete": {
            "href": "https://api.baasic.com/<version>/<api-key>/key-values/<key>",
            "templated": false
        }
    },
    "_embedded": { }
}
```

HAL links are preferred way to access Bassic back-end. To manually access the predefined links, one should use *_links* property from the returned resource:

```javascript
_links.put.href
_links.delete.href
```

### Embeds

To reduce the number of round-trips to back-end, embeds can be used. Available embeds can be found in the *_embedded* property in case of HAL+JSON format, or in the object itself in case of JSON. They look similar to this:

_HAL+JSON_
```javascript
"_embedded": {
	"author": { },
	"comments": [ ],
	"ratings": [ ],
	"tags": [ ]
}
```

_JSON_
```javascript
{
	"author": { },
	"comments": [ ],
	"ratings": [ ],
	"tags": [ ]
}
```

**Note:** They are returned as empty objects or arrays until explicitly requested through the _embed_ query parameter.

### Fields

To define what fields should be returned from the REST API, _fields_ query parameter should be used. Comma separate the field names and note that dot notation is supported for embedded resources. 

### Allowed Search Types

1. *BQL or Baasic Query Language* can be used through the _searchQuery_ query parameter in order to filter through available resources. BQL uses standard SQL syntax, e.g. WHERE clause: 

 ```
 WHERE Field = 'Value'
 ```


	**Note:** This type of search is case-sensitive.

2. In contrast to the BQL search, *Phrase Search* should contain expected search keywords. Only
resource containing the search keywords will be listed. 

	**Notes:** 
    - This type of search is case-insensitive;
    - Some resource properties may not be searchable.

## Issue reporting

Before you create a new issue, please make sure it hasn't already been reported. In case it already exists simply add a quick _"+1"_ or _"I have the same problem"_ to the existing issue thread.

## Other

* Help us write the documentation
* Looking for something else to do? Get in [touch](https://groups.google.com/forum/#!forum/baasic-baas)..