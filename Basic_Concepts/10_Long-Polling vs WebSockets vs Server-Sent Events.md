# Long-Polling vs WebSockets vs Server-Sent Events

## Standard HTTP request
- The client opens the connection and requests data from the server
- Server calculates the response result
- The server returns the result to the customer through the opened connection

## Ajax Polling (used in most Ajax applications)
- The client opens the connection and requests data from the HTTP server.
- The request will be sent to the server at regular intervals (0.5s)
- The server calculates the response result and returns it to the client
- The client keeps repeating steps 1-3 above to get updates from the server

The problem is: The client keeps sending requests to the server, but most of the returned results are empty, which greatly increases the HTTP load

## HTTP Long-Polling
- The client opens the connection and requests data from the HTTP server.
- If the server has no data, hold the connection until there is data or the connection times out
- Once there is data, the server returns the result to the client
- After receiving the result, the client will send another long polling request. So the server always has a long polling request waiting
- No long polling request is timeout, once timeout, the client will send the request again

## WebSockets (TCP)
- The client establishes a connection with the server through a WebSocket handshake
- After the connection is established successfully, the client and server can send data to each other
- Applicable to real-time messaging system Whatsapp, FB messager, Wechat, etc.

## Server-Sent Event(SSEs)
- The client sends a HTTP request to the server, such as opening a web page
- The requested webpage has established a connection with the server
- Once there is new data, the server will actively send data to the client
- Suitable for displaying real-time trading data of stocks
