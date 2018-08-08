# Core Concepts

Lets get familiar with the basic concepts of Chakra Framework.

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
collectively solving the issues that arise as a community. 

## Modularity

Chakra works a little differently from other app frameworks we are used to. Each Chakra app is a collection 
of modules or plugins. Each plugin focuses on a specific functionality, and is independent from others.

Lets take an example. Lets assume that we are developing a messaging app. 
The basic features can be: 
- tracking user identities
- sending messages to other users
- storing each user's messages securely

Each of these features can be encapsulated into a separate plugin module.

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
