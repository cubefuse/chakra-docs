# Core Concepts

## Decentralized Apps (Dapps)

Decentralized applications are the next generation of connected apps. Some years ago, we were using traditional software
that had to be installed on a computer prior to use, and had no or little online interactions. Fast forward to today, we
see that many apps have migrated to the web, and a web browser is all we need to use these apps.

Today's web apps are based on the client-server architecture most of the time, meaning all data is processed on a remote
server operated by the app developers (cloud computing). This poses a number of problems regarding privacy of user data.
Developers incur huge maintenance costs as well.

Decentralized apps shift the responsibilities towards the user. Computations are done on the client computers itself, and
no data is sent to a server. This makes data more private, and eliminates down-times due to centralization. Maintenance
costs are minimal as well, because there are no servers to maintain.

While it seems that Dapps are the ultimate solution, keep in mind that they come with their own quirks as well. The
technologies are new and may be buggy. There are a lot of technical hurdles to overcome.

With Chakra, we aim to provide an optimal development experience and build an active plugin ecosystem,
collectively solving the issues that arise, as a community. 

## Plugins

The building blocks of Chakra apps are plugins. The Chakra library is only a thin layer that provides
an environment for plugins to function and communicate. 

Each Chakra app is a collection of modules or plugins. Each plugin focuses on a specific functionality, and is independent from others.

As an example, lets assume that we are developing a messaging app. 
The basic features can be: 
- tracking user identities
- sending messages to other users
- storing each user's messages securely

You should start by creating a new plugin module for each of these new features. Plugins should be able to work
independently.     

## Publish-Subscribe Model

How do plugins talk to each other? We use a message bus for communications between plugins.

Lets take YouTube as an example, to understand how this works. in YouTube, we subscribe to channels. When new
videos are published to those channels, we get notified. YouTube is acting as a broker to deliver us the videos. The
importance here is that content creators do not have to know that a certain subscriber exists. They can just publish 
their content and whoever actually needs those content will consume them.

Similarly, in Chakra,
- Plugins publish data as **Messages**. These messages are formatted as JSON objects and are published with a **Topic**.
- A topic is just like a channel in YouTube. Other plugins can **subscribe** to a topic. This way they specify types of
messages they can respond to.

> A topic is made of two parts: the name of the Chakra Plugin publishing the message, and the action that triggered the
message. For example: `Identity.UserLoggedIn` or `Messenger.MessageSent`.

- When a new message is published, all plugins subscribed to that message's topic are notified instantly. 
- These plugins can then read that message and perform any action accordingly. Afterwards, they can also publish new
messages, and the process will go on.

This pattern is called the Publish-Subscribe model (pub-sub, in short form). Chakra already implements this for you, and
you only have to specify what messages each plugin would be sending and what subscriptions each plugin would handle.

With the Pub-Sub model, we would be able to,
- isolate each plugin from others, making them independent.
- continue to run the app, even if a plugin crashes.
- Run multiple work in parallel, optimizing performance.
- Start / stop plugins on-demand, freeing up resources when they are not in use.

## Next Steps

Let's apply what we have learnt by [creating a new Chakra app](/essentials/creating-app.md).
