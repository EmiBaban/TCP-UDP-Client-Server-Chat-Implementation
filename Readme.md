# HTTP Library Client

**Author:** Baban Mihai-Emilian (324CD)

## Project Overview

This project implements a chat server and subscriber clients using TCP and UDP sockets in C. The system enables real-time communication between multiple clients, demonstrating mastery in socket programming, event-driven architecture, and resource management.

Originally based on the laboratory 7 skeleton code, the project expands on it to deliver a robust client-server communication model.

## Architecture

The system consists of two main components:

- **Server (`server.c`)**: Manages TCP and UDP connections, maintaining a list of clients and topics, and efficiently handles client subscriptions and message delivery.
- **Subscriber (`subscriber.c`)**: Acts as a client that connects to the server, subscribes/unsubscribes to topics, and receives messages.

### Core Data Structures

- `struct chat_packet`: Stores essential information about a packet sent to subscribers or the server.
- `struct client`: Stores client-specific data such as ID, socket, and topic subscriptions.

## Server Features

- Parses the port number and initializes two sockets (TCP and UDP).
- Binds the server address and listens for incoming TCP connections.
- Uses the `poll` function to efficiently monitor and process events across multiple sockets.
- Dynamically manages connected clients and their subscriptions.
- Handles new and existing client connections, ensuring seamless communication.
- Receives messages from clients using a custom `recv_all()` function.
- Gracefully handles client disconnections and resource cleanup.

## Subscriber Features

- Establishes a TCP connection to the server.
- Uses an event loop with `poll()` to listen for both keyboard input and server messages.
- Supports the following commands:
  - `subscribe <topic>`: Subscribe to a topic for receiving messages.
  - `unsubscribe <topic>`: Unsubscribe from a topic.
  - `exit`: Disconnects from the server and exits the client.

## Why Recruiters Should Care

- **Socket Programming:** Demonstrates proficiency in both TCP and UDP protocols.
- **Event-Driven Design:** Efficient handling of multiple clients using `poll`.
- **Robustness:** Effective management of client connections and topic subscriptions.
- **Clean Architecture:** Separation of concerns between server and client modules.
- **Scalability:** Designed to handle multiple simultaneous connections.
- **Code Quality:** Emphasis on resource management and clean error handling.

## How to Run

1. Compile the server and subscriber source files.
2. Start the server by specifying the port number.
3. Launch one or more subscriber clients and connect to the server.
4. Use the supported commands to interact with the chat system.

---
