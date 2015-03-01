# EventDispatcher.js

The minimal implementation of Event Pub/Sub system in JavaScript.




## Usage

like this.

```javascript
var hoge = new EventDispatcher();

hoge
	.on('success', function(code){
		console.log('success: response code=%s', code);
	})
	.on('error', function(code){
		console.log('error: response code=%s', code);
	});

hoge.fire('success', 200);
```




## Methods

all methods are chainable.




### EventDispatcher#on(type, listener)

Attach an event handler.


#### parameters

| name | type | description
| ---  | ---  | ---
| type | string | event type
| listener | Function | the event listener


#### example

```javascript
var a = new EventDispatcher();

a.on('event', handler);
```




### EventDispatcher#off(type, listener)

Detach the event listener.

If the event listener is detached for more than twice,
this method detach all of them.


#### parameters

| name | type | description
| ---  | ---  | ---
| type | string | event type
| listener | Function | the event listener


#### example

```javascript
a.off('event', callback);
```




### EventDispatcher#fire

Fire the event.


#### parameters

| name | type | description
| ---  | ---  | ---
| type | string | event type
| optArgs | ...* | arguments

```javascript
a.fire('event', arg1, arg2, arg3);
```




### LICENSE

MIT