# Riddlet Bots

Riddlet Bots are chat programs that use the Riddlet functions to send and recieve messages on a given server. 

## Installing the official bot library

Installation is fairly simple. Just run `npm install --save riddlet-bot` in your project directory.

## Your first bot

The official bot library allows for very barebones bot creation.

### Simple Log Bot

To create a bot, you first want to create a new `RiddletBot` class.

```js
var bot = new RiddletBot("https://talk.needformea.de")
```

You should know if if this works when you get a token printed to your terminal. (ie: `xxxxxxxxxxxxx.yyyyyyyyyyyy.zzzzzzzzzzzz`)

We now want to stop the bot process and put that token as a second parameter. This allows our bot to have the same token each time it connects to the server.

```js
var bot = new RiddletBot("https://talk.needformea.de", "xxxxxxxxxxxxx.yyyyyyyyyyyy.zzzzzzzzzzzz")
```

Your bot should now log every message it recieves from the server. 

### Custom Message Handler

Now to create a custom Message Handler.

Here is an example message handler that we will be using.

```js
var xMessageHandler = function (bot, message) {
  if(message.data === "!info") {
    bot.SendMessage("test", "#all")
  }
}
```

Lets go line by line as to each part of the Message Handler

```js
var xMessageHandler = function (bot, message)
```

This line defines the message handler. The `bot` parameter is the `RiddletBot` object that we defined. The `message` parameter is a [message](/object-refrence/#message-object) object.

```js
if(message.data === "!info")
```

This checks to see if the message's text is equal to "!info" (ie: the user sent the mesesage "!info")

```js
bot.SendMessage("test", "#all")
```

This sends a message, and does all necessary compatibility checks with the server for you. The first parameter is the `message` that you want to send (equivalent to `message.data`) and the second parameter is the room you want it to go. 

Now we want to import it into our bot.

```js
var bot = new RiddletBot("https://talk.needformea.de", "xxxxxxxxxxxxx.yyyyyyyyyyyy.zzzzzzzzzzzz", xMessageHandler)
```

And that's your first bot!