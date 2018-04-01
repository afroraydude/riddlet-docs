# Object Refrence

## Socket.io objects

The socket.io objects `io` and `socket` are mostly unmodified from their original socket.io object. You can find information on these objects on the [socket.io docs](https://socket.io/docs/server-api/)

## `message` Object

Message objects are the go-to for any socket transmission that isn't already custom defined.

Example `messsage` object:

```json
{
  "data":"hello",
  "id":"152255174502021051",
  "room":"#default",
  "client":"username15chars",
  "color":"coral"
}
```

`data`: The message data. Plain text message is usually what the user typed in.

`id`: Custom ID of message based on UNIX timestamp plus some extra numbers added for good measure

`room`: The room the message is supposed to go to.

`client`: The client's custom name.

`color`: The user's color (used for the text 'Anonymous' on the web app)

## `serverInfo` Object

This object is sent time a user connects to the server.

Example `serverInfo` object:

```json
{
  "title": "Test Server",
  "rooms": ["/"],
  "maxcharlen": 500,
  "ip": "123.456.789.0",
  "isMod":false,
  "logo":"https://example.com/logo.png",
  "version":11
}
```

`version`: The minimum client version to use the server.
`title`: The server's name
`rooms`: The namespace (for socket.io)
`maxcharlen`: The maximum characters that can be in a message
`ip`: The public IP of the server
`isMod`: True if the server uses adapters
`logo`: The logo of the server

## `user` Object

This contains all of the user's information necessary for viewing messages.

Example `user` object:

```json
{
  "name": "92wM66tMWxd6l0I",
  "color": "purple"
}
```

`name`: Equivalent of the `client` variable in a message object.

`color`: Equivalent of the `color` variable in a message object.
