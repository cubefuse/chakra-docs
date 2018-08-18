# Creating a Chakra App

## Quick Start

1. Start by setting up your project as described in the [Getting Started](/essentials/getting-started.md) guide.

2. After importing the Chakra library, you can use it by creating a new instance.

 ```js
const chakra = new Chakra({
    name: 'Your App Name',
    version: 'Your App Version'
});
```

3. To add plugins to Chakra, use the `plug` function and pass a list of objects that implement the `Chakra.Plugin` interface as arguments.
```js
// Below, both SomePlugin and SomeAnotherPlugin are Chakra Plugins.
const plugin1 = new SomePlugin();
const plugin2 = new SomeAnotherPlugin();
chakra.plug(plugin1, plugin2);
```
For more information about developing plugins, see [Creating a Chakra Plugin](/essentials/creating-plugins.md).

4. To start the Chakra app, simply call,
```js
chakra.start()
```

## Next Steps

To add new functionality to your Chakra app, you'll be developing plugins. To learn how to develop plugins, check 
[this page](/essentials/creating-plugins.md).
