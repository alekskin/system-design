# Relational Databases

Relational (SQL) database enforces structure (schema).
Non-relational (No-SQL) do not.

SQL (structured query language). Powerful query language.

SQL DB main principles known as  ACID:
- **Atomicity**
  Several operations construct a Transaction: all succeed or all fail

- **Concistency**
  Any transaction operates on the current state.
  There is no "stale" state in DB.

- **Isolation**
  Transactions running simultaneously are treated as to be run one-by-one.
  Operations within a transaction stays within it until its commited.
  If another transaction is performed on the same data, one would wait for another.

- **Durability**
  Successful transaction is persisted.

Database index -- additional data structure optimized for search on a particular attribute (column).
Uses B-Trees under the hood
