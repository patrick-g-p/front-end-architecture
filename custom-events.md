## Custom Events

Firing custom events is incredibly useful.  Please use the power of them wisely:

### naming events 

Store your custom events in Enum Objects:

```js
const customEventsEnum = {
  USER_LOGIN: 'user-login'
};

// reference
customEventsEnum.USER_LOGIN // this will enable autocomplete
```
Note the *kebab-case* for these event names.  It helps visually distinguish them from DOM events.

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
