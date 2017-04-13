# JSDAD
JavaScript - Deans Anything Downloader

## The What!
 - Simple, Light Weight, Fast, Multi Treading Safe, Multi Browser Support

## The Function Usage Overview (Integration)
```javascript
/* Import the [JSDad.js](/jsdad.js) script*/

/* Call the Function Once JSDad.js has loaded*/
AnythingDownloader(method, postdata, url, datatype, filename, mimetype, prevalidation, onprevalidationerror, postvalidation,  onpostvalidationerror);
```

Supported Args:
- *method*: _'GET'_ or _'POST'_
- *postdata*: (Any Format, Only used when method is POST)
- *url*: any ISO RFC formated url
- *datatype*: _'text'_ or _'json'_ or _'blob'_
- *filename*: (any valid filename with or without an extension)
- *mimetype*: ex: 'text/html' or major/minor, see ISO RFC MIME Types
- *prevalidation*: function(request, data) returns boolean
- *onprevalidationerror*: function(request, data) called if prevalidation returns false
- *postvalidation*: function(request, data) returns boolean
- *onpostvalidationerror*: function(request, data) called if postvalidation returns false


## The How?
Example: Great White Sharks - Source Google.co.za
```javascript
AnythingDownloader(
    method='GET', 
    postdata=null,
    url='https://www.google.co.za/search?q=great%20white%20Sharks',
    datatype='text',
    filename='download.html',
    mimetype='text/html',
    prevalidation=function(request, data){
        /* pre validate data before connecting to server and or request and return a boolean value*/
        return true;
    },
    onprevalidationerror=function(request, data){
        /* Handle pre-validation Error*/
        return true;
    },
    postvalidation=function(request, data){ 
        /* post validate data before connecting to server and or request and return a boolean value*/
        return true;
    },
    onpostvalidationerror=function(request, data){
        /* Handle post-validation Error*/
        return true;
    }
);
```
