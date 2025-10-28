`javascript function generateReply(message) { const msg = message.toLowerCase();

if (msg.includes("hello") || msg.includes("hi")) { return "Hi there! 😊 How can I assist you today?"; } else if (msg.includes("help")) { return "Sure! Let me know what you need help with."; } else if (msg.includes("test")) { return "Testing successful! Everything looks good."; } else if (msg.includes("bye")) { return "Goodbye! Have a great day!"; } else { return "Thank you for your message!"; } }

function sendMessage() { const input = document.getElementById("userInput"); const message = input.value.trim(); if (message === "") return;

const chatBody = document.getElementById("chatBody");

const msgDiv = document.createElement("div"); msgDiv.classList.add("message", "sent"); msgDiv.textContent = message; chatBody.appendChild(msgDiv);

const replyText = generateReply(message); const replyDiv = document.createElement("div"); replyDiv.classList.add("message", "received"); replyDiv.textContent = replyText; setTimeout(() => chatBody.appendChild(replyDiv), 600);

chatBody.scrollTop = chatBody.scrollHeight; input.value = ""; } `
