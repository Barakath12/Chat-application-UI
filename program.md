<title>Smart Chat UI</title> <style> body { font-family: "Poppins", sans-serif; background-color: #ffffff; color: #bc4262; display: flex; justify-content: center; align-items: center; height: 100vh; margin: 0; }
.chat-container {
  width: 400px;
  height: 600px;
  border: 2px solid #000;
  display: flex;
  flex-direction: column;
  background-color: #fff;
  box-shadow: 5px 5px 15px rgba(0, 0, 0, 0.2);
}

.chat-header {
  background-color: #000;
  color: #fff;
  text-align: center;
  padding: 15px;
  font-size: 20px;
  font-weight: bold;
  letter-spacing: 1px;
}

.chat-body {
  flex: 1;
  padding: 15px;
  overflow-y: auto;
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.message {
  padding: 10px 15px;
  border: 1px solid #000;
  max-width: 70%;
  font-size: 14px;
  word-wrap: break-word;
}

.sent {
  align-self: flex-end;
  background-color: #f0f0f0;
}

.received {
  align-self: flex-start;
  background-color: #e8e8e8;
}

.chat-footer {
  display: flex;
  border-top: 2px solid #000;
  padding: 10px;
}

.chat-footer input {
  flex: 1;
  padding: 10px;
  border: 1px solid #000;
  outline: none;
  font-size: 14px;
}

.chat-footer button {
  background-color: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin-left: 5px;
  cursor: pointer;
  transition: 0.3s;
}

.chat-footer button:hover {
  background-color: #444;
}
</style>
Smart Chat UI
<div class="chat-body" id="chatBody">
  <div class="message received">Hello! How can I help you today?</div>
</div>

<div class="chat-footer">
  <input type="text" id="userInput" placeholder="Type your message..." />
  <button onclick="sendMessage()">Send</button>
</div>
<script> function generateReply(message) { const msg = message.toLowerCase(); if (msg.includes("hello") || msg.includes("hi")) { return "Hi there! 😊 How can I assist you today?"; } else if (msg.includes("help")) { return "Sure! Let me know what you need help with."; } else if (msg.includes("test")) { return "Testing successful! Everything looks good."; } else if (msg.includes("bye")) { return "Goodbye! Have a great day!"; } else { return "Thank you for your message!"; } } function sendMessage() { const input = document.getElementById("userInput"); const message = input.value.trim(); if (message === "") return; const chatBody = document.getElementById("chatBody"); const msgDiv = document.createElement("div"); msgDiv.classList.add("message", "sent"); msgDiv.textContent = message; chatBody.appendChild(msgDiv); const replyText = generateReply(message); const replyDiv = document.createElement("div"); replyDiv.classList.add("message", "received"); replyDiv.textContent = replyText; setTimeout(() => chatBody.appendChild(replyDiv), 600); chatBody.scrollTop = chatBody.scrollHeight; input.value = ""; } </script>
