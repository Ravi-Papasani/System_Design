# Load Balancing

## Benefits of Load Balancing
- Provide uninterrupted service.
- Less downtime and high throughput.
- It is easier to manage incoming requests.
- Better allocation of requests, not overloading a certain machine/server.

## Load Balancing Algorithm
- First, Load Balancing will use Health Checks to forward requests only to healthy machines.
- Then choose one of these healthy machines according to different algorithms. Algorithm includes
  - Forward to the least connected machine: avoid overloading of certain machines Least Connection
  - Forward to the machine with the shortest response time Least Response Time
  - Forward to the machine with the least traffic Least Bandwidth
  - Round Robin
  - Weighted Round Robin
  - **IP Hash**： calculate a hash(IP address)

## L4(Transport Layer) and L7(Application Layer)
- L4 is based on the fourth layer of the OSI model-TCP layer, LB can forward through IP address and Port number.
- L7 is based on the seventh layer of the OSI model application layer, LB can forward application layer information such as URL.

## Nginx and HAProxy
- **Nginx**
  - It is L7 LB, which can load a large number of connections and has very strong performance.
  - Can be a reverse proxy, static web page, and image server.
  - The Community is active and there are many third-party plugins available.
- **HAProxy**
  - L4 LB, pure load balancer
  - Superior to Nginx in concurrent processing
  - There are many load balancing strategies.
