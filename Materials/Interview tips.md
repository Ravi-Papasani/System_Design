## How to sort out your clues during an interview
- Discuss who the user is
- According to user discussion feature and function
- Ask about the system needs estimate traffic
- According to the feature, discuss which data the system needs to store and serve, and what to store these data, and discuss the SQL/NoSQL/cache/object storage/hdfs choice
- According to the data, design the service. Drawing.
- work through a use case, connect all services together, and modify the diagram just drawn at the same time. For example, do uber eats, discuss that the user wants to order food, go to the restaurant to receive the order, and then the driver receives the order. . . .
- Discuss the details of the use case, such as how to recognize when the uber eats driver enters a certain area, and how to store it in the cache. The interviewer will drive your design throughout the entire process, and will not leave you talking to yourself.
- The interviewer will ask what to do if some links are down. Mainly to avoid Single Point of Failure
   - Replica, master-slave, active-passive or
   - Periodically save the snapshot on the disk, and then save the action log... If you hang up, you can restore it again.
- Finally, I will ask how to scale out. multi-instance, partition, Load balance. Occasionally talk about Service Mesh, Microservice.

The above process refers to one-acre three-part land, which is suitable for students who do not have much work experience and who are nervous and clueless in the interview. You can simply refer to it.
