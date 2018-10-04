##Blocking I/O

###### Python

```
import requests
print('Start')
response = requests.get('http://www.google.com')

# just print out the first 30 characters of the response body
print(response.text[0:30])
print('Done!')
```

Prints:

```
Start
<!doctype html><html itemscope
End
```

##Non-blocking I/O

###### Node.js

```
var request = require('request');
console.log("Start");
request('http://www.google.com', function (error, response, body) {
    // just print out the first 30 characters of the response body
    console.log(body.slice(0, 30))
})
console.log("Done!");
```

Prints:

```
Start
Done!
<!doctype html><html itemscope
```

Callback function: a function passed as an argument to another function that is expected to be executed at some later time (perhaps when an operation is completed, or a specific event occurs)

event loop
Node just continues to listen for events
you specify what code to execute whenever an event happens
if something requires I/O, that's spun off in the background, so the event loop can handle other callbacks

######Global Installation

######Modules

* Modules are js files
* can be required, so that you can bring code from one file to another
