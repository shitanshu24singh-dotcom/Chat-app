<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Chat App</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f4f9;
      margin: 0;
      padding: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }
    .chat-container {
      background: #fff;
      width: 400px;
      height: 600px;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
      display: flex;
      flex-direction: column;
    }
    .chat-header {
      background: #2196F3;
      color: white;
      padding: 15px;
      text-align: center;
      border-radius: 10px 10px 0 0;
    }
    .chat-box {
      flex: 1;
      padding: 15px;
      overflow-y: auto;
    }
    .message {
      margin: 10px 0;
      padding: 10px;
      border-radius: 5px;
      max-width: 70%;
    }
    .sent {
      background: #2196F3;
      color: white;
      margin-left: auto;
    }
    .received {
      background: #e0e0e0;
      margin-right: auto;
    }
    .chat-input {
      display: flex;
      padding: 10px;
      border-top: 1px solid #ccc;
    }
    .chat-input input {
      flex: 1;
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    .chat-input button {
      margin-left: 10px;
      padding: 10px 15px;
      border: none;
      border-radius: 5px;
      background: #2196F3;
      color: white;
      cursor: pointer;
    }
    .chat-input button:hover {
      background: #1976D2;
    }
  </style>
</head>
<body>
  <div class="chat-container">
    <div class="chat-header">Chat App</div>
    <div class="chat-box" id="chatBox"></div>
    <div class="chat-input">
      <input type="text" id="messageInput" placeholder="Type a message...">
      <button onclick="sendMessage()">Send</button>
    </div>
  </div>

  <script>
    const chatBox = document.getElementById("chatBox");
    const messageInput = document.getElementById("messageInput");

    function sendMessage() {
      const msg = messageInput.value.trim();
      if (!msg) return;

      const messageDiv = document.createElement("div");
      messageDiv.className = "message sent";
      messageDiv.textContent = msg;
      chatBox.appendChild(messageDiv);

      messageInput.value = "";
      chatBox.scrollTop = chatBox.scrollHeight;

      // Simulated reply
      setTimeout(() => {
        const replyDiv = document.createElement("div");
        replyDiv.className = "message received";
        replyDiv.textContent = "Got it: " + msg;
        chatBox.appendChild(replyDiv);
        chatBox.scrollTop = chatBox.scrollHeight;
      }, 1000);
    }
  </script>
</body>
</html>
