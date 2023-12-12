<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Chat</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            display: flex;
            flex-direction: column;
            height: 100vh;
        }

        #chat-box {
            flex: 1;
            overflow-y: auto;
            padding: 10px;
            border-bottom: 1px solid #ccc;
        }

        #message-input {
            display: flex;
            padding: 10px;
            align-items: center;
            justify-content: space-between;
            background-color: #f5f5f5;
        }

        #message-input input {
            flex: 1;
            padding: 8px;
            margin-right: 10px;
            border: 1px solid #ccc;
        }

        #send-button {
            cursor: pointer;
            padding: 8px 15px;
            background-color: #4caf50;
            color: white;
            border: none;
            border-radius: 4px;
        }
    </style>
</head>
<body>
    <div id="chat-box"></div>
    <div id="message-input">
        <input type="text" id="message" placeholder="Type your message...">
        <button id="send-button" onclick="sendMessage()">Send</button>
    </div>

    <script>
        function sendMessage() {
            var messageInput = document.getElementById("message");
            var chatBox = document.getElementById("chat-box");

            var message = messageInput.value.trim();
            if (message !== "") {
                var newMessage = document.createElement("p");
                newMessage.textContent = "You: " + message;
                chatBox.appendChild(newMessage);
                messageInput.value = "";
                chatBox.scrollTop = chatBox.scrollHeight;
            }
        }
    </script>
</body>
</html>
