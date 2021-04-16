# Indexes
- Indexes can be added to a single field or a compound field, usually the field after where
- Speed up data retrieval.
- Can not add indexes to all fields, because the index will take up space.
- Reduce the performance of data writing, such as insert, update, delete, because each write operation requires updating the index in addition to writing data. This is also one of the reasons why not all fields can be indexed.
  