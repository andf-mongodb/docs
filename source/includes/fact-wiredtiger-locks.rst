For most read and write operations, WiredTiger uses optimistic
concurrency control. WiredTiger uses only intent locks at the global,
database and collection levels. When the storage engine detects
conflicts between two operations, one will incur a write conflict
causing MongoDB to transparently retry that operation.

- Some global operations, typically operations involving
  multiple databases, require a global -- or "instance-wide" --
  exclusive lock. See also :ref:`faq-concurrency-lock-multiple-dbs`

- Certain administrative operations, such as repairing a database,
  require a database exclusive lock. See also
  :ref:`faq-concurrency-database-lock`
