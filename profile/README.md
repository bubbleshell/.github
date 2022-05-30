# Bubble, a virtual operating system for chatbots

Bubble isn't just a framework. It's a **virtual operating system** specifically designed for managing complex chatbots. Bubble is designed to handle many common issues in modern chatbots: numerous messaging formats offered in different instant messaging apps, process scheduling, as well as the need to expose your IP address for the sake of webhooks. Bubble also takes care of your service quota and managing users and accounts to deliver the best omnichannel experience despite all the constraints.

Bubble is inspired by [Ika](https://github.com/reinhart1010/ika), an unfinished chatbot library by [Reinhart Previano K. (@reinhart1010)](https://reinhart1010.id), combined with his ambitions to build [an official cyborg account](https://github.com/reinhart1010/pr0xy). This new operating system will also be used for his internal automation services in the near future. However, unlike Ika, Bubble is designed to run as a whole operating system, instead of providing generic utilities to send messages.

Our official mascot is [Shiftine](https://reinhart1010.id/author/shiftine), who's now completely made up of recycled plastic materials glued with her favorite project Caps.

## Architecture

The Bubble system network is entirely composed of **Instances** and **Relays**. **Instances** are the ones running the real Bubble system while **Relays** are platform-specific adapters which work together with Bubble **Instances**.

Bubble is designed so its main instances may run without fully exposing their IP address. This works by replicating the convenience of Telegram Bot API's [`getUpdates`](https://core.telegram.org/bots/api#getting-updates) mechanism with numerous helpers which can store incoming webhook messages temporarily.

Bubble instances are written in [Rust](https://www.rust-lang.org/), while depend on [Apache CouchDB](https://couchdb.apache.org/) for database as well as [Socket.io](https://socket.io/) and [ZeroMQ](https://zeromq.org/) for network messaging. Helpers, however, may be written in numerous programming languages and database systems, so some of them can be installed in a regular PHP shared hosting or even serverless environments!
