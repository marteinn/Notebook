# Tip: Using the Fetch Api with Django Rest Framework

## Server
First, make sure you use the SessionAuthentication in Django. Put this in your settings.py

```python
# Django rest framework
REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES': [
        'rest_framework.authentication.SessionAuthentication'
    ]
}
```

## Client 
Then start with including the getCookie method from the [Django Docs](https://docs.djangoproject.com/en/1.8/ref/csrf/#ajax).

Finally use the `fetch` method to call your endpoint.

```javascript
var myData = {
    hello: 1
};

fetch("/api/v1/endpoint/5/", {
    method: "put",
    credentials: "same-origin",
    headers: {
        "X-CSRFToken": getCookie("csrftoken"),
        "Accept": "application/json",
        "Content-Type": "application/json"
    },
    body: JSON.stringify(myData)
}).then(function(response) {
    return response.json();
}).then(function(data) {
    console.log("Data is ok", data);
}).catch(function(ex) {
    console.log("parsing failed", ex);
});
```

Easy! (Remember this will currently only work on Chrome and Firefox)
