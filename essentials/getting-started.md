# Getting Started

Developing a new decentralized app? You're in the right place. Get started by including the Chakra library in your application.

## npm package

This is the recommended method for using Chakra.

Requires at least Node.js v6 and npm v3.

```sh
npm install @chakrajs/framework
```

If you are using `yarn` (recommended), use this instead.

```sh
yarn add @chakrajs/framework
```

You can then import the npm package to your code using as follows, depending on your environment.

```js
const Chakra = require('@chakrajs/framework')
// or
import Chakra from '@chakrajs/framework'
```

## `<script>` include
Directly include with `<script>` tag on your html pages. This only works for web browsers.
`Chakra` would be included as a global variable.

- Download and use

Downloads can be found in the [GitHub Releases](https://github.com/cubefuse/chakra/releases) page.

- Use from CDN

```html
<!-- Development version -->
<script src="https://unpkg.com/@chakrajs/framework/dist/index.js"></script>

<!-- Minified version -->
<script src="https://unpkg.com/@chakrajs/framework/dist/index.min.js"></script>
```

## Initializing Chakra app

To include Chakra in your project:
```js
const chakra = new Chakra()
chakra.plug(
  // Add plugins you want to use as arguments here
)
chakra.start()
```

## Next steps

- [Learn](/concepts/modularity.md) the concepts behind Chakra
- [Create a new app](/essentials/creating-app.md) with Chakra Framework
