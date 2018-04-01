# Adapters

## What is an "Adapter"?

Adapters are extensions for Riddlet Server. They can be objects with functions or classes with functions. Adapters allow you to handle messages on your own.

## The functions of an Adapter

### All adapter functions

All adapter functions recieve specific parameters. They are as follows:

- `io`: The inner socket.io object, use for anything with the server-side of message handling (sending messages, rooms, sockets) (object)
- `socket`: The socket the message came from (object)
- `message`: The message in question (object)
- `messages`: the last messages sent (array of `message`)
- `serverInfo`: The server's public info (object)
- `user`: The user's token, decoded (object)

### `beforeMessage()`

This is ran before the normal message handler is loaded. If you wanted to handle custom commands, socket attributes, or otherwise modify any of the parameters, you would do it in this function.

### `afterMessage()`

This is ran right after the default message handler. If you wanted to keep messages for long term storage, you would probably handle that within this function.