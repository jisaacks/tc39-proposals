# Concise Method Binding

This is a proposal that would allow using the proposed [`::`](https://github.com/zenparsing/es-function-bind) operator with the concise methods from ES2015.

The syntax would looks something like this:

```javascript
let lib = {
  ::doSomething() {
    return this;
  }
}
```

Desugared it would be equivalent to:

```javascript
var lib = {};
lib.doSomething = (function() {
  return this;
}).bind(lib);
```
