# [_vm-browserify_](https://github.com/warren-bank/fork-vm-browserify/tree/fork)

Fork of [_vm-browserify@1.1.2_](https://github.com/browserify/vm-browserify/releases/tag/v1.1.2): [`vm`](https://nodejs.org/api/vm.html) module for the browser

# example

Just write some client-side javascript:

``` js
var vm = require('@warren-bank/vm-browserify');

window.addEventListener('load', function () {
    var res = vm.runInNewContext('a + 5', { a : 100 });
    document.querySelector('#res').textContent = res;
});
```

compile it with [browserify](http://github.com/substack/node-browserify):

```
browserify entry.js -o bundle.js
```

then whip up some html:

``` html
<html>
  <head>
    <script src="/bundle.js"></script>
  </head>
  <body>
    result = <span id="res"></span>
  </body>
</html>
```

and when you load the page you should see:

```
result = 105
```

# methods

## vm.runInNewContext(code, context={})

Evaluate some `code` in a new iframe with a `context`.

Contexts are like wrapping your code in a `with()` except slightly less terrible
because the code is sandboxed into a new iframe.

# install

The [upstream library](https://github.com/browserify/vm-browserify) is depended upon by browserify,
so you should just be able to `require('vm')` and it will just work.
However if you want to use [this fork](https://github.com/warren-bank/fork-vm-browserify/tree/fork),
you must install it with [npm](http://npmjs.org):

```bash
npm install @warren-bank/vm-browserify
```

# license

* [_vm-browserify@1.1.2_](https://github.com/browserify/vm-browserify/releases/tag/v1.1.2) is [MIT](https://github.com/browserify/vm-browserify/blob/v1.1.2/LICENSE)
* all original code belonging to this fork that is not in the upstream project is [GPL-2.0](https://github.com/warren-bank/fork-vm-browserify/blob/fork/LICENSE.txt)
