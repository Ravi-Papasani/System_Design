# Optimistic locking vs Pessimistic locking

## Optimistic locking 
- I am optimistic that no one will modify the same data, so when the data is read from the database, it will not be locked, but when the data is updated again, it will be judged whether anyone has changed it during this period, and it can be controlled by the same version number or CAS
- Optimistic locking is suitable for scenarios with few write operations, because if there are many write operations, there will be more conflicts, which will lead to non-stop retry and reduce performance
- _Example_: version controllers such as git and svn

## Pessimistic locking 
- By default, someone will modify the same data, so when the data is read from the database, it will be locked and will be released when the update is over.
- Suitable for scenarios with many write operations
- _Example_: database row lock
