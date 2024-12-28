```html
<div id="chat-area"></div>
<input type="text" id="messageInput" placeholder="Type your message...">
<button onclick="sendMessage()">Send</button>

<script src="https://cdn.jsdelivr.net/npm/graphql-ws@5.0.1/dist/index.js"></script>
<script>
  const wsClient = new WebSocket(
    'ws://your-vps-ip-or-domain:4000/graphql',
    'graphql-ws'
  );

  const sendMessage = () => {
    const content = document.getElementById('messageInput').value;
    if (content) {
      wsClient.send(JSON.stringify({
        type: 'start',
        id: '1',
        payload: {
          query: `mutation AddMessage($roomId: ID!, $content: String!) { addMessage(roomId: $roomId, content: $content) { id content timestamp sender { id name } } }`,
          variables: { roomId: "room-1", content }
        },
      }));
      document.getElementById('messageInput').value = '';
    }
  };

  wsClient.onmessage = (event) => {
    const data = JSON.parse(event.data);
    if (data.type === 'data' && data.payload.data) {
      const message = data.payload.data.addMessage;
      document.getElementById('chat-area').innerHTML += `<p>${message.sender.name}: ${message.content}</p>`;
    }
  };

  wsClient.onopen = () => {
    wsClient.send(JSON.stringify({
      type: 'start',
      id: '2',
      payload: { query: `subscription { messageAdded(roomId: "room-1") { id content timestamp sender { id name } } }` }
    }));
  };
</script>
```