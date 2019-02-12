ember-cli-native-stencil
==============================================================================

This addon lets you use WebComponents built with [Stencil.js](https://stenciljs.com/)
in your Ember applications.


Compatibility
------------------------------------------------------------------------------

* Ember.js v2.18 or above
* Ember CLI v2.13 or above


Installation
------------------------------------------------------------------------------

```
ember install ember-cli-native-stencil
```


Usage
------------------------------------------------------------------------------

This addon works at build time, which means that once it is installed, there's
nothing left to do from the developer.

## Handling custom events

For the moment, if you want your application to act upon custom events, you
can do so as always in your ember app (see example below for a refresher).

```hbs
<my-web-component custom-change={{action 'myCustomHandler'}} />
```

Remind that in order to retrieve the custom data that your custom event may carry,
you will have to do **one of the following**:

```js
// Option 1: from the component
//
// Your template file looks like this
// <my-web-component custom-change={{action 'myCustomHandler'}} />
//
// Your JS action should look like this
myCustomHandler(event) {
  let data = event.target.value
}
```

```js
// Option 2: from the template
//
// Your template file looks like this
// <my-web-component custom-change={{action 'myCustomHandler' value="target.value"}} />
//
// Your JS action should look like this
myCustomHandler(customData) {
  // customData is already bound to the correct value
}
```

License
------------------------------------------------------------------------------

This project is licensed under the [MIT License](LICENSE.md).

