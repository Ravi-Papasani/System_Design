# A step-by-step guide

## The first step is to clarify the needs
Ask the interviewer about the specific requirements and functions of the system. For example, to design a Twitter, you can ask:
- Can users tweets and follow other users
- Need to show the user's timeline
- Can Tweet contain videos or pictures
- Do you need push notifications?
- Can you search for Tweets
- Etc., etc

## The second step is to estimate
- System scale; for example, DAU, users tweet several times a day, QPS, Peek QPS (QPS*3)
- storage
- bandwidth

## The third step is to define the system interface (API)
- Corresponds to the needs of the first step

## The fourth step is to define the data model
- Define table structure, fields
- SQL or NoSQL
- How to store static files, pictures, videos (ex., AWS S3)

# High-level design
Draw an Architectural diagram

## Detailed design
### Dig deeper into 2, 3 important parts, such as
- Data storage, we want to store a large amount of data, how to do Data partitioning
- How to optimize search
- How to recover from disaster
- and many more

## Identify and resolve system bottlenecks
- Does the system have a single point of failure
- Is there enough Replication?
- How to monitor the system, how and under what circumstances to issue a warning to the Application owner?
