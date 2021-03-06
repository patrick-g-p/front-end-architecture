## Custom Events

Firing custom events is incredibly useful.  Please use the power of them wisely:

### naming events 

Store your custom events in Enum Objects:

```js
const customEventsEnum = {
  LOGIN: 'login',
  scrollup: 'scrollup'
};

// reference
customEventsEnum.LOGIN // this will enable autocomplete
```
### namespacing events
You can and should prefix your events with a namespace to scope it to a component, page, section, or action type:
```js
counterEventsEnum = {
  INCREMENT: 'counter.increment',
  DECREMENT: 'counter.decrement',
};

userEventsEnum = {
 LOGIN: 'user.login',
 LOGOUT: 'user.logout'
};

```

### namespacing further:
If you want to namespace to a library or to your app preface the custom event like so:
```js
myapp:counter.increment
```

### multiple words
In the case of a component named `PeopleCounter`
The namespace would be `peoplecounter`  *without* kebabcase.

So the a long-winded custom event may be:

`mygreatapp:peoplecounter.finishcount`

### detail object
You can pass a `detail` object to your custom events to pass along information.

Try to define your `detail` object with generic fields of data.  
You can then use object creators and 
object extension to inherit type of data.

### dispatching the event
Dispatch the event from wherever you please.  
I recommend letting the event bubble to the top.  
You can always pass the `target` 
in as a value in the `detail` object.

#### dispatching from target element
```js

myTargetElement.dispatchEvent(counterEventsEnum.INCREMENT);

```

#### dispatching from document/window
```js

window.dispatchEvent(counterEventsEnum.INCREMENT, {
  detail: {
    target: // target element you want,
    component: //you could potentially pass 'this' 
  }
});

```


