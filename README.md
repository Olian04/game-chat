# game-chat
A chat window with support for /commands, commonly used in games

```js
const chat = new GameChat({
    el: '#chat',
    messages: []
});

chat.onMessage = msg => {
  // Will fire whenever the user or game-chat adds a message to the chat
  // the exeption being messages added using pushMessage wont trigger onMessage
  
  // msg is an array of { text: String, color: CssColorString }
}

chat.pushMessage([
  { text: 'Hello ', color: 'skyblue' },
  { text: 'world!', color: 'orangered' }
]);

chat.onCommand = ({ command, arg }) => ({ 
  response: { text: 'executed: ' + command, target: 'self', color: 'yellow' }
  prompt: { prompt: command, color: 'yellow' }
});

chat.whileTyping = ({ maybeCommand, message }) => [
  // Formats the text your are currently typing
  { text: maybeCommand, color: 'pink' },
  { text: message, color: 'white' }
];
```
