# Chat Application

This is a basic multi-client chat application written in Java, which allows multiple clients to communicate with each other via a server. The chat is hosted locally, with each client being able to send and receive messages in real-time.

## Table of Contents
- [Project Structure](#project-structure)
- [Features](#features)
- [Requirements](#requirements)
- [Usage](#usage)
- [Code Explanation](#code-explanation)
- [License](#license)

---

### Project Structure

The application is divided into three main classes:

1. **Server**: Manages incoming client connections and starts client handler threads.
2. **ClientHandler**: Handles the communication between the server and each client.
3. **Client**: Allows users to connect to the server, send, and receive messages.

---

### Features

- **Multi-Client Support**: Multiple clients can connect to the server simultaneously.
- **Real-Time Communication**: Messages sent by a client are instantly broadcasted to all other clients.
- **Graceful Client Disconnection**: When a client disconnects, the server notifies other clients.

---

### Requirements

- **Java Development Kit (JDK)** 8 or above
- **IDE** (Optional, e.g., IntelliJ IDEA, Eclipse, or Visual Studio Code) to edit and run the code
- **Terminal** (Command Line) to run the program manually

---

### Usage

1. **Clone the Repository**

   Clone the repository containing this project or download the files.

   ```bash
   git clone https://github.com/capybara-brain346/Multi-Client-Chat.git
   cd Multi-Client-Chat
   ```

2. **Compile the Code**

   Open a terminal or command prompt, navigate to the project directory, and compile the Java files.

   ```bash
   javac Server.java ClientHandler.java Client.java
   ```

3. **Start the Server**

   In the terminal, start the server with the following command:

   ```bash
   java Server
   ```

   The server will be running on `localhost` at port `1234`.

4. **Start the Client(s)**

   Open a new terminal or command prompt instance for each client you want to connect to the server and execute the following command:

   ```bash
   java Client
   ```

5. **Enter a Username**

   Upon running the `Client` program, you will be prompted to enter a username. This username will be displayed with each message you send.

6. **Chat**

   Once connected, type messages in each client terminal to send them to other clients in the chat room.

---

### Code Explanation

#### 1. Server Class
The `Server` class is responsible for accepting incoming connections from clients. It listens on a specified port (`1234`) and starts a new `ClientHandler` thread for each connected client.

#### 2. ClientHandler Class
The `ClientHandler` class is a runnable class that manages the communication for a single client. It performs the following functions:
- Reads messages sent by the client.
- Broadcasts the message to other connected clients.
- Notifies other clients if a client disconnects.

#### 3. Client Class
The `Client` class allows users to connect to the server and send messages to other clients. The class provides two main functions:
- `sendMessage()`: Reads input from the console and sends messages to the server.
- `listenForMessage()`: Listens for incoming messages from the server and displays them on the console.

---

### Example Usage

```bash
java Server
# Output: "A new client has connected."

java Client
# Prompt: "Enter your username: "
# Example: "Alice"
# Start chatting as "Alice"

java Client
# Prompt: "Enter your username: "
# Example: "Bob"
# Start chatting as "Bob"
```

Each message from a client will be broadcasted to all connected clients, so "Alice" and "Bob" can see each other's messages.

---
