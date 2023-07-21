# Architectural messaging patterns: an illustrated guide

[Architectural messaging patterns: an illustrated guide](https://www.redhat.com/architect/architectural-messaging-patterns)

## **Message exchange architectures**

This section describes the messaging patterns that are relevant to the mechanism for transmitting messages between a sender and receiver.

### ****Pub-Sub****

A publisher pushes a message to topic/Inbox . A subscribers is linked to the topic and listens for messages being added. Once it gets a message, it processes it.

Typically need lots of information to be sent in the message body.

This is usually seen as one subscriber to one one topic

![Untitled](Architectural%20messaging%20patterns%20an%20illustrated%20gu%204325ecaeaeab4332b9f909a35cef0aa0/Untitled.png)

### Fanout

Same concepts as pub-sub but multiple subscribers are listening to a topic e.g Booking cancelled in Seaware. Activities Service cancels booked activities. F&B service cancels table booking.

![Untitled](Architectural%20messaging%20patterns%20an%20illustrated%20gu%204325ecaeaeab4332b9f909a35cef0aa0/Untitled%201.png)

### ****Unidirectional streaming****

Data is constantly being sent from a published to a subscriber, either directly or via a message broker.

### B****idirectional streaming****

Constant flow of data back a forth. Example is gRPC, which, once connection is established, allows data to flow between sender and receiver as required.

## Routing **exchange architectures**

### Unicast

App sends API requests. Internet knows how find API endpoint location, API sends response back.

![Untitled](Architectural%20messaging%20patterns%20an%20illustrated%20gu%204325ecaeaeab4332b9f909a35cef0aa0/Untitled%202.png)

### Broadcast

Senders emits message to all receivers on network

> Under ARP, the router knows the physical devices on the network and then correlates the device identifier, the MAC address, to the logical IP address, and then forwards the message accordingly.
> 

![Untitled](Architectural%20messaging%20patterns%20an%20illustrated%20gu%204325ecaeaeab4332b9f909a35cef0aa0/Untitled%203.png)

### ****Multicast****

Similar to broadcast but can have multiple groups of receivers. Live broadcasts over internet involve sender sending message to group of devices people are watching stream on.

![Untitled](Architectural%20messaging%20patterns%20an%20illustrated%20gu%204325ecaeaeab4332b9f909a35cef0aa0/Untitled%204.png)

### ****Anycast****

Receiver must meet certain conditions for the router to send a message to it 

![Untitled](Architectural%20messaging%20patterns%20an%20illustrated%20gu%204325ecaeaeab4332b9f909a35cef0aa0/Untitled%205.png)