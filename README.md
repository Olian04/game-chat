# game-chat
A stencil based custom element of a chat window with support for /commands, commonly used in games

```html
<game-chat
    onCommand="commandIssued()"
    onTyping="typing()"
    ></game-chat>
<script>
  const commandIssued = ({ command, arg }) => ({ 
    response: { text: 'executed: ' + command, target: 'self', color: 'yellow' }
    prompt: { prompt: command, color: 'yellow' }
  });
  
  const typing = ({ maybeCommand, message }) => [
    // Formats the text your are currently typing
    { text: maybeCommand, color: 'pink' },
    { text: message, color: 'white' }
  ];
</script>
```
