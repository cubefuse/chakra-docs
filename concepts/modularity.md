# Modularity

Lets get familiar with the concept of modularity in the Chakra Framework.

## Plugins

The building blocks of Chakra apps are plugins. The Chakra library is only a thin layer that provides
an environment for plugins to function and communicate. 

Each Chakra app is a collection of modules or plugins. Each plugin focuses on a specific functionality, and is independent from others.

As an example, lets assume that we are developing a messaging app. 
The basic features can be: 
- tracking user identities
- sending messages to other users
- storing each user's messages securely

## Publish-Subscribe Model

How do these plugins talk to each other?

- Plugins publish **Messages** after performing some function. These messages are comprised of a **Topic** (basically the
type of the message) and a JSON body.
- Plugins also **Subscribe** to other topics. This way they specify types of messages they can respond to.
- When a new message is published, all plugins subscribed to that message's topic are notified instantly. 
- These plugins can then read the body of that message and perform some actions. Afterwards, they will also publish new
messages.

This pattern is called the Publish-Subscribe model (pub-sub, in short form). Chakra already implements this for you, and
you only have to specify what messages each plugin would be sending and what subscriptions each plugin would handle.
