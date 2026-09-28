# Top 20 DBMS Interview Questions — Answers for Backend Developers

These are written in interview-speaking style: you can say the answer directly to the interviewer. Under each question, I’ve explained the important terminology and sub-concepts so you can handle follow-up questions too.

---

## 📑 Table of Contents

- [1. What is a DBMS, and what is the difference between DBMS and RDBMS?](#1-what-is-a-dbms-and-what-is-the-difference-between-dbms-and-rdbms)
- [2. What is the three-schema architecture of a DBMS?](#2-what-is-the-three-schema-architecture-of-a-dbms)
- [3. What are the different types of data models?](#3-what-are-the-different-types-of-data-models)
- [4. What is an ER model?](#4-what-is-an-er-model)
- [5. What are the different types of keys in DBMS?](#5-what-are-the-different-types-of-keys-in-dbms)
- [6. What are integrity constraints in DBMS?](#6-what-are-integrity-constraints-in-dbms)
- [7. What is normalization? Explain 1NF, 2NF, 3NF, and BCNF.](#7-what-is-normalization-explain-1nf-2nf-3nf-and-bcnf)
- [8. What is denormalization, and when is it useful?](#8-what-is-denormalization-and-when-is-it-useful)
- [9. What is a database transaction? Explain ACID properties.](#9-what-is-a-database-transaction-explain-acid-properties)
- [10. What is concurrency control? Explain locks and two-phase locking.](#10-what-is-concurrency-control-explain-locks-and-two-phase-locking)
- [11. What is a deadlock in DBMS?](#11-what-is-a-deadlock-in-dbms)
- [12. What are transaction isolation levels?](#12-what-are-transaction-isolation-levels)
- [13. What is a database index? Explain B-tree and hash indexes.](#13-what-is-a-database-index-explain-b-tree-and-hash-indexes)
- [14. How does a DBMS store data on disk?](#14-how-does-a-dbms-store-data-on-disk)
- [15. How does a DBMS process a query?](#15-how-does-a-dbms-process-a-query)
- [16. How does a DBMS recover from crashes?](#16-how-does-a-dbms-recover-from-crashes)
- [17. How does a DBMS provide security?](#17-how-does-a-dbms-provide-security)
- [18. What is a distributed database?](#18-what-is-a-distributed-database)
- [19. What is the CAP theorem?](#19-what-is-the-cap-theorem)
- [20. What is the difference between SQL and NoSQL databases?](#20-what-is-the-difference-between-sql-and-nosql-databases)
- [Final revision: what you should be able to explain confidently](#final-revision-what-you-should-be-able-to-explain-confidently)

---

# 1. What is a DBMS, and what is the difference between DBMS and RDBMS?

### Interview answer

A DBMS (Database Management System) is software used to store, organize, retrieve, update, and manage data efficiently. An RDBMS (Relational Database Management System) is a type of DBMS that stores data in tables consisting of rows and columns. RDBMSs use relationships, keys, and integrity constraints to maintain consistency between tables. Examples include MySQL, PostgreSQL, Oracle Database, and SQL Server.

### Important terminologies

**DBMS**

* A DBMS acts as an interface between applications and stored data.

* It manages data access, security, concurrency, and recovery.

* It may use different data models, such as relational, hierarchical, or document-based.

**RDBMS**

* An RDBMS organizes data into tables with defined relationships.

* Relationships are commonly represented using primary keys and foreign keys.

* Most relational systems support SQL and transactions, though specific features vary.

**Rows and columns**

* A row represents one record, such as one customer.

* A column represents an attribute, such as customer name or email.

* A table groups records that share a common structure.

**Examples**

* MySQL and PostgreSQL are relational database systems.

* MongoDB is a document-oriented database.

* The key difference is the data model, not simply whether a database uses SQL.

[⬆ Back to top](#-table-of-contents)

---

# 2. What is the three-schema architecture of a DBMS?

### Interview answer

The three-schema architecture separates a database into three levels: external, conceptual, and internal. The external level describes how individual users or applications view the data. The conceptual level describes the overall logical structure of the database, while the internal level describes how data is physically stored. This separation supports data abstraction and data independence.

### Important terminologies

**1. External level**

* This is the user or application view of the database.

* Different users can see different subsets of the same database.

* For example, an employee may see their own payroll details, while HR can access broader employee records.

**2. Conceptual level**

* This describes the complete logical structure of the database.

* It defines entities, attributes, relationships, and constraints.

* It generally hides physical storage details from users.

**3. Internal level**

* This describes how data is physically organized and accessed.

* It includes storage structures, indexes, file organization, and access paths.

* Its purpose is to support efficient storage and retrieval.

**Data abstraction**

* Data abstraction hides unnecessary implementation details.

* Users interact with data without needing to understand its physical storage.

* It makes database systems easier to use and maintain.

**Data independence**

* Data independence means changes at one schema level need not require changes at higher levels.

* Physical data independence: storage changes do not require changes to the logical schema.

* Logical data independence: logical schema changes can be made without requiring changes to every user view, although this can be harder to achieve.

[⬆ Back to top](#-table-of-contents)

---

# 3. What are the different types of data models?

### Interview answer

A data model defines how data is structured, related, and represented in a database. Common models include relational, hierarchical, network, and document models. The relational model organizes data into tables, hierarchical and network models represent relationships using tree-like or graph-like structures, and document databases store data as documents. The choice depends on the application's data structure and access patterns.

### Important terminologies

**1. Relational model**

* Data is organized into tables containing rows and columns.

* Relationships are represented using keys.

* It is suitable for structured data and applications requiring strong consistency and relational queries.

**2. Hierarchical model**

* Data is organized as a tree with parent-child relationships.

* A child typically has one parent, while a parent can have multiple children.

* It works well for naturally hierarchical data but is less flexible for many-to-many relationships.

**3. Network model**

* Data is organized as records connected through links.

* A record can have multiple parent and child relationships.

* It supports more complex relationships than the hierarchical model, but navigation can be complicated.

**4. Document model**

* Data is stored as documents, often in JSON-like formats.

* Documents can contain nested objects and arrays.

* It is useful when records have flexible or evolving structures; MongoDB is a common example.

**Structured vs. flexible schema**

* A structured schema defines the expected fields and data types.

* A flexible schema allows records to have different fields or structures.

* Flexible schemas still require validation and good data-design practices.

[⬆ Back to top](#-table-of-contents)

---

# 4. What is an ER model?

### Interview answer

An Entity-Relationship (ER) model is a conceptual way to design a database before implementing it. It represents entities, their attributes, and the relationships between them. Cardinality describes how many instances can participate in a relationship, while participation describes whether that relationship is mandatory or optional. ER diagrams help convert real-world requirements into a database design.

### Important terminologies

**Entity**

* An entity is a real-world object or concept about which we store data.

* Examples include Student, Employee, Product, and Order.

* An entity type describes a category; an entity instance is one specific member of it.

**Attribute**

* An attribute describes a property of an entity.

* For an Employee, attributes might include employee ID, name, and salary.

* Attributes can be simple, composite, multivalued, or derived.

**Relationship**

* A relationship describes an association between entities.

* For example, a Customer places an Order.

* Relationships can be one-to-one, one-to-many, or many-to-many.

**Cardinality**

* Cardinality specifies the number of entity instances that can be related.

* 1:1: one person has one passport, under the chosen business rules.

* 1:N: one department has many employees; M:N: students enroll in many courses.

**Participation**

* Participation specifies whether every entity must take part in a relationship.

* Total participation means participation is mandatory.

* Partial participation means participation is optional.

**ER diagram**

* An ER diagram visually represents entities, attributes, and relationships.

* It helps identify tables, keys, and relationship constraints before implementation.

* Many-to-many relationships are usually implemented using a separate junction table in a relational database.

[⬆ Back to top](#-table-of-contents)

---

# 5. What are the different types of keys in DBMS?

### Interview answer

Keys are attributes, or combinations of attributes, used to identify records and establish relationships between tables. A super key uniquely identifies a row, while a candidate key is a minimal super key. One candidate key is selected as the primary key, and the remaining candidate keys are alternate keys. A foreign key references a key in another or the same table to maintain referential integrity.

### Important terminologies

**Super key**

* A super key is any set of attributes that uniquely identifies a row.

* It may contain extra attributes that are not needed for uniqueness.

* For example, `{student_id, name}` can be a super key if `student_id` is unique.

**Candidate key**

* A candidate key is a minimal super key.

* Minimal means removing any attribute would make it stop being unique.

* A table can have multiple candidate keys.

**Primary key**

* A primary key is the candidate key selected as the main identifier.

* It must be unique and cannot contain `NULL` values.

* A table has one primary key constraint, which may consist of multiple columns.

**Alternate key**

* An alternate key is a candidate key that was not selected as the primary key.

* It still uniquely identifies records.

* For example, if both student ID and email are unique, one may be primary and the other alternate.

**Composite key**

* A composite key uses two or more attributes together.

* For example, `(student_id, course_id)` can identify a student's course enrollment.

* Neither attribute necessarily needs to be unique by itself.

**Foreign key**

* A foreign key references a candidate key—commonly a primary key—in another or the same table.

* It helps prevent references to nonexistent records.

* Depending on the database and constraint definition, referenced values must match an existing key value or be `NULL` when allowed.

**Natural key vs. surrogate key**

* A natural key comes from real-world data, such as a government-issued identifier or a carefully chosen unique code.

* A surrogate key is an artificial identifier, such as an auto-generated numeric ID or UUID.

* Surrogate keys can remain stable even when real-world attributes change.

[⬆ Back to top](#-table-of-contents)

---

# 6. What are integrity constraints in DBMS?

### Interview answer

Integrity constraints are rules that ensure the accuracy and consistency of database data. Entity integrity requires primary keys to be unique and non-null, while referential integrity ensures that foreign-key references are valid. Domain constraints restrict values to permitted types or ranges, and user-defined constraints enforce business-specific rules. These constraints prevent invalid data from entering the database.

### Important terminologies

**Entity integrity**

* Every row must be uniquely identifiable by its primary key.

* Primary-key values cannot be `NULL`.

* This prevents records from having missing or duplicate primary identifiers.

**Referential integrity**

* A foreign-key value must refer to an existing referenced key value, unless `NULL` is allowed.

* It prevents orphan records, such as an order referencing a nonexistent customer.

* Deletion or update behavior can be configured, for example, to restrict the operation or cascade changes.

**Domain constraint**

* A domain defines the valid values for an attribute.

* It can include data type, permitted range, format, or allowed values.

* For example, an age field may be restricted to non-negative integers.

**User-defined constraint**

* A business rule specific to an application or organization.

* For example, an employee's end date cannot be earlier than their start date.

* Such rules may be enforced using checks, unique constraints, foreign keys, or application logic.

**Constraint vs. validation**

* A database constraint is enforced by the database itself.

* Application validation checks input before it reaches the database.

* Both are useful, but database constraints protect data even when multiple applications write to the same database.

[⬆ Back to top](#-table-of-contents)

---

# 7. What is normalization? Explain 1NF, 2NF, 3NF, and BCNF.

### Interview answer

Normalization is the process of organizing relational data to reduce unnecessary duplication and prevent data anomalies. First Normal Form requires atomic values and no repeating groups; Second Normal Form removes partial dependencies on a composite key. Third Normal Form removes inappropriate transitive dependencies, and BCNF requires every non-trivial functional dependency to have a super key as its determinant. Normalization improves consistency and makes updates safer.

### Important terminologies

**Normalization**

* Normalization decomposes tables according to their dependencies.

* Its goal is to reduce redundancy and prevent insertion, update, and deletion anomalies.

* A good decomposition should ideally be lossless and preserve important dependencies.

**Functional dependency**

* A functional dependency `X → Y` means that a value of X determines exactly one value of Y.

* For example, `student_id → student_name` if each student ID identifies one student.

* Functional dependencies help determine candidate keys and normal forms.

**1NF — First Normal Form**

* Each field contains a single value from its domain, rather than a repeating group or list.

* Rows should be identifiable, and values should follow the column's intended domain.

* For example, storing multiple phone numbers in one field can violate a design's intended 1NF structure.

**2NF — Second Normal Form**

* The table must already be in 1NF.

* Every non-prime attribute must depend on the whole of every candidate key, not just part of a composite candidate key.

* It mainly addresses partial dependencies; it is automatically satisfied when all candidate keys contain only one attribute.

**3NF — Third Normal Form**

* The table must already be in 2NF.

* For every non-trivial functional dependency `X → A`, either X is a super key or A is a prime attribute.

* Informally, it removes problematic transitive dependencies of non-key attributes on keys.

**BCNF — Boyce-Codd Normal Form**

* For every non-trivial functional dependency `X → Y`, X must be a super key.

* BCNF is stricter than 3NF.

* A table can satisfy 3NF but violate BCNF when a determinant is not a super key.

**Data anomalies**

* Insertion anomaly: data cannot be inserted without adding unrelated data.

* Update anomaly: the same fact must be updated in multiple places.

* Deletion anomaly: deleting one record unintentionally removes another important fact.

**Lossless decomposition**

* Decomposing a table is lossless when joining the resulting tables recreates exactly the original information.

* It must not create spurious rows or lose information.

* Dependency preservation means important dependencies can still be enforced without joining the decomposed tables.

[⬆ Back to top](#-table-of-contents)

---

# 8. What is denormalization, and when is it useful?

### Interview answer

Denormalization is the intentional introduction of redundancy into a database to improve read performance or simplify queries. For example, a system may store a frequently used aggregate or copy a customer name into an order record to avoid repeated joins. It can reduce query cost, but it increases storage and creates consistency challenges. I would consider it after measuring a real performance problem.

### Important terminologies

**Redundancy**

* Redundancy means storing the same fact in multiple places.

* It can speed up reads when the duplicated data is frequently needed.

* However, every copy may need to be kept consistent.

**Read performance**

* Denormalization can reduce joins, repeated calculations, or expensive lookups.

* It is useful for read-heavy applications and reporting workloads.

* The benefit should be measured against the extra maintenance cost.

**Update anomaly**

* If duplicated data changes in one place but not another, records can disagree.

* For example, a customer's address might be updated in the customer table but remain old in copied order data.

* Applications may need transactions, controlled updates, or refresh processes to avoid inconsistencies.

**Materialized view**

* A materialized view stores the result of a query rather than calculating it from scratch each time.

* It can accelerate reporting and aggregate queries.

* Its data must be refreshed or maintained as the underlying data changes.

**When to denormalize**

* Consider it when profiling identifies a costly read pattern.

* Common examples include reporting tables, cached aggregates, and read-optimized data models.

* Keep the normalized source of truth clear wherever possible.

[⬆ Back to top](#-table-of-contents)

---

# 9. What is a database transaction? Explain ACID properties.

### Interview answer

A transaction is a logical unit of work that contains one or more database operations. ACID stands for Atomicity, Consistency, Isolation, and Durability. Atomicity means all operations succeed or none do; consistency preserves database rules, isolation controls interference between concurrent transactions, and durability ensures committed changes survive failures. ACID properties help make database operations reliable.

### Important terminologies

**Transaction**

* A transaction groups related operations into one logical unit.

* For example, transferring money requires debiting one account and crediting another.

* The transaction should not leave the system with only one of those changes applied.

**Atomicity**

* Atomicity means all-or-nothing execution.

* If a transaction fails before committing, its partial changes are rolled back.

* It prevents incomplete operations from being treated as successful.

**Consistency**

* Consistency means a successful transaction preserves defined database constraints and invariants.

* For example, it should not violate a foreign-key constraint.

* The database begins and ends the transaction in a valid state, assuming the transaction itself correctly implements the business rules.

**Isolation**

* Isolation controls how concurrent transactions interact.

* It prevents certain transactions from observing or causing intermediate or conflicting results.

* The actual guarantees depend on the database's isolation level and implementation.

**Durability**

* Once a transaction commits successfully, its changes should survive a crash.

* Databases commonly use transaction logs and persistent storage to provide this guarantee.

* Durability guarantees depend on the database's configuration and the failure model it promises to handle.

**COMMIT and ROLLBACK**

* `COMMIT` makes a transaction's changes permanent according to the database's guarantees.

* `ROLLBACK` cancels uncommitted changes.

* Savepoints can allow a transaction to roll back to an intermediate point, where supported.

[⬆ Back to top](#-table-of-contents)

---

# 10. What is concurrency control? Explain locks and two-phase locking.

### Interview answer

Concurrency control manages simultaneous transactions so they do not corrupt data or produce unacceptable results. A shared lock generally allows multiple transactions to read the same data, while an exclusive lock allows one transaction to modify it and prevents conflicting access. Two-phase locking has a growing phase, where locks are acquired, and a shrinking phase, where locks are released. It helps ensure conflict-serializable execution, although it can cause deadlocks.

### Important terminologies

**Concurrency**

* Concurrency means multiple transactions are active during overlapping periods.

* It improves throughput and resource utilization.

* Without proper control, concurrent operations can interfere with one another.

**Shared lock (S lock)**

* A shared lock is generally used for reading data.

* Multiple transactions can hold shared locks on the same item simultaneously.

* A shared lock normally conflicts with an exclusive lock on that item.

**Exclusive lock (X lock)**

* An exclusive lock is generally used when modifying data.

* It prevents other transactions from obtaining conflicting shared or exclusive locks.

* It helps ensure that concurrent transactions do not make incompatible changes to the same data.

**Two-phase locking (2PL)**

* In the growing phase, a transaction may acquire locks but cannot release them.

* In the shrinking phase, it may release locks but cannot acquire new ones.

* Basic 2PL guarantees conflict serializability, but it does not by itself guarantee freedom from deadlocks.

**Strict 2PL**

* Strict two-phase locking holds exclusive locks until the transaction commits or aborts.

* This helps prevent other transactions from reading or overwriting uncommitted writes.

* It simplifies recovery and prevents cascading rollbacks caused by dirty writes.

**Serializability**

* Serializability means a concurrent execution is equivalent, under a defined correctness criterion, to some serial order.

* A serial execution runs transactions one after another.

* Serializability allows concurrency while preserving a defined form of correctness.

**Lock granularity**

* Granularity describes the size of the locked resource: row, page, table, or database.

* Fine-grained locks allow more concurrency but require more lock-management overhead.

* Coarse-grained locks are simpler but may block more transactions.

[⬆ Back to top](#-table-of-contents)

---

# 11. What is a deadlock in DBMS?

### Interview answer

A deadlock occurs when two or more transactions wait indefinitely for resources held by one another. For example, transaction A holds a lock on row 1 and waits for row 2, while transaction B holds row 2 and waits for row 1. A DBMS can detect deadlocks and abort a transaction to break the cycle. Deadlocks can be reduced by consistent lock ordering, short transactions, and appropriate retry logic.

### Important terminologies

**Deadlock**

* A deadlock is a cycle of waiting that prevents the involved transactions from progressing.

* It commonly occurs when transactions acquire locks in different orders.

* The DBMS usually resolves it by choosing a transaction to abort.

**Wait-for graph**

* A wait-for graph represents transactions as nodes.

* An edge `T1 → T2` means T1 is waiting for a resource held by T2.

* In common lock-based systems, a cycle indicates a deadlock.

**Deadlock detection**

* The DBMS can periodically inspect a wait-for graph for cycles.

* If a deadlock is found, it selects a victim transaction.

* Detection has overhead, so databases may balance detection frequency against delay.

**Deadlock prevention**

* Prevention techniques make deadlocks impossible under a chosen policy.

* Examples include acquiring locks in a consistent order or using timestamp-based schemes.

* Prevention can reduce concurrency or cause additional waiting.

**Deadlock recovery**

* The DBMS aborts or rolls back one or more transactions to release their locks.

* The aborted transaction can often be retried.

* Applications should handle deadlock errors safely, ideally by retrying the whole transaction when appropriate.

**Starvation**

* Starvation occurs when a transaction is repeatedly delayed or selected as a victim.

* Unlike deadlock, it does not require a cycle of waiting.

* Fair scheduling and victim-selection policies can reduce starvation.

[⬆ Back to top](#-table-of-contents)

---

# 12. What are transaction isolation levels?

### Interview answer

Isolation levels define how much one transaction is allowed to observe the effects of other concurrent transactions. The standard levels are Read Uncommitted, Read Committed, Repeatable Read, and Serializable. They provide different trade-offs between concurrency and consistency, affecting anomalies such as dirty reads, non-repeatable reads, and phantom reads. Exact behavior can vary between database systems, particularly when they use MVCC.

### Important terminologies

**1. Read Uncommitted**

* This is the weakest standard isolation level.

* It may permit dirty reads, where a transaction reads another transaction's uncommitted changes.

* Some database systems implement it similarly to Read Committed.

**2. Read Committed**

* A transaction reads only committed data.

* It prevents dirty reads.

* Re-reading the same row may return a different committed value if another transaction updates it.

**3. Repeatable Read**

* It prevents dirty reads and, in the SQL standard, non-repeatable reads.

* The exact treatment of phantom reads depends on the database implementation.

* Some systems use snapshot-based behavior that differs from lock-based implementations.

**4. Serializable**

* This is the strongest standard isolation level.

* Concurrent transactions behave as if they executed in some serial order.

* It may reduce concurrency or abort transactions that need to be retried.

**Dirty read**

* A transaction reads data written by another transaction that has not committed.

* If the writer rolls back, the reader has observed a value that never became committed data.

* Read Committed and stronger standard isolation levels prevent this anomaly.

**Non-repeatable read**

* A transaction reads a row twice and gets different values because another transaction committed an update.

* The row was present both times, but its data changed.

* Repeatable Read prevents this anomaly under the standard definition.

**Phantom read**

* A transaction repeats a query using the same condition and gets a different set of rows.

* Another transaction may have inserted or deleted rows matching that condition.

* Serializable isolation prevents the anomaly as defined by the standard.

**Lost update**

* Two transactions read the same original value and then overwrite each other's changes.

* One transaction's update is effectively lost.

* Locking, atomic updates, or optimistic concurrency checks can prevent it.

**MVCC**

* Multi-Version Concurrency Control keeps multiple versions of data.

* Readers can often access a consistent snapshot without blocking writers.

* It can improve concurrency, but its exact guarantees depend on the isolation level and implementation.

[⬆ Back to top](#-table-of-contents)

---

# 13. What is a database index? Explain B-tree and hash indexes.

### Interview answer

An index is a data structure that helps the database locate rows without scanning the entire table. B-tree indexes maintain ordered keys and support equality, range searches, and sorting, while hash indexes use a hash function and are mainly useful for equality lookups. Indexes can improve reads but consume storage and add overhead to inserts, updates, and deletes. I choose indexes based on actual query patterns and execution plans.

### Important terminologies

**Index**

* An index stores search-key values and information that helps locate corresponding rows.

* It is similar to an index in a book: it helps find information without reading every page.

* Indexes may be built on one column or multiple columns.

**B-tree / B+ tree**

* These are balanced tree structures commonly used for database indexes.

* They keep keys ordered, making range scans and ordered retrieval efficient.

* Many database systems use B+ tree variants, where leaf pages are linked or otherwise support efficient ordered traversal.

**Hash index**

* A hash function maps a key to a bucket or location.

* Hash indexes are well suited to equality lookups.

* They generally do not support efficient ordered range scans.

**Clustered index**

* In systems that support this concept, a clustered index determines or closely corresponds to the physical organization of table rows.

* A table can generally have only one such physical ordering.

* The exact meaning and implementation vary by database.

**Non-clustered index**

* A non-clustered index is stored separately from the table's row organization.

* It contains indexed keys and a way to locate the corresponding rows.

* A table can have multiple non-clustered indexes.

**Composite index**

* A composite index contains multiple columns, such as `(department_id, salary)`.

* Column order matters for which query predicates and ordering operations can use it efficiently.

* An index on `(A, B)` commonly supports lookups beginning with A better than lookups on B alone.

**Covering index**

* A covering index contains all the columns needed for a particular query.

* The database may answer that query from the index without fetching the full table row.

* This can reduce I/O, at the cost of a larger index.

**Index trade-offs**

* Indexes speed up supported searches, joins, and sometimes sorting.

* They consume disk and memory and must be maintained during writes.

* Too many or poorly chosen indexes can slow write-heavy workloads.

[⬆ Back to top](#-table-of-contents)

---

# 14. How does a DBMS store data on disk?

### Interview answer

A DBMS typically stores table data and indexes in files that are divided into fixed-size pages or blocks. A page contains records or parts of records, along with metadata used to manage the stored data. Frequently accessed pages are cached in memory through a buffer pool to reduce disk I/O. When a required page is not in memory, the DBMS loads it from storage.

### Important terminologies

**Data file**

* A data file stores database pages on persistent storage.

* Pages may contain table rows, index entries, or other database structures.

* The DBMS manages how these files are allocated and accessed.

**Page**

* A page is a basic unit of data organization and often the unit of disk I/O.

* It has a fixed size within a given database configuration.

* A page may contain multiple rows or index entries.

**Block**

* A block is a storage unit used by the operating system or storage device.

* Database pages and storage blocks are related but are not necessarily the same size.

* The DBMS and operating system coordinate how data is transferred.

**Record**

* A record is the stored representation of a row or data item.

* It contains field values and may include metadata.

* Records can be fixed-length or variable-length, depending on the data and storage design.

**Buffer pool**

* The buffer pool is a region of memory used to cache database pages.

* If a requested page is already cached, the DBMS can avoid a storage read.

* The buffer manager chooses pages to evict when memory is needed.

**Dirty page**

* A dirty page is a cached page that has been modified but not yet written to its persistent data file.

* The DBMS tracks these modifications.

* Write-ahead logging helps ensure recovery remains possible before modified pages are written.

**Disk I/O**

* Disk I/O means reading data from or writing data to persistent storage.

* Random I/O can be more expensive than sequential access, depending on the storage device.

* Reducing unnecessary I/O is a major goal of database performance optimization.

[⬆ Back to top](#-table-of-contents)

---

# 15. How does a DBMS process a query?

### Interview answer

When a query arrives, the DBMS parses it to check its syntax and resolve referenced objects. It then uses a query optimizer to consider possible execution strategies and choose a plan based on estimated cost. The execution engine runs the selected plan, accessing tables and indexes as required. The plan may include scans, joins, sorts, and aggregations.

### Important terminologies

**Parsing**

* Parsing checks whether the query follows the database's syntax.

* The DBMS also resolves names such as tables and columns.

* It produces an internal representation that later stages can process.

**Query optimization**

* The optimizer considers alternative ways to execute the query.

* It may choose join order, access paths, and join algorithms.

* Its goal is to find an efficient plan based on available information and cost estimates.

**Execution plan**

* An execution plan describes the operations the database will perform.

* It may show table scans, index scans, joins, sorts, and aggregations.

* An actual execution plan may also include runtime statistics.

**Cost estimation**

* The optimizer estimates the resource cost of possible plans.

* Estimates can include I/O, CPU, memory, and row counts.

* Statistics about data distribution help the optimizer make better choices.

**Table scan**

* A table scan reads rows from the table, often examining a large portion or all of it.

* It can be efficient when many rows are needed.

* An index is not always faster than a table scan.

**Join algorithms**

* Nested-loop join: for each row from one input, searches for matching rows in the other.

* Hash join: builds a hash table from one input and probes it with the other.

* Merge join: processes inputs in key order, advancing through them to find matches.

**Statistics**

* Statistics describe characteristics such as row counts, value distributions, and distinct values.

* The optimizer uses them to estimate how many rows an operation will produce.

* Stale or inaccurate statistics can lead to poor execution plans.

**EXPLAIN**

* `EXPLAIN` shows the plan the database intends to use.

* Some databases provide an option to execute the query and show actual runtime details.

* Comparing estimated and actual row counts can help identify performance problems.

[⬆ Back to top](#-table-of-contents)

---

# 16. How does a DBMS recover from crashes?

### Interview answer

A DBMS uses recovery mechanisms to restore the database to a consistent state after a crash. It maintains transaction logs that record changes and uses checkpoints to reduce the amount of work required during recovery. Depending on which changes were committed, recovery may redo committed operations and undo incomplete transactions. Write-ahead logging ensures the relevant log records are persisted before corresponding data pages are written.

### Important terminologies

**Transaction log**

* A transaction log records information about database changes and transaction activity.

* It supports crash recovery and may also support replication or point-in-time recovery.

* The exact log format and contents depend on the database system.

**Checkpoint**

* A checkpoint records recovery-related information about the database's state.

* It helps the DBMS identify where recovery should begin or which work remains necessary.

* A checkpoint does not necessarily mean every dirty page has been written to disk.

**Undo**

* Undo reverses the effects of changes that should not remain, such as those from incomplete transactions.

* It may use information stored in logs to restore previous values.

* The details depend on the recovery algorithm.

**Redo**

* Redo reapplies logged changes that need to be reflected in the recovered database.

* It can restore changes that were committed but whose data pages had not yet reached persistent storage.

* Redo is designed to be repeatable in common recovery algorithms.

**Write-ahead logging (WAL)**

* WAL requires relevant log records to be persisted before the associated dirty data page is written.

* This ensures recovery information is available if a crash occurs.

* Commit records are also persisted according to the database's durability guarantees.

**Crash recovery**

* After a crash, the DBMS examines its logs and recovery metadata.

* It determines which transactions committed and which were incomplete.

* It then performs the required redo and undo operations.

**Backup vs. recovery**

* A backup is a saved copy of database data.

* Recovery uses backups, logs, and other mechanisms to restore data after failures.

* A backup alone may not provide recovery to the latest moment; transaction logs can support point-in-time recovery.

[⬆ Back to top](#-table-of-contents)

---

# 17. How does a DBMS provide security?

### Interview answer

A DBMS protects data through authentication, authorization, roles, privileges, and auditing. Authentication verifies who is connecting, while authorization determines what that identity is allowed to do. Roles group permissions so they can be managed consistently, and auditing records relevant database activity. Backend applications should also use least-privilege accounts and protect credentials.

### Important terminologies

**Authentication**

* Authentication verifies the identity of a user or service.

* It may use passwords, certificates, or other supported mechanisms.

* Strong authentication reduces the risk of unauthorized access.

**Authorization**

* Authorization determines which actions an authenticated identity can perform.

* Permissions may control reading, inserting, updating, deleting, or managing database objects.

* Authorization should follow the principle of least privilege.

**Role**

* A role is a named collection of permissions or privileges.

* Administrators can grant roles to users or other roles, depending on the DBMS.

* Roles simplify permission management across teams and applications.

**Privilege**

* A privilege is permission to perform a specific operation.

* Examples include reading a table, modifying records, or creating database objects.

* Privileges should be limited to what a user or application needs.

**Auditing**

* Auditing records selected activities, such as logins, permission changes, or data access.

* It can help with incident investigation and compliance.

* Audit logs need suitable access controls and retention policies.

**Least privilege**

* Each account receives only the permissions needed for its job.

* A backend service that only reads data should not automatically receive write or administrator privileges.

* This limits the damage caused by compromised credentials or application bugs.

**Encryption**

* Encryption at rest protects stored data, while encryption in transit protects data moving over a network.

* Key management is essential to both.

* Encryption complements, rather than replaces, authentication and authorization.

[⬆ Back to top](#-table-of-contents)

---

# 18. What is a distributed database?

### Interview answer

A distributed database stores or manages data across multiple machines or locations while providing a coordinated database service. Replication keeps copies of data on multiple nodes, while sharding distributes different subsets of data across nodes. Partitioning divides data into manageable pieces, and consistency describes how reads and writes are observed across the system. Distributed databases can improve scalability and availability but introduce coordination and failure-handling challenges.

### Important terminologies

**Distributed database**

* A distributed database uses multiple networked machines to store or manage data.

* It may appear as one logical database to applications.

* Network failures, node failures, and coordination become important design concerns.

**Replication**

* Replication maintains copies of data on multiple nodes.

* It can improve availability, read capacity, and disaster recovery.

* Replicas must be coordinated or reconciled to handle concurrent writes and failures.

**Sharding**

* Sharding distributes different subsets of data across different database nodes.

* For example, customers may be assigned to shards based on a customer ID.

* A good shard key distributes load and avoids excessive cross-shard operations.

**Partitioning**

* Partitioning divides a dataset into smaller logical or physical pieces.

* It may occur within one database server or across multiple servers.

* Sharding is commonly used to describe partitioning across separate database nodes.

**Horizontal vs. vertical partitioning**

* Horizontal partitioning divides rows into subsets.

* Vertical partitioning divides columns or groups of columns into separate structures.

* Sharding commonly uses horizontal partitioning.

**Consistency**

* Consistency describes the guarantees a system provides about the values returned by reads and the ordering of writes.

* Some systems provide strong consistency, while others permit temporary differences between replicas.

* The appropriate guarantee depends on application requirements.

**Replication lag**

* Replication lag is the delay between a change on one node and its availability on a replica.

* Reads from lagging replicas may return stale data.

* Applications must account for this when freshness matters.

**Shard key**

* A shard key determines where a record is stored.

* Its distribution affects load balancing and query efficiency.

* A poor shard key can create hot spots or require expensive cross-shard queries.

[⬆ Back to top](#-table-of-contents)

---

# 19. What is the CAP theorem?

### Interview answer

The CAP theorem describes a trade-off in a distributed data system when a network partition occurs. Consistency means operations behave according to a single-copy, up-to-date view; availability means every request to a non-failing node receives a response; and partition tolerance means the system continues operating despite communication failures between nodes. During a partition, a system cannot guarantee both consistency and availability in the CAP sense for every request. The design must define which requests can succeed and what guarantees they receive.

### Important terminologies

**Consistency (CAP)**

* In CAP, consistency is commonly understood as linearizability: operations appear to occur atomically in a single order that respects real-time ordering.

* This is different from the broader database term used to describe valid data and constraints in ACID.

* Strong consistency may require a node to wait for coordination before responding.

**Availability (CAP)**

* Availability means each request received by a non-failing node gets a response.

* The response need not necessarily contain the latest value under a weaker consistency model.

* Returning an error or waiting indefinitely does not satisfy this strict CAP availability definition.

**Partition tolerance**

* A network partition occurs when some nodes cannot communicate with others.

* Partition tolerance means the system continues to operate despite that communication failure.

* In a real distributed system, network partitions must generally be considered possible.

**CP system**

* During a partition, a CP-style design prioritizes consistency over responding to every request.

* Some operations may be rejected or delayed until safe coordination is possible.

* This avoids returning conflicting or stale results for operations requiring strong consistency.

**AP system**

* During a partition, an AP-style design prioritizes responding to requests.

* Some responses may be stale or conflicting until replicas reconcile.

* Applications may need conflict resolution or eventual convergence.

**CA system**

* A CA system provides consistency and availability when there is no network partition.

* A system that cannot tolerate partitions cannot guarantee both properties during a partition.

* Therefore, “CA” is not a general solution to network partitions in a distributed system.

**Eventual consistency**

* Eventual consistency means replicas are expected to converge if no new updates occur and communication eventually recovers.

* Reads may temporarily return different values from different replicas.

* It is useful when availability and scale matter more than immediate global agreement.

**Important interview clarification**

* CAP is specifically about behavior during a network partition, not a simple choice of any two properties under all circumstances.

* It does not mean a database permanently chooses only two of the three properties.

* Real systems may offer different guarantees for different operations or configurations.

[⬆ Back to top](#-table-of-contents)

---

# 20. What is the difference between SQL and NoSQL databases?

### Interview answer

SQL databases generally use the relational model, structured tables, and declarative SQL queries. NoSQL is a broad category of databases that use models such as document, key-value, graph, and wide-column storage. Relational databases are often a natural fit for structured data and relational transactions, while NoSQL databases can be useful for particular access patterns or flexible data structures. The choice depends on consistency, query requirements, scaling, data relationships, and operational needs.

### Important terminologies

**SQL database**

* SQL databases typically organize data into relations, represented as tables.

* They commonly support joins, constraints, and transactions.

* Examples include PostgreSQL, MySQL, Oracle Database, and SQL Server.

**NoSQL database**

* NoSQL refers to several non-relational data models rather than one specific technology.

* Many NoSQL systems support flexible schemas or distribution across nodes.

* Their query languages, consistency guarantees, and transaction capabilities vary significantly.

**Relational database**

* Data is represented through tables and relationships.

* Keys and constraints help enforce data integrity.

* It is often useful when relationships and multi-record transactions are central to the application.

**Document database**

* Stores records as documents, often using JSON-like structures.

* Documents can contain nested objects and arrays.

* Useful when application records have flexible or hierarchical structures.

**Key-value database**

* Stores values associated with unique keys.

* It is often optimized for direct lookups by key.

* Common use cases include caching, session storage, and simple high-throughput access patterns.

**Graph database**

* Represents data as nodes and relationships, often with properties on both.

* It is designed to query connections and paths between entities.

* It can be useful for social networks, recommendation relationships, and fraud-network analysis.

**Column-family / wide-column database**

* Organizes data into rows with potentially varying sets of columns grouped into column families.

* It is designed for particular large-scale distributed workloads.

* It is different from a traditional relational database that stores a fixed set of columns per table.

**Schema**

* A schema describes the structure and rules of stored data.

* Relational databases typically define table structures explicitly.

* Some NoSQL systems allow more flexible schemas, but applications still need consistent data conventions and validation.

**Horizontal scaling**

* Horizontal scaling adds more machines to distribute storage or processing.

* It can increase capacity but introduces coordination and operational complexity.

* Not every workload scales linearly by adding nodes.

**How to choose**

* Choose based on the data relationships, query patterns, transaction needs, consistency requirements, and scale.

* A relational database can also scale substantially, and many support JSON or distributed features.

* NoSQL is not automatically faster or more scalable; the data model and workload determine the fit.

[⬆ Back to top](#-table-of-contents)

---

# Final revision: what you should be able to explain confidently

Use this checklist to test whether you can answer the 20 questions without memorizing every sentence.

**Your DBMS revision checklist** (0 / 12)

- [ ] **DBMS fundamentals** — DBMS vs. RDBMS, schemas, data models
- [ ] **Database design** — ER model, cardinality, keys, integrity constraints
- [ ] **Normalization** — 1NF, 2NF, 3NF, BCNF, anomalies, denormalization
- [ ] **Transactions** — ACID, commit, rollback, consistency
- [ ] **Concurrency** — Shared/exclusive locks, 2PL, serializability, deadlocks
- [ ] **Isolation** — Four isolation levels, dirty reads, non-repeatable reads, phantoms
- [ ] **Performance** — Indexes, B-trees, hash indexes, composite indexes
- [ ] **Storage** — Pages, records, buffer pool, disk I/O
- [ ] **Query processing** — Parsing, optimizer, execution plans, joins, statistics
- [ ] **Recovery and security** — Logs, checkpoints, undo/redo, permissions, auditing
- [ ] **Distributed databases** — Replication, sharding, partitioning, consistency
- [ ] **CAP and database types** — CAP theorem, SQL vs. NoSQL, database models

*Reset*

Interview tip: For each question, start with the definition, explain how it works, give one example, and mention a trade-off where relevant. That structure helps you sound clear and confident while leaving room for the interviewer to ask follow-up questions.

[⬆ Back to top](#-table-of-contents)
