# PostgreSQL — Complete Interview Question Bank

> Section-wise, exhaustive question bank for PostgreSQL interviews — from junior to senior/architect/DBA level. Covers SQL fundamentals, internals, indexing, MVCC, WAL, VACUUM, replication, partitioning, performance tuning, security, extensions, and a rich **Situation-Based Scenario** section with real-world debugging and design challenges.

---

## Table of Contents

1. [Core Fundamentals & Architecture](#1-core-fundamentals--architecture)
2. [Data Types & Schema Design](#2-data-types--schema-design)
3. [SQL — Queries, Joins & Aggregations](#3-sql--queries-joins--aggregations)
4. [Advanced SQL — Window Functions, CTEs & Subqueries](#4-advanced-sql--window-functions-ctes--subqueries)
5. [Indexing — Types, Internals & Strategy](#5-indexing--types-internals--strategy)
6. [MVCC — Multi-Version Concurrency Control](#6-mvcc--multi-version-concurrency-control)
7. [Transactions, Locking & Isolation Levels](#7-transactions-locking--isolation-levels)
8. [VACUUM, Autovacuum & Bloat](#8-vacuum-autovacuum--bloat)
9. [Write-Ahead Log (WAL) & Crash Recovery](#9-write-ahead-log-wal--crash-recovery)
10. [Replication & High Availability](#10-replication--high-availability)
11. [Partitioning](#11-partitioning)
12. [Query Planning & EXPLAIN ANALYZE](#12-query-planning--explain-analyze)
13. [Performance Tuning & Configuration](#13-performance-tuning--configuration)
14. [Connection Pooling — PgBouncer & Pgpool](#14-connection-pooling--pgbouncer--pgpool)
15. [JSON & JSONB](#15-json--jsonb)
16. [Full-Text Search](#16-full-text-search)
17. [Stored Procedures, Functions & Triggers](#17-stored-procedures-functions--triggers)
18. [Security & Access Control](#18-security--access-control)
19. [Backup, Restore & Point-in-Time Recovery](#19-backup-restore--point-in-time-recovery)
20. [Extensions & Tooling](#20-extensions--tooling)
21. [Scaling — Sharding, Citus & Read Replicas](#21-scaling--sharding-citus--read-replicas)
22. [Monitoring & Observability](#22-monitoring--observability)
23. [PostgreSQL vs Other Databases](#23-postgresql-vs-other-databases)
24. [Situation-Based / Scenario Questions](#24-situation-based--scenario-questions)
25. [High-Frequency Quick Reference](#25-high-frequency-quick-reference)

---

## 1. Core Fundamentals & Architecture

### What & Why PostgreSQL

- What is PostgreSQL? How does it differ from MySQL and other RDBMS?
- What does ORDBMS (Object-Relational Database Management System) mean in PostgreSQL's context?
- What is the latest major version of PostgreSQL and what are its notable features?
- What are the key strengths of PostgreSQL over MySQL?
  - Full ACID compliance, MVCC, advanced indexing (GIN, GiST, BRIN), JSON/JSONB, extensibility, better standards compliance, window functions, CTEs, table inheritance, foreign data wrappers
- What is the PostgreSQL license? (PostgreSQL License — permissive, similar to BSD/MIT)
- What language is PostgreSQL written in? (C)
- What is the postmaster process? What does it do?
- What is a backend process in PostgreSQL? How does one get created?
- What are the key background processes in PostgreSQL?
  - `autovacuum launcher`, `WAL writer`, `background writer`, `checkpointer`, `stats collector`, `archiver`, `WAL sender/receiver`
- What is the shared buffer pool? What does it store?
- What is the `pg_data` directory? What are its key subdirectories?
  - `base/` (database files), `global/` (cluster-wide tables), `pg_wal/` (WAL files), `pg_xact/` (transaction status), `postgresql.conf`, `pg_hba.conf`
- What is `postgresql.conf`? What does it configure?
- What is `pg_hba.conf`? What does it control?
- What is `pg_ident.conf`?
- What is the difference between a database cluster and a database in PostgreSQL?
- What is `initdb`? What does it do?
- What is `pg_ctl`? What commands does it support?
- What is the difference between `pg_ctl stop -m fast` vs `-m smart` vs `-m immediate`?
- What is the `PGDATA` environment variable?
- What is `PGPORT` and `PGHOST`?
- What is a tablespace in PostgreSQL? Why would you create one?
- What are system catalogs in PostgreSQL? Give 5 examples.
  - `pg_class`, `pg_attribute`, `pg_index`, `pg_namespace`, `pg_constraint`, `pg_proc`, `pg_type`, `pg_stat_activity`, `pg_locks`
- What is `pg_class`? What does each row represent?
- What is `information_schema`? How does it differ from `pg_catalog`?
- What is an OID (Object Identifier) in PostgreSQL?
- What is `pg_stat_activity`? What columns are most important?
- What is the role of the `postgres` superuser?
- What is `psql`? What are commonly used meta-commands?
  - `\d`, `\dt`, `\di`, `\df`, `\dn`, `\l`, `\c`, `\x`, `\timing`, `\copy`, `\e`, `\!`
- What is `SHOW ALL`? What is `SHOW shared_buffers`?
- What is `SELECT version()`?

---

## 2. Data Types & Schema Design

### Primitive Types

- What are the numeric types in PostgreSQL? (`smallint`, `integer`, `bigint`, `numeric`, `real`, `double precision`, `serial`, `bigserial`)
- What is `SERIAL`? What does it create under the hood? (sequence + default)
- What is `IDENTITY` column (PostgreSQL 10+)? How is it different from `SERIAL`?
- What is `NUMERIC(precision, scale)`? When do you use it over `FLOAT`?
- What are the character types? (`char(n)`, `varchar(n)`, `text`)
- What is the difference between `char(n)`, `varchar(n)`, and `text`? Which is preferred?
- What are the date/time types? (`date`, `time`, `timestamp`, `timestamptz`, `interval`)
- What is the difference between `timestamp` and `timestamptz`?
- What is `NOW()` vs `CURRENT_TIMESTAMP` vs `LOCALTIMESTAMP`?
- What are Boolean values in PostgreSQL?
- What is `UUID` type? How do you generate UUIDs?
- What is the `bytea` type? When do you use it?
- What is `money` type? Should you use it? (Avoid — use `numeric` instead)
- What is the `inet`, `cidr`, `macaddr` type?

### Special Types

- What is an `ARRAY` type in PostgreSQL? How do you declare and query it?
- What is `hstore`? When would you use it vs JSONB?
- What is the `enum` type? How do you create and use it?
- What is the `composite` type (row type)?
- What is the `range` type? (`int4range`, `tsrange`, `daterange`, etc.)
- What is the `tsvector` and `tsquery` type? (full-text search)
- What is the `point`, `line`, `polygon`, `circle` geometric type?

### Schema Design

- What are the normal forms? (1NF, 2NF, 3NF, BCNF, 4NF, 5NF)
- What is denormalization? When is it appropriate in PostgreSQL?
- What is a primary key? What is a surrogate key vs natural key?
- What is `UUID` vs `BIGSERIAL` as primary key? Trade-offs for distributed systems?
- What is a foreign key? What are the constraint actions? (`ON DELETE CASCADE`, `ON DELETE SET NULL`, `ON DELETE RESTRICT`, `ON DELETE NO ACTION`)
- What is a unique constraint vs a unique index in PostgreSQL?
- What is `NOT NULL` constraint? What is a `CHECK` constraint?
- What is a partial unique constraint? (unique index with `WHERE` clause)
- What is `DEFERRABLE` and `INITIALLY DEFERRED` on constraints?
- What is table inheritance in PostgreSQL? When is it used?
- What is the difference between a schema and a database in PostgreSQL?
- What is `search_path`? What is the default? (`$user, public`)
- What is `CREATE SCHEMA`, `ALTER SCHEMA`, `DROP SCHEMA CASCADE`?
- What is `COMMENT ON` statement?
- What is `CREATE TABLE LIKE`? What is `CREATE TABLE AS SELECT`?
- What is a temporary table? How does it differ from a regular table? What are its limitations with connection pooling?
- What is an unlogged table? When would you use it? What is the trade-off?
- What is `TOAST` (The Oversized-Attribute Storage Technique)? How does it work?
  - Values > 2KB are compressed/stored out-of-line in a TOAST table
- What is `FILLFACTOR`? What is its default? When would you lower it?

---

## 3. SQL — Queries, Joins & Aggregations

### Basic Queries

- What is the difference between `WHERE` and `HAVING`?
- What is the execution order of a SQL query? (FROM → WHERE → GROUP BY → HAVING → SELECT → DISTINCT → ORDER BY → LIMIT)
- What is the difference between `DELETE`, `TRUNCATE`, and `DROP`?
- What is `TRUNCATE` vs `DELETE`? Which is faster and why?
- What is `RETURNING` clause in PostgreSQL? Give a use case.
- What is `INSERT ... ON CONFLICT DO NOTHING`? What is `ON CONFLICT DO UPDATE` (UPSERT)?
- What is `ON CONFLICT (column) DO UPDATE SET col = EXCLUDED.col`?
- What is `COPY` command? When would you use it over `INSERT`?
- What is the difference between `\COPY` (client-side) and `COPY` (server-side)?
- What is `VALUES` clause? Can you `SELECT` from a `VALUES` list?
- What is `LIMIT` and `OFFSET`? What are the problems with large `OFFSET`?
- What is cursor-based pagination? How is it better than `OFFSET`?

### Joins

- What are the types of SQL joins?
  - `INNER JOIN`, `LEFT JOIN`, `RIGHT JOIN`, `FULL OUTER JOIN`, `CROSS JOIN`, `SELF JOIN`, `LATERAL JOIN`
- What is the difference between `LEFT JOIN` and `LEFT OUTER JOIN`?
- What is a `CROSS JOIN`? When would you use it?
- What is a `LATERAL JOIN`? How is it different from a regular join? When is it needed?
- What is a self-join? Give a real-world example. (employee-manager hierarchy)
- What is the difference between a join and a subquery? When is each preferred?
- What is a `NATURAL JOIN`? Why should you avoid it?
- What is `USING (column)` vs `ON table1.col = table2.col`?
- What is `EXCEPT`? What is `INTERSECT`? What is `UNION` vs `UNION ALL`?

### Aggregations & Grouping

- What are aggregate functions? (`COUNT`, `SUM`, `AVG`, `MIN`, `MAX`, `ARRAY_AGG`, `STRING_AGG`, `JSON_AGG`, `BOOL_AND`, `BOOL_OR`)
- What is `GROUP BY`? What is `GROUPING SETS`?
- What is `ROLLUP`? What is `CUBE`? How do they extend `GROUP BY`?
- What is `FILTER (WHERE ...)` clause on aggregate functions?
- What is the difference between `COUNT(*)`, `COUNT(col)`, and `COUNT(DISTINCT col)`?
- What is `DISTINCT ON (col)` in PostgreSQL? How is it different from standard `DISTINCT`?

---

## 4. Advanced SQL — Window Functions, CTEs & Subqueries

### Window Functions

- What is a window function? How does it differ from an aggregate function?
- What is `OVER()` clause?
- What is `PARTITION BY` in a window function?
- What is `ORDER BY` inside `OVER()`?
- What is the `ROWS BETWEEN` / `RANGE BETWEEN` frame specification?
- What is `ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW`?
- What are ranking window functions? (`ROW_NUMBER()`, `RANK()`, `DENSE_RANK()`, `NTILE()`)
- What is the difference between `ROW_NUMBER()`, `RANK()`, and `DENSE_RANK()`?
- What are value window functions? (`LAG()`, `LEAD()`, `FIRST_VALUE()`, `LAST_VALUE()`, `NTH_VALUE()`)
- What is `LAG()` and `LEAD()`? Give a use case. (compare current row with previous/next)
- What are aggregate window functions? (`SUM() OVER()`, `AVG() OVER()`, `COUNT() OVER()`)
- What is a running total using window functions?
- What is `PERCENT_RANK()` and `CUME_DIST()`?
- Can you use a window function in a `WHERE` clause? (No — use a subquery or CTE)

### CTEs (Common Table Expressions)

- What is a CTE? What is the `WITH` clause?
- What is the difference between a CTE and a subquery?
- What is a recursive CTE? When do you use it?
- Write a recursive CTE to traverse an employee-manager hierarchy.
- What is the `RECURSIVE` keyword in a CTE?
- What is the base case and recursive case in a recursive CTE?
- What is `UNION ALL` vs `UNION` inside a recursive CTE?
- What is a materialized CTE vs inline CTE in PostgreSQL 12+?
  - PostgreSQL 12+ inlines CTEs by default (not a fence); use `WITH foo AS MATERIALIZED (...)` to force materialization
- When would you force a CTE to be materialized?
- What is the `CYCLE` detection clause in recursive CTEs (PostgreSQL 14+)?
- What is the `SEARCH` clause in recursive CTEs (PostgreSQL 14+)?

### Subqueries

- What is a correlated subquery? What is an uncorrelated subquery?
- What is `EXISTS` vs `IN`? When is each faster?
- What is `ANY` vs `ALL` in subqueries?
- What is a scalar subquery?
- What is a `LATERAL` subquery? When do you need `LATERAL`?
- What is the difference between `NOT IN` and `NOT EXISTS` when NULLs are involved?

---

## 5. Indexing — Types, Internals & Strategy

### Index Types

- What are the index types available in PostgreSQL?
  - `B-tree`, `Hash`, `GIN`, `GiST`, `SP-GiST`, `BRIN`, `Bloom`
- What is a **B-tree index**? What operations does it support? When is it the default?
  - Equality (`=`), range (`<`, `>`, `BETWEEN`), sorting. Default and most versatile.
- What is a **Hash index**? What operation does it support? When is it useful?
  - Only equality (`=`). Faster than B-tree for pure equality. WAL-logged since PG 10.
- What is a **GIN (Generalized Inverted Index)**? What data types is it suited for?
  - Arrays, JSONB, full-text search (`tsvector`), `hstore`. "What documents contain this key?"
- What is a **GiST (Generalized Search Tree)**? What is it used for?
  - Geometric types, range types, full-text search, PostGIS. "Does this geometry overlap?"
- What is the difference between GIN and GiST for full-text search?
  - GIN: faster lookups, slower builds, larger; GiST: lossy (rechecks needed), faster builds, smaller
- What is a **BRIN (Block Range INdex)**? When is it extremely effective?
  - For naturally ordered, very large tables (time-series, log tables). Tiny size, cheap to maintain, fast for range scans on ordered data.
- What is a **SP-GiST** index? What is it used for? (space-partitioned GiST — phone numbers, IP routing tables, quadtrees)
- What is a **Bloom filter index**? When is it useful? (multi-column equality queries where individual column selectivity is low)

### Index Variants & Features

- What is a **partial index**? What is the `WHERE` clause on an index?
  - Index only covers rows matching a condition. Smaller, faster, used for sparse data or specific queries.
- What is a **covering index** (index-only scan)? What is `INCLUDE`?
  - `CREATE INDEX ON t(col1) INCLUDE (col2, col3)` — includes extra columns without indexing them, enables index-only scan
- What is an **expression index** (functional index)? Give an example.
  - `CREATE INDEX ON users (LOWER(email))` — index on computed expression
- What is a **unique index**? How is it different from a unique constraint?
- What is a **composite index**? What is the importance of column order?
- What is the **leading column** rule for composite indexes?
- What is a multi-column index vs multiple single-column indexes?
- What is an **index scan** vs **bitmap index scan** vs **index-only scan**?
- When does PostgreSQL choose a sequential scan over an index scan?
- What is a **concurrent index build**? (`CREATE INDEX CONCURRENTLY`)
- What is the trade-off of `CONCURRENTLY`? (slower, can't run inside transaction, may fail and leave invalid index)
- What is an **invalid index**? How do you detect and fix it?
- What is `REINDEX`? What is `REINDEX CONCURRENTLY` (PG 12+)?
- What is `pg_stat_user_indexes`? What is the `idx_scan` column?
- How do you find unused indexes? What queries help?
- How do you find missing indexes? (look at `pg_stat_user_tables` for `seq_scan` count on large tables)
- What is index bloat? How does it occur? How do you fix it?
- What is `FILLFACTOR` on an index? What is the default? (90%)
- What is the overhead of having too many indexes?

---

## 6. MVCC — Multi-Version Concurrency Control

- What is MVCC? What problem does it solve?
- How does MVCC allow readers to not block writers and vice versa?
- What is a tuple in PostgreSQL? What is `xmin` and `xmax` on a tuple?
  - `xmin`: transaction ID that inserted the row; `xmax`: transaction ID that deleted/updated it (0 = not deleted)
- What is a transaction snapshot in PostgreSQL?
- What is `txid_current()`?
- What is a transaction ID (XID)? How many bits is it? (32-bit — ~4 billion)
- What is transaction ID wraparound? Why is it catastrophic?
  - After ~2 billion transactions, old XIDs appear "in the future" — data becomes invisible
- What is `VACUUM FREEZE`? What is `relfrozenxid`?
- What is `autovacuum_freeze_max_age`? What happens when a table's XID age exceeds it?
- What is the `age()` function on a transaction ID?
- What is `pg_database.datfrozenxid`? Why is it important to monitor?
- What is a dead tuple? When is it created?
- Why doesn't PostgreSQL immediately delete rows on `UPDATE` or `DELETE`?
- What is the visibility rule for a tuple? When is a tuple visible to a transaction?
- What is HOT update (Heap Only Tuple)? What optimization does it provide?
  - If updated row stays on same page and no indexed columns changed, update is in-place — no index update needed
- What is the difference between MVCC in PostgreSQL vs MySQL InnoDB?
- What is `pg_visibility` extension?

---

## 7. Transactions, Locking & Isolation Levels

### Transactions

- What is a transaction in PostgreSQL? What are ACID properties?
- What is `BEGIN`, `COMMIT`, `ROLLBACK`?
- What is `SAVEPOINT`? What is `ROLLBACK TO SAVEPOINT`? What is `RELEASE SAVEPOINT`?
- What is autocommit in PostgreSQL? Is it on by default?
- What is `SET LOCAL` vs `SET` inside a transaction?
- What is `idle in transaction` state? Why is it dangerous?
- What is `idle_in_transaction_session_timeout`? Why should you set it?
- What is `statement_timeout`? What is `lock_timeout`?
- What is `deadlock_timeout`?

### Isolation Levels

- What are the 4 transaction isolation levels in SQL?
  - `READ UNCOMMITTED`, `READ COMMITTED`, `REPEATABLE READ`, `SERIALIZABLE`
- Does PostgreSQL support `READ UNCOMMITTED`? (Treated as `READ COMMITTED` — no dirty reads)
- What is **READ COMMITTED** (default in PostgreSQL)? What anomalies can it have?
  - Non-repeatable reads, phantom reads
- What is **REPEATABLE READ** in PostgreSQL? What anomalies does it prevent?
  - Prevents dirty reads and non-repeatable reads. In PostgreSQL, also prevents phantom reads (snapshot taken at transaction start)
- What is **SERIALIZABLE** isolation in PostgreSQL?
  - Uses SSI (Serializable Snapshot Isolation). Prevents all anomalies. May abort transactions with serialization failure.
- What is SSI (Serializable Snapshot Isolation)? How is it different from traditional locking-based SERIALIZABLE?
- What is a dirty read? Non-repeatable read? Phantom read? Write skew? Lost update?
- What is a serialization failure? What error code does it return? (`40001` — `serialization_failure`)
- How should applications handle serialization failures? (retry the transaction)
- What is `SET TRANSACTION ISOLATION LEVEL SERIALIZABLE`?
- What is `SET default_transaction_isolation`?

### Locking

- What are the lock modes in PostgreSQL?
  - `ACCESS SHARE`, `ROW SHARE`, `ROW EXCLUSIVE`, `SHARE UPDATE EXCLUSIVE`, `SHARE`, `SHARE ROW EXCLUSIVE`, `EXCLUSIVE`, `ACCESS EXCLUSIVE`
- What operations acquire `ACCESS EXCLUSIVE` lock? (DDL like `ALTER TABLE`, `DROP`, `TRUNCATE`, `VACUUM FULL`, `LOCK TABLE`)
- What lock does `SELECT` acquire? (`ACCESS SHARE`)
- What lock does `INSERT/UPDATE/DELETE` acquire? (`ROW EXCLUSIVE`)
- What lock does `SELECT FOR UPDATE` acquire? (`ROW SHARE` table + row-level exclusive)
- What is `SELECT FOR UPDATE`? What is `SELECT FOR SHARE`?
- What is `SELECT FOR UPDATE SKIP LOCKED`? When is it used? (queue processing)
- What is `SELECT FOR UPDATE NOWAIT`?
- What is `LOCK TABLE`?
- What is a deadlock? How does PostgreSQL detect and handle it?
  - PostgreSQL detects deadlocks after `deadlock_timeout` (default 1s) and aborts one transaction
- What is `pg_locks`? What does it show?
- What is `pg_blocking_pids(pid)` function?
- What is advisory lock? (`pg_advisory_lock`, `pg_advisory_xact_lock`, `pg_try_advisory_lock`)
- What is the difference between session-level and transaction-level advisory locks?
- What is `pg_stat_activity.wait_event_type` and `wait_event`?
- What are the most common wait events? (`Lock`, `LWLock`, `IO`, `Client`)
- How do you find blocking queries in PostgreSQL?
- What is a lock queue? What is lock priority starvation?
- What is `lock_timeout`? How does it help avoid lock waits?

---

## 8. VACUUM, Autovacuum & Bloat

### VACUUM

- What is `VACUUM`? What does it do?
  - Reclaims space from dead tuples, updates visibility map, prevents XID wraparound
- What is `VACUUM FULL`? How is it different from regular `VACUUM`?
  - Full: rewrites entire table, acquires `ACCESS EXCLUSIVE` lock, reclaims space to OS. Regular: marks space for reuse, no lock on reads/writes.
- When should you use `VACUUM FULL`? What are its risks?
- What is `VACUUM ANALYZE`? What does `ANALYZE` do?
  - Updates table statistics used by the query planner
- What is `VACUUM FREEZE`? What does it do?
- What is `VACUUM VERBOSE`? What information does it output?
- What is `pg_stat_user_tables.n_dead_tup`? What does it tell you?
- What is the visibility map? What does `VACUUM` do to it?
- What is the free space map (FSM)?

### Autovacuum

- What is autovacuum? Why is it critical to leave it enabled?
- What are the key autovacuum configuration parameters?
  - `autovacuum_vacuum_threshold` (default 50), `autovacuum_vacuum_scale_factor` (default 0.2), `autovacuum_analyze_threshold` (50), `autovacuum_analyze_scale_factor` (0.1), `autovacuum_vacuum_cost_delay`, `autovacuum_max_workers` (3), `autovacuum_naptime` (1min)
- What is the formula for when autovacuum triggers?
  - `n_dead_tup > threshold + scale_factor * n_live_tup`
- What is the problem with default autovacuum settings on large tables?
  - Scale factor of 0.2 means on a 1B-row table, 200M dead tuples needed before vacuum triggers
- How do you tune autovacuum per table? (`ALTER TABLE t SET (autovacuum_vacuum_scale_factor = 0.01)`)
- What is `autovacuum_vacuum_cost_delay`? What is autovacuum cost-based throttling?
- What is `vacuum_cost_limit` and `vacuum_cost_delay`?
- What is `autovacuum_freeze_max_age`? (default 200 million — table is force-vacuumed before XID age reaches this)
- What is autovacuum starvation? What causes it?
- What happens when autovacuum is blocked by a long-running transaction?
- What is `pg_stat_user_tables.last_autovacuum` and `last_autoanalyze`?
- What is `pg_stat_progress_vacuum`?
- What is `log_autovacuum_min_duration`?
- What is wraparound-prevention autovacuum? Why can't it be canceled? (Unlike normal autovacuum)

### Table & Index Bloat

- What is table bloat? What is index bloat?
- What causes bloat? (MVCC dead tuples not reclaimed quickly enough)
- What is the `bloat` query? (join on `pg_class`, `pg_statistic` etc.)
- What is `pgstattuple` extension? What does it reveal?
- What is `pg_repack`? How does it differ from `VACUUM FULL`?
  - `pg_repack` rewrites table online without `ACCESS EXCLUSIVE` lock (uses triggers)
- What is `pg_squeeze`? How does it compare to `pg_repack`?
- What is index bloat? How do you detect it?
- How do you rebuild an index without locking? (`REINDEX CONCURRENTLY`)
- What is `CLUSTER`? What does it do? What lock does it acquire?

---

## 9. Write-Ahead Log (WAL) & Crash Recovery

### WAL Fundamentals

- What is WAL (Write-Ahead Log)? What is its purpose?
- What is the WAL record? What information does it contain?
- How does WAL ensure durability?
- What is the WAL directory? (`pg_wal/` — formerly `pg_xlog/`)
- What is a WAL segment? What is its default size? (16 MB — configurable at `initdb`)
- What is LSN (Log Sequence Number)? What does it represent?
- What is `pg_current_wal_lsn()`? What is `pg_walfile_name(lsn)`?
- What is `wal_level`? What are the values?
  - `minimal` (no replication), `replica` (physical replication), `logical` (logical replication)
- What is `synchronous_commit`? What are the values and their durability guarantees?
  - `off`, `local`, `remote_write`, `remote_apply`, `on` (default)
- What is the performance vs durability trade-off of `synchronous_commit = off`?
- What is `fsync`? What happens if you set `fsync = off`? (Data loss risk on crash — never in production)
- What is `wal_sync_method`?
- What is `commit_delay` and `commit_siblings`?

### Checkpoints

- What is a checkpoint in PostgreSQL?
- What happens during a checkpoint?
- What is `checkpoint_completion_target`? What is the default? (0.9)
- What is `max_wal_size` and `min_wal_size`?
- What is `checkpoint_timeout`? (default 5 minutes)
- What causes a checkpoint more frequently than `checkpoint_timeout`? (`max_wal_size` exceeded)
- What is checkpoint spread? Why is it important?
- What is the `bgwriter`? How does it differ from the checkpointer?
- What is `bgwriter_delay`, `bgwriter_lru_maxpages`, `bgwriter_lru_multiplier`?
- What is `shared_buffers`? Why is dirty buffer writing split between bgwriter and checkpointer?

### Crash Recovery

- What happens on PostgreSQL restart after a crash?
- What is the recovery process? (reads WAL, replays records to bring DB to consistent state)
- What is `pg_wal_replay_pause()` and `pg_wal_replay_resume()`?
- What is `recovery.conf` (old) vs `standby.signal` and `recovery.conf` params in `postgresql.conf` (PG 12+)?
- What is `restore_command`?
- What is WAL archiving? What is `archive_command`?

---

## 10. Replication & High Availability

### Physical (Streaming) Replication

- What is streaming replication in PostgreSQL?
- What is the difference between physical replication and logical replication?
- What is a primary server? What is a standby (replica) server?
- How does WAL streaming replication work?
  - Primary sends WAL records to standby via WAL sender/receiver processes
- What is `primary_conninfo`? What is `standby.signal`?
- What is `wal_level = replica` requirement for streaming replication?
- What is `max_wal_senders`? What is `max_replication_slots`?
- What is synchronous vs asynchronous replication?
- What is `synchronous_standby_names`?
- What is replication lag? How do you measure it?
  - `pg_stat_replication.write_lag`, `flush_lag`, `replay_lag`, `sent_lsn - replay_lsn`
- What is `hot_standby`? What is a hot standby? (readable replica)
- What is `hot_standby_feedback`? What is the risk of enabling it?
  - Prevents vacuum from removing rows needed by standby queries — can cause primary bloat
- What is a replication slot? What are its types? (physical, logical)
- What is the danger of an unused replication slot? (WAL accumulates indefinitely)
- What is `pg_replication_slots`?
- What is WAL shipping vs streaming replication?
- What is `pg_basebackup`? What does it do?
- What is failover in PostgreSQL? What is `pg_ctl promote`?
- What is `pg_promote()` function (PG 12+)?
- What is `recovery_target_timeline`?

### Logical Replication

- What is logical replication? How does it differ from physical?
  - Replicates changes at the row/table level (decoded from WAL), not block-level. Allows selective replication, cross-version, cross-platform.
- What is a publication? What is a subscription?
- What is `CREATE PUBLICATION`? What is `CREATE SUBSCRIPTION`?
- What is `wal_level = logical` requirement?
- What operations are replicated? (`INSERT`, `UPDATE`, `DELETE`) — DDL is NOT replicated
- What are the limitations of logical replication?
  - No DDL replication, no sequence sync, large objects not replicated, must have replica identity
- What is `REPLICA IDENTITY`? What are the options? (`DEFAULT`, `FULL`, `NOTHING`, `USING INDEX`)
- What is the use case for logical replication vs physical?
  - Zero-downtime major version upgrades, selective table sync, multi-master (BDR/pglogical), CDC
- What is pglogical? What is BDR (Bi-Directional Replication)?

### High Availability Tools

- What is Patroni? What problem does it solve?
  - Automated failover and HA for PostgreSQL using DCS (etcd, Consul, ZooKeeper)
- What is `pg_auto_failover`?
- What is repmgr?
- What is Pgpool-II? (connection pooling + HA + load balancing)
- What is `Barman` (Backup and Recovery Manager)?
- What is Stolon?
- What is the difference between VIP failover and DNS-based failover?

---

## 11. Partitioning

### Partitioning Fundamentals

- What is table partitioning in PostgreSQL? What problem does it solve?
- What are the 3 partitioning strategies in PostgreSQL?
  - **Range partitioning**: based on a range of values (dates, IDs)
  - **List partitioning**: based on explicit list of values (country, status)
  - **Hash partitioning**: based on hash of column modulo number of partitions
- What is declarative partitioning (introduced in PG 10)? How does it differ from table inheritance-based partitioning?
- What is a partition key?
- What is a default partition?
- What is partition pruning? When does it happen?
  - Planner eliminates irrelevant partitions at query time (planning-time pruning) and execution time (runtime pruning, PG 11+)
- What is `enable_partition_pruning`?
- What is partition-wise join? What is `enable_partitionwise_join`? (PG 11+)
- What is partition-wise aggregate? (PG 11+)
- Can you have a unique constraint on a partitioned table? What restriction applies?
  - Must include the partition key column(s)
- Can you have a foreign key that references a partitioned table? (PG 12+: yes)
- What is sub-partitioning?
- What are the limitations of partitioned tables?
  - No global unique indexes (unless includes partition key), no primary key without partition key, some join types less efficient

### Creating & Managing Partitions

- How do you create a range-partitioned table?
  ```sql
  CREATE TABLE orders (id bigserial, created_at timestamptz, ...)
    PARTITION BY RANGE (created_at);
  CREATE TABLE orders_2024 PARTITION OF orders
    FOR VALUES FROM ('2024-01-01') TO ('2025-01-01');
  ```
- How do you attach an existing table as a partition? (`ATTACH PARTITION`)
- How do you detach a partition? (`DETACH PARTITION`) — What is `DETACH CONCURRENTLY` (PG 14+)?
- What happens to inserts when no partition matches and there's no default partition? (error)
- How do you automate partition creation? (pg_partman extension)
- What is `pg_partman`? How does it simplify partition management?
- What is the performance consideration when having thousands of partitions?
- What is the difference between `TRUNCATE` on a parent vs child partition table?

---

## 12. Query Planning & EXPLAIN ANALYZE

### Query Planner

- What is the PostgreSQL query planner (optimizer)?
- What is a query plan? What is a plan tree?
- What is `EXPLAIN`? What is `EXPLAIN ANALYZE`? What is the difference?
  - `EXPLAIN`: shows estimated plan without executing; `EXPLAIN ANALYZE`: executes and shows actual rows/time
- What is `EXPLAIN (ANALYZE, BUFFERS, VERBOSE, FORMAT JSON)`?
- What is `EXPLAIN (ANALYZE, COSTS, TIMING, BUFFERS)`?
- What is `auto_explain` extension?
- What are the key node types in an EXPLAIN output?
  - `Seq Scan`, `Index Scan`, `Index Only Scan`, `Bitmap Index Scan`, `Bitmap Heap Scan`, `Nested Loop`, `Hash Join`, `Merge Join`, `Sort`, `Hash`, `Aggregate`, `Gather`, `Gather Merge`
- What is a `Seq Scan`? When does the planner choose it over an index scan?
- What is an `Index Scan` vs `Index Only Scan`? What enables index-only scan?
- What is a `Bitmap Index Scan` + `Bitmap Heap Scan`? When is it used?
  - When multiple rows from an index need to be fetched — builds a bitmap of pages then fetches them in order
- What is a `Nested Loop Join`? When is it efficient?
- What is a `Hash Join`? When is it used?
- What is a `Merge Join`? What does it require?
- What is `cost` in EXPLAIN output? What is `startup cost` vs `total cost`?
- What is `rows` estimate? What does a large discrepancy with actual rows indicate?
- What is `width` in EXPLAIN output?
- What is `loops` in EXPLAIN ANALYZE?
- What are `shared hit` and `shared read` in BUFFERS output?
  - `shared hit`: pages found in buffer cache; `shared read`: pages read from disk
- What is `workers` in EXPLAIN output? What is a parallel query plan?

### Statistics & Planner Configuration

- What are planner statistics? Where are they stored? (`pg_statistic`, viewed via `pg_stats`)
- What is `ANALYZE`? When does it run?
- What is `default_statistics_target`? What is the default? (100)
- How do you increase statistics for a specific column? (`ALTER TABLE t ALTER COLUMN c SET STATISTICS 500`)
- What is `n_distinct` in `pg_stats`?
- What is `correlation` in `pg_stats`? Why does it matter for index scan efficiency?
- What is `most_common_vals` and `most_common_freqs`?
- What is `histogram_bounds`?
- What is `pg_stat_statements`? What does it track?
- What is extended statistics? (`CREATE STATISTICS`) — PG 10+
  - For correlated columns — tells planner about multi-column correlations
- What is `enable_seqscan`, `enable_indexscan`, `enable_hashjoin`, etc.?
- What is `random_page_cost` and `seq_page_cost`? Why does `random_page_cost` matter for index decisions?
- What is `effective_cache_size`? How does it affect planner decisions?
- What is `work_mem`? What operations use it?
  - Sorting, hashing, bitmap operations. Each node can use up to `work_mem`.
- What is `parallel_tuple_cost`, `parallel_setup_cost`, `min_parallel_table_scan_size`?
- What is JIT compilation in PostgreSQL 11+? (`jit = on`)
- What is `jit_above_cost`?

---

## 13. Performance Tuning & Configuration

### Key Configuration Parameters

- What is `shared_buffers`? What is the recommended value? (25% of RAM)
- What is `effective_cache_size`? What should it be set to? (50–75% of RAM — hint to planner, not allocation)
- What is `work_mem`? Why is setting it too high dangerous?
  - Each sort/hash node per query can use `work_mem`. With 100 connections and 5 nodes each: 100 × 5 × work_mem
- What is `maintenance_work_mem`? What operations use it? (`VACUUM`, `CREATE INDEX`, `ALTER TABLE ADD FOREIGN KEY`)
- What is `max_connections`? What is the overhead of each PostgreSQL connection?
  - Each connection spawns a backend process (~5–10 MB). High connections → use PgBouncer
- What is `max_wal_size`? What is `min_wal_size`?
- What is `wal_buffers`? What is the default? (`-1` = auto: 1/32 of shared_buffers, max 64MB)
- What is `checkpoint_completion_target`? Why set it to 0.9?
- What is `random_page_cost`? What should it be for SSDs? (1.1–2.0 for SSD vs default 4.0 for HDD)
- What is `effective_io_concurrency`? What should it be for SSDs? (200 for SSD, 2 for HDD)
- What is `max_worker_processes`, `max_parallel_workers`, `max_parallel_workers_per_gather`?
- What is `log_min_duration_statement`? How do you use it to find slow queries?
- What is `log_slow_query`?
- What is `pg_stat_statements.max` and `pg_stat_statements.track`?
- What is `track_io_timing`? What does it add to EXPLAIN ANALYZE output?
- What is `huge_pages`? When should you enable it?
- What is `temp_file_limit`?
- What is `autovacuum_vacuum_cost_delay`? How does it affect I/O load?
- What is `bgwriter_lru_maxpages`?

### Common Performance Problems & Fixes

- What is the N+1 query problem in PostgreSQL? How do you fix it?
- What is a missing index? How do you find tables with high `seq_scan` counts on large tables?
  - Query `pg_stat_user_tables` for `seq_scan > 0 AND n_live_tup > 100000`
- What is index bloat? How does it affect query performance?
- What is a sequential scan on a large table with an existing index? What causes the planner to ignore the index?
  - Low selectivity, stale statistics, correlation = 1, `random_page_cost` too high vs actual disk speed
- What is `pg_stat_statements`? How do you find the top 10 slowest queries?
- What is `log_lock_waits`?
- What is `auto_explain.log_min_duration`?
- What is table bloat impact on performance?
- What is the `planner vs actual rows` discrepancy in EXPLAIN? What causes it?
- What are temp files in PostgreSQL? When are they created? How do you detect them?
  - Created when an operation exceeds `work_mem`. Check `pg_stat_database.temp_files` and `temp_bytes`.
- What is the impact of too many indexes on write performance?
- What is `CLUSTER` and when does it help? (Re-orders table on disk according to index — improves sequential access)
- What is `pg_prewarm` extension?

---

## 14. Connection Pooling — PgBouncer & Pgpool

### Why Connection Pooling

- Why does PostgreSQL need a connection pooler?
  - Each PostgreSQL connection = dedicated OS process (~5–10 MB). 1000 connections = 5–10 GB RAM wasted.
- What is the problem with too many `max_connections` in PostgreSQL?
- What is PgBouncer? What problem does it solve?

### PgBouncer

- What are the 3 pooling modes in PgBouncer?
  - **Session mode**: connection held for entire client session (equivalent to no pooling for persistent connections)
  - **Transaction mode**: connection returned to pool after each transaction (recommended)
  - **Statement mode**: connection returned after each statement (only for autocommit workloads)
- What is the recommended PgBouncer mode? (`transaction` mode)
- What features are NOT available in transaction mode?
  - `SET` (session-level), prepared statements (unless tracked), advisory locks, `LISTEN/NOTIFY`, temporary tables
- What is `pool_mode` in PgBouncer?
- What is `max_client_conn`? What is `default_pool_size`?
- What is the connection string format for PgBouncer?
- What is `server_idle_timeout`?
- What is `client_idle_timeout`?
- What is `server_lifetime`?
- What is `SHOW POOLS` in PgBouncer admin? What is `SHOW STATS`?
- What is `PAUSE` and `RESUME` in PgBouncer?
- What is `RELOAD` in PgBouncer?
- What is `reserve_pool_size` and `reserve_pool_timeout`?
- What is the difference between PgBouncer and Pgpool-II?
- What is `pgcat`? (Rust-based connection pooler — newer alternative)
- What is connection string pinning in transaction mode?
- What is `idle_transaction_timeout` in PostgreSQL? How does it help connection pools?

### Pgpool-II

- What is Pgpool-II? What features does it provide beyond connection pooling?
  - Connection pooling, read/write splitting, load balancing, replication, failover, parallel query
- What is the query routing in Pgpool-II?
- What are the watchdog features in Pgpool-II?

---

## 15. JSON & JSONB

- What is `json` type vs `jsonb` type? What are the key differences?
  - `json`: stores raw text, preserves whitespace/key order, slower queries; `jsonb`: binary format, deduplicates keys, supports indexing, faster queries
- Which should you use in most cases and why? (`jsonb`)
- What is the `->` operator? What is `->>`?
  - `->`: returns JSON object/array element; `->>`: returns text
- What is `#>` and `#>>`? (path navigation for nested JSON)
- What is `@>` operator? (contains — JSON includes)
- What is `<@` operator? (is contained by)
- What is `?` operator? (key existence)
- What is `?|` and `?&`? (any key / all keys exist)
- What is `||` operator on JSONB? (merge)
- What is `-` operator on JSONB? (delete key)
- What is `jsonb_set()`? What is `jsonb_insert()`?
- What is `jsonb_each()`, `jsonb_object_keys()`, `jsonb_array_elements()`?
- What is `json_agg()`, `json_build_object()`, `json_build_array()`, `row_to_json()`?
- What is `to_jsonb()`, `to_json()`?
- How do you index JSONB? What index type? (GIN index with `jsonb_path_ops` or default `jsonb_ops`)
- What is the difference between `jsonb_ops` and `jsonb_path_ops` GIN operator classes?
  - `jsonb_ops`: supports `?`, `?|`, `?&`, `@>`; `jsonb_path_ops`: only `@>` but smaller and faster
- What is `jsonpath` in PostgreSQL 12+? What is `jsonb_path_query()`?
- What is `@@` and `@?` operator for jsonpath?
- What is `jsonb_path_match()`, `jsonb_path_exists()`?
- When would you use JSONB vs a normalized relational schema?
- What are the limitations of JSONB? (no schema enforcement, harder to query deeply nested, no referential integrity)

---

## 16. Full-Text Search

- What is full-text search (FTS) in PostgreSQL?
- What is `tsvector`? What is `tsquery`?
- What is `to_tsvector('english', text)`?
- What is `to_tsquery('english', 'word1 & word2')`?
- What is `plainto_tsquery()`? What is `phraseto_tsquery()`? What is `websearch_to_tsquery()`?
- What is the `@@` match operator?
- What is `ts_rank()`? What is `ts_rank_cd()`?
- What is `ts_headline()`? (returns document with matches highlighted)
- What is a text search configuration? (`pg_catalog.english`, etc.)
- How do you create a GIN index for full-text search?
  ```sql
  CREATE INDEX ON articles USING GIN(to_tsvector('english', body));
  ```
- What is a `tsvector` column? Why is it better than indexing `to_tsvector()` directly?
  - Stored computed tsvector column + index on that column = faster inserts, smaller index overhead
- How do you keep a tsvector column updated? (trigger or generated column)
- What are the limitations of PostgreSQL FTS vs Elasticsearch?
  - No fuzzy matching, limited language support, no relevance tuning, no autocomplete, no faceted search
- When would you use PostgreSQL FTS vs Elasticsearch?
- What is `pg_trgm` extension? What does it enable? (trigram similarity, fuzzy search, LIKE/ILIKE indexing)
- What is trigram similarity? What is `similarity()`? What is `%` operator?
- What is `GIN` vs `GiST` index for `pg_trgm`?

---

## 17. Stored Procedures, Functions & Triggers

### Functions

- What is the difference between a function and a procedure in PostgreSQL?
  - Functions return values, can be used in SELECT; Procedures (PG 11+) can use transactions, called with CALL
- What are PL/pgSQL functions? How do you create one?
- What is `$$` dollar quoting?
- What is `LANGUAGE plpgsql` vs `LANGUAGE sql` vs `LANGUAGE python`?
- What is a `RETURNS TABLE(...)` function? What is `RETURNS SETOF`?
- What is `RETURN NEXT` vs `RETURN QUERY`?
- What is `STRICT` on a function? (`RETURNS NULL ON NULL INPUT`)
- What is `CALLED ON NULL INPUT`?
- What is `IMMUTABLE`, `STABLE`, `VOLATILE` on a function?
  - `IMMUTABLE`: same args always return same result (can be indexed); `STABLE`: same result within a transaction; `VOLATILE`: default, may change
- What is `SECURITY DEFINER` vs `SECURITY INVOKER` function?
- What is `COST` on a function? What is `ROWS` on a set-returning function?
- What is `PARALLEL SAFE`, `PARALLEL RESTRICTED`, `PARALLEL UNSAFE`?
- What are PL/Python, PL/Perl, PL/Tcl, PL/V8 languages?

### Triggers

- What is a trigger in PostgreSQL?
- What is a `BEFORE` trigger vs an `AFTER` trigger vs an `INSTEAD OF` trigger?
- What is a `FOR EACH ROW` trigger vs `FOR EACH STATEMENT` trigger?
- What is `OLD` and `NEW` in a trigger?
- What is a `WHEN` condition on a trigger?
- What is a constraint trigger?
- What is a transition table in a trigger? (`REFERENCING NEW TABLE AS new_data`)
- When would you use a trigger vs application logic?
- What are the performance implications of triggers?
- What is a trigger function? What must it return?
- What is `tg_op`? What is `tg_table_name`?
- What is `pg_trigger` catalog?

### Procedures & Transactions

- What is `CREATE PROCEDURE` (PG 11+)?
- What is `CALL procedure_name()`?
- How do procedures differ from functions regarding transaction control?
  - Procedures can call `COMMIT` and `ROLLBACK` within the body
- What is `EXCEPTION` block in PL/pgSQL?
- What is `GET DIAGNOSTICS`?

---

## 18. Security & Access Control

### Authentication

- What is `pg_hba.conf`? What are the authentication methods?
  - `trust`, `reject`, `md5`, `scram-sha-256`, `peer`, `ident`, `ldap`, `radius`, `cert`, `pam`, `gss`
- What is the difference between `md5` and `scram-sha-256`? Which is recommended?
- What is `peer` authentication?
- What is `ssl = on` in postgresql.conf? What is `hostssl` in pg_hba.conf?
- What is `sslmode` in connection string? (`disable`, `require`, `verify-ca`, `verify-full`)
- What is `ssl_cert_file`, `ssl_key_file`, `ssl_ca_file`?

### Authorization & Roles

- What is the role system in PostgreSQL?
- What is `CREATE ROLE` vs `CREATE USER`? (User = role with LOGIN privilege)
- What is `GRANT` and `REVOKE`?
- What are the key privileges? (`SELECT`, `INSERT`, `UPDATE`, `DELETE`, `TRUNCATE`, `REFERENCES`, `TRIGGER`, `CONNECT`, `TEMPORARY`, `EXECUTE`, `USAGE`, `CREATE`)
- What is `GRANT SELECT ON ALL TABLES IN SCHEMA public TO role`?
- What is `ALTER DEFAULT PRIVILEGES`?
- What is `GRANT CONNECT ON DATABASE` vs `GRANT USAGE ON SCHEMA`?
- What is the `public` schema default privilege issue? (All users can create objects — tighten with `REVOKE CREATE ON SCHEMA public FROM PUBLIC`)
- What is Row-Level Security (RLS)?
- What is `ALTER TABLE t ENABLE ROW LEVEL SECURITY`?
- What is `CREATE POLICY`? What are `USING` and `WITH CHECK` clauses?
- What is `BYPASSRLS` role attribute?
- What is `current_user` vs `session_user`?
- What is `SET ROLE`? What is `RESET ROLE`?
- What is superuser? When should you avoid using it?
- What is `pg_read_all_data` and `pg_write_all_data` (PG 14+)?

### Audit & Compliance

- What is `pgaudit` extension? What does it log?
- What is `log_statement`? What are the values? (`none`, `ddl`, `mod`, `all`)
- What is `log_connections` and `log_disconnections`?
- What is `log_duration`? What is `log_min_duration_statement`?

---

## 19. Backup, Restore & Point-in-Time Recovery

### Backup Tools

- What is `pg_dump`? What formats does it support? (`plain`, `custom`, `directory`, `tar`)
- What is the difference between `pg_dump` and `pg_dumpall`?
- What is `pg_restore`? When do you use it?
- What is the custom format (`-Fc`)? Why is it preferred over plain SQL?
- What is `pg_dump -t tablename`? What is `pg_dump -s` (schema only)?
- What is `pg_dump -n schema`?
- What is `--no-owner`, `--no-privileges` in pg_dump?
- What is `--clean` and `--if-exists` in pg_dump?
- What is parallel restore? (`pg_restore -j 4`)
- What is `pg_basebackup`? What does it do?
- What is `pg_basebackup -P -R`? What is `-R`? (writes recovery config for replica)
- What is `pg_dump` vs `pg_basebackup`? (logical vs physical backup)

### Point-in-Time Recovery (PITR)

- What is PITR? How does it work in PostgreSQL?
- What is WAL archiving? What is `archive_command`?
- What is `archive_status`?
- What is a base backup in PITR context?
- What is `recovery_target_time`? What is `recovery_target_lsn`? What is `recovery_target_name`?
- What is `recovery_target_inclusive`?
- What is `restore_command`?
- What is `pg_wal_replay_pause()` and `pg_wal_replay_resume()` in recovery?
- What is Barman? What is its role in PITR?
- What is `pgBackRest`? How does it compare to Barman?
- What is WAL-G? (faster, cloud-native WAL archiving and backup tool)
- What is `pg_dump` restore time vs PITR restore time trade-off?
- What is RTO (Recovery Time Objective) and RPO (Recovery Point Objective)?

---

## 20. Extensions & Tooling

### Key Extensions

- What is `pg_stat_statements`? How do you enable and use it?
- What is `auto_explain`? How do you enable it?
- What is `pg_trgm`? What does it enable?
- What is `uuid-ossp`? What is `gen_random_uuid()` (built-in PG 13+)?
- What is `pgcrypto`? What functions does it provide?
- What is `tablefunc`? What is `crosstab()` (pivot)?
- What is `pg_partman`? What does it automate?
- What is `PostGIS`? What does it add?
- What is `TimescaleDB`? What is it built for? (time-series data on PostgreSQL)
- What is `pgvector`? What does it enable? (vector similarity search for AI/ML embeddings)
- What is `pg_repack`? What does it do?
- What is `pgstattuple`? What information does it provide?
- What is `pageinspect`? What low-level info does it expose?
- What is `pg_visibility`? What does it reveal about the visibility map?
- What is `pg_buffercache`? What does it show?
- What is `pg_prewarm`? What does it do? (pre-loads data into shared_buffers)
- What is `file_fdw`? What is `postgres_fdw`? What are Foreign Data Wrappers?
- What is `dblink`?
- What is `pg_cron`? What does it enable?
- What is `hypopg`? What is a hypothetical index?

### Administrative Tooling

- What is `pgAdmin`? What are alternatives? (DBeaver, DataGrip, TablePlus)
- What is `pgBadger`? What does it analyze? (PostgreSQL log analyzer for slow queries, lock waits)
- What is `pgmetrics`? What is `pganalyze`?
- What is `Percona Monitoring and Management (PMM)` for PostgreSQL?
- What is `check_postgres` monitoring script?
- What is `Postgres Exporter` for Prometheus?
- What is `pgbench`? What does it benchmark?

---

## 21. Scaling — Sharding, Citus & Read Replicas

- Does PostgreSQL have built-in sharding? (No — use Citus, manual sharding, or FDW-based partitioning)
- What is Citus? What does it add to PostgreSQL?
  - Distributed query execution, distributed tables, reference tables, columnar storage, parallel ingestion
- What is a distributed table in Citus? What is a reference table?
- What is the Citus coordinator? What are Citus worker nodes?
- What is co-location in Citus?
- What is the shard count in Citus? (default 32 shards per table)
- What is `create_distributed_table()` in Citus?
- What is `run_command_on_workers()`?
- What is the trade-off of cross-shard queries in Citus?
- How do you scale reads in PostgreSQL? (read replicas + load balancing)
- What is Pgpool-II read-write splitting?
- What is application-level read/write splitting?
- What is connection load balancing with multiple replicas?
- What is `PUBLICATION FOR ALL TABLES`? What is logical replication for read scaling?
- What is a foreign data wrapper (FDW) based federation?
- What is `postgres_fdw`? How does it enable cross-database queries?
- When should you consider sharding vs partitioning vs replicas?
- What is `pg_partman` + logical replication for time-series offloading?
- What is Aurora PostgreSQL? How does its storage layer differ from vanilla PostgreSQL?
- What is AlloyDB? (Google's PostgreSQL-compatible cloud DB)
- What is Neon? (serverless PostgreSQL with branching)
- What is Supabase? (PostgreSQL-based backend-as-a-service)

---

## 22. Monitoring & Observability

### System Views & Statistics

- What is `pg_stat_activity`? What are the key columns?
  - `pid`, `state`, `wait_event_type`, `wait_event`, `query`, `query_start`, `state_change`, `client_addr`
- What are the `state` values in `pg_stat_activity`?
  - `active`, `idle`, `idle in transaction`, `idle in transaction (aborted)`, `fastpath function call`, `disabled`
- What is `pg_stat_user_tables`? What columns matter most?
  - `seq_scan`, `idx_scan`, `n_live_tup`, `n_dead_tup`, `last_vacuum`, `last_autovacuum`, `last_analyze`
- What is `pg_stat_user_indexes`? What is `idx_scan` used for?
- What is `pg_stat_database`? What columns are important?
  - `numbackends`, `xact_commit`, `xact_rollback`, `blks_hit`, `blks_read`, `tup_fetched`, `temp_files`, `temp_bytes`, `deadlocks`
- What is `pg_stat_bgwriter`? What metrics does it expose?
- What is `pg_stat_replication`? What columns indicate lag?
- What is `pg_stat_wal`?
- What is `pg_stat_progress_vacuum`? What does it show?
- What is `pg_stat_progress_index`? What is `pg_stat_progress_cluster`?
- What is `pg_locks`? What is `pg_blocking_pids()`?
- What is `pg_stat_statements`? How do you find top queries by total time?
  ```sql
  SELECT query, calls, total_exec_time, mean_exec_time
  FROM pg_stat_statements
  ORDER BY total_exec_time DESC
  LIMIT 20;
  ```
- What is cache hit ratio? How do you calculate it?
  ```sql
  SELECT blks_hit::float / (blks_hit + blks_read) AS cache_hit_ratio
  FROM pg_stat_database WHERE datname = current_database();
  ```
- What is a good cache hit ratio target? (> 99%)
- What is `pg_stat_reset()`?
- What is `pg_statio_user_tables`? What does it expose? (buffer hits and disk reads per table)
- What is `txid_current()` vs `age(relfrozenxid)` monitoring?
- What metrics should you monitor in PostgreSQL production?
  - Connection count, replication lag, cache hit ratio, dead tuple count, bloat, VACUUM frequency, lock waits, long-running transactions, temp file usage, XID age

---

## 23. PostgreSQL vs Other Databases

### PostgreSQL vs MySQL

- What are the key differences between PostgreSQL and MySQL?
- Which has better MVCC implementation? (PostgreSQL — no-lock reads and writes)
- Which supports more data types natively? (PostgreSQL — arrays, JSONB, ranges, hstore, geometric)
- Which has better standards SQL compliance? (PostgreSQL)
- What does MySQL not support that PostgreSQL does? (partial indexes, index-only scan via INCLUDE, CTEs with modification, FULL OUTER JOIN in older versions, defer constraints, writeable CTEs, window functions were added later)
- What is the default transaction isolation in MySQL InnoDB? (`REPEATABLE READ`) vs PostgreSQL? (`READ COMMITTED`)
- How does full-text search compare? (PostgreSQL built-in vs MySQL FULLTEXT index)

### PostgreSQL vs Oracle

- What does Oracle have that PostgreSQL lacks? (Partitioned global indexes, result cache, more PL/SQL features)
- What open-source tools help migrate from Oracle to PostgreSQL? (ora2pg, AWS SCT)
- What is `pg_compat` and Oracle compatibility mode?

### PostgreSQL vs Other NoSQL/NewSQL

- When would you choose PostgreSQL over MongoDB? (strong consistency, complex queries, referential integrity, JSONB is "good enough" JSON)
- When would you choose MongoDB over PostgreSQL?
- What is CockroachDB? How does it compare? (NewSQL — PostgreSQL wire-compatible, distributed, multi-region)
- What is YugabyteDB? (PostgreSQL-compatible distributed SQL)
- What is Amazon Aurora PostgreSQL? What is its storage innovation?
- What is Google AlloyDB? (columnar engine acceleration + PostgreSQL)
- What is Neon? (serverless PostgreSQL with storage/compute separation and branching)

---

## 24. Situation-Based / Scenario Questions

---

### 🔴 Performance & Slow Query Scenarios

**S1.** A query that was fast last month is now taking 30 seconds. No code was changed. How do you investigate?
> — Step 1: Run `EXPLAIN (ANALYZE, BUFFERS)` — check if plan changed (e.g., switched from index scan to seq scan). Step 2: Check `pg_stat_statements` for mean_exec_time trend. Step 3: Check if statistics are stale — run `ANALYZE table`. Step 4: Check for table/index bloat. Step 5: Check if new rows caused the planner to change strategy (statistics need refresh). Step 6: Check if new indexes were added/dropped. Step 7: Check if `work_mem` is causing disk spills (temp files). Fix: `ANALYZE`, potentially `VACUUM`, check `random_page_cost` for SSD, update statistics target.

**S2.** Your PostgreSQL server CPU is at 100% during business hours. How do you diagnose it?
> — Query `pg_stat_activity` for `state = 'active'` to find running queries. Look at `query` and `query_start` for long-running ones. Use `pg_stat_statements` ordered by `total_exec_time` to find expensive queries. Check for full sequential scans on large tables (`pg_stat_user_tables.seq_scan`). Check for missing indexes. Look for lock contention (`wait_event_type = 'Lock'`). Check connection count — too many connections causes overhead. Use `pg_blocking_pids()` to find blocked queries.

**S3.** `EXPLAIN ANALYZE` shows `actual rows = 50000` but `estimated rows = 10`. What causes this and what is the fix?
> — Severe statistics underestimation. Causes: table grew rapidly after last `ANALYZE`; column has high correlation that planner doesn't know about; multiple correlated columns (planner assumes independence). Fix: run `ANALYZE table`; increase `default_statistics_target` or per-column statistics (`ALTER TABLE t ALTER COLUMN c SET STATISTICS 500`); create extended statistics for correlated columns (`CREATE STATISTICS s ON col1, col2 FROM table`).

**S4.** A specific query is doing a `Seq Scan` on a 100M-row table even though the column has a B-tree index. Why?
> — Planner considers seq scan cheaper when: selectivity is low (>10–15% of rows returned), statistics are stale, `random_page_cost` is too high relative to actual disk speed (use 1.1 for SSD), `effective_cache_size` is set too low. Fix: update statistics, lower `random_page_cost` for SSD, ensure the WHERE clause matches the index, check if function is applied to indexed column (prevents index use — create expression index instead).

**S5.** Your sort operations are writing to temp files, causing slow queries. What do you do?
> — Temp files are created when sort/hash exceeds `work_mem`. Fix: increase `work_mem` for the session or globally. Be careful: `work_mem` per sort node per connection. Check `log_temp_files = 0` to log all temp file creation. Use `EXPLAIN (ANALYZE, BUFFERS)` to see `Sort Method: external merge Disk`. Also consider adding an index to avoid the sort entirely. Monitor `pg_stat_database.temp_files` and `temp_bytes`.

---

### 🔴 VACUUM & Bloat Scenarios

**S6.** Your PostgreSQL table is 500 GB but only has 100 GB of actual data. VACUUM isn't reclaiming space. What is happening?
> — Table has severe bloat (dead tuples). Regular `VACUUM` marks space as reusable but doesn't return it to the OS. Options: (1) `VACUUM FULL` — rewrites table, returns space, but requires `ACCESS EXCLUSIVE` lock (downtime). (2) `pg_repack` — rewrites table online without long lock. (3) `pg_squeeze`. Check if autovacuum is running frequently enough. Check for long-running transactions blocking vacuum (`pg_stat_activity` for old `xmin`).

**S7.** Autovacuum is running on a table constantly but the table keeps bloating. What are the possible causes?
> — High write/update rate generating dead tuples faster than vacuum can clean. Autovacuum too throttled (`autovacuum_vacuum_cost_delay` too high). Long-running transactions holding back the vacuum horizon (vacuum can't remove tuples visible to older transactions). Replication slot holding `xmin` back. Fix: Tune autovacuum per table (`autovacuum_vacuum_scale_factor = 0.01` for large tables), increase `autovacuum_max_workers`, check `pg_replication_slots` for `xmin` lag, kill blocking long transactions.

**S8.** You see the warning "WARNING: database is not accepting commands to avoid wraparound data loss." What happened and how do you recover?
> — Transaction ID wraparound danger. The database has frozen to prevent data corruption. PostgreSQL enters this state when `datfrozenxid` age approaches `autovacuum_freeze_max_age`. Recovery: connect via single-user mode. Run `VACUUM FREEZE` on affected tables. Check `pg_database` for `datfrozenxid` age. Long-term: monitor XID age (`SELECT max(age(datfrozenxid)) FROM pg_database`), set alert at 1.5 billion, tune `autovacuum_freeze_max_age`.

**S9.** A long-running analytics query (running for 6 hours) is blocking VACUUM and causing table bloat to grow. How do you handle it?
> — The long transaction's `xmin` prevents VACUUM from removing dead tuples older than that transaction. Options: Cancel the blocking query (`pg_cancel_backend(pid)`) or terminate it (`pg_terminate_backend(pid)`). Set `statement_timeout` for analytics queries. Move analytics to a read replica. Set `idle_in_transaction_session_timeout`. Monitor with `pg_stat_activity` and alert on transactions older than X minutes.

---

### 🔴 Replication & HA Scenarios

**S10.** Your primary PostgreSQL server crashed and the replica is behind by 30 seconds. How do you promote it and what data might you lose?
> — Run `pg_ctl promote -D $PGDATA` or use `pg_promote()` function (PG 12+). The 30-second lag means ~30 seconds of data may be lost (RPO = 30 seconds). After promotion: update application connection string to point to the new primary. To prevent future data loss: use synchronous replication (`synchronous_commit = on`, `synchronous_standby_names`). Use Patroni for automated failover.

**S11.** Your replica's replication lag keeps growing and is now 10 minutes behind. How do you investigate?
> — Check `pg_stat_replication` on primary: `write_lag`, `flush_lag`, `replay_lag`. On replica: check `pg_stat_wal_receiver`. Possible causes: heavy write load on primary outpacing replica; `max_wal_size` too small causing checkpoint pressure; replica CPU/disk bottleneck; network bandwidth saturation; `hot_standby_feedback = on` + long queries on replica slowing vacuum on primary (causing more WAL). Fix: dedicated replica disk I/O, increase `wal_receiver_status_interval`, check replica query load.

**S12.** An unused replication slot is causing your primary PostgreSQL server's disk to fill up with WAL files. How do you fix it?
> — Unused replication slots prevent WAL cleanup. Fix: drop the unused slot (`SELECT pg_drop_replication_slot('slot_name')`). Prevent recurrence: set `max_slot_wal_keep_size` (PG 13+) to limit WAL accumulation per slot. Monitor `pg_replication_slots.active` and `pg_replication_slots.wal_status`. Alert when `pg_replication_slots.retained_wal` grows beyond threshold.

---

### 🔴 Locking & Deadlock Scenarios

**S13.** Your application is intermittently getting deadlock errors (`ERROR: deadlock detected`). How do you diagnose and fix it?
> — PostgreSQL logs include the deadlock details (`log_lock_waits = on`, `deadlock_timeout = 1s`). Examine the log for the two transactions and their lock sequences. Fix: ensure all transactions acquire locks in the same order. Use `SELECT ... FOR UPDATE` consistently. Shorten transactions. Use `NOWAIT` or `SKIP LOCKED` for queue-like patterns. Application must retry on `deadlock_detected` error (SQLSTATE `40P01`).

**S14.** An `ALTER TABLE ADD COLUMN` is blocking all reads and writes for minutes. How do you avoid this?
> — `ALTER TABLE` acquires `ACCESS EXCLUSIVE` lock. For adding a column with a non-volatile default, PostgreSQL 11+ does it instantly without rewrite (stored in catalog). For adding NOT NULL column with default in older versions: (1) Add nullable column, (2) backfill in batches, (3) add constraint. Use `pg_repack` for table rewrites. Run DDL during low-traffic windows. Use `lock_timeout = '2s'` to avoid indefinite lock waits, retry until acquired.

**S15.** A query is blocked waiting for a lock held by an `idle in transaction` connection. How do you handle it?
> — The `idle in transaction` connection opened a transaction, acquired a lock, and went idle (application bug — forgot to commit). Fix immediately: identify with `pg_stat_activity WHERE state = 'idle in transaction'`. Kill with `pg_terminate_backend(pid)`. Long-term: set `idle_in_transaction_session_timeout = '30s'` in `postgresql.conf`. Fix the application to commit/rollback promptly.

---

### 🔴 Schema & Migration Scenarios

**S16.** You need to add an index to a 500M-row table in production without downtime. How?
> — Use `CREATE INDEX CONCURRENTLY` — builds index without holding a lock on the table. It does two scans (takes longer, ~3x the time), cannot run inside a transaction block, and may fail (leaving an invalid index — detectable in `pg_indexes` or `pg_index.indisvalid`). If it fails: `DROP INDEX CONCURRENTLY` the invalid one and retry. Monitor progress with `pg_stat_progress_create_index`.

**S17.** You need to change a column type from `VARCHAR(100)` to `TEXT` in production on a large table. What is the safest approach?
> — `ALTER TABLE t ALTER COLUMN c TYPE TEXT` rewrites the entire table and acquires `ACCESS EXCLUSIVE` lock. Safe approach: (1) Add a new `TEXT` column. (2) Write a trigger to sync old → new column. (3) Backfill in batches: `UPDATE t SET new_col = old_col WHERE id BETWEEN x AND y`. (4) Swap columns. (5) Drop trigger and old column. Alternatively, for `VARCHAR → TEXT` specifically: PostgreSQL may do it with minimal lock as an optimization (check your version).

**S18.** You have a multi-GB table and need to delete all rows older than 1 year. `DELETE FROM` is blocking everything. How do you do it safely?
> — Large `DELETE` holds a lock and generates huge WAL. Safe approach: Delete in batches (`DELETE FROM t WHERE id IN (SELECT id FROM t WHERE created_at < now() - interval '1 year' LIMIT 10000)`), add delay between batches to let autovacuum and replication keep up. Better: Use table partitioning by date — `DETACH PARTITION` of old partition + `DROP TABLE` is near-instant with no lock on main table.

---

### 🔴 Connection & Pooling Scenarios

**S19.** Your PostgreSQL server has 500 open connections, `max_connections = 500`, and new connections are being refused. Memory usage is at 90%. What do you do?
> — PostgreSQL connections are expensive (~10 MB each). Fix: Deploy PgBouncer in transaction mode immediately. Set `max_connections` back to 100–200. PgBouncer maintains a smaller pool to PostgreSQL while handling thousands of client connections. Find and close idle connections (`pg_terminate_backend` for `state = 'idle'` and `idle_in_transaction`). Set `idle_in_transaction_session_timeout`, `tcp_keepalives_idle`.

**S20.** After enabling PgBouncer in transaction pooling mode, your application is getting errors with prepared statements and `SET` commands. Why?
> — In transaction mode: (1) Prepared statements are tied to a session — PgBouncer doesn't route them to the same backend. Fix: disable prepared statements in the application driver (e.g., `prepareThreshold=0` in JDBC). (2) `SET` commands are session-level — reset when connection is returned to pool. Fix: use `SET LOCAL` inside transactions. (3) Advisory locks, `LISTEN/NOTIFY`, and temp tables don't work in transaction mode.

---

### 🔴 Architecture & Design Scenarios

**S21.** You're building a multi-tenant SaaS on PostgreSQL. How do you design for tenant isolation?
> — Three approaches: (1) **Database-per-tenant**: strongest isolation, complex to manage, hard to query across tenants. (2) **Schema-per-tenant**: moderate isolation, shared server, use `search_path` per connection. (3) **Shared table with tenant_id column**: easiest management, add RLS policy (`CREATE POLICY ... USING (tenant_id = current_setting('app.tenant_id'))`), add index on `tenant_id` in all tables. Most SaaS apps use shared table + RLS with PgBouncer setting `SET LOCAL app.tenant_id = $1`.

**S22.** A time-series table with 10 billion rows is causing query timeouts and autovacuum struggles to keep up. How do you redesign it?
> — Partition the table by time range (monthly or daily): `PARTITION BY RANGE (created_at)`. Old partitions are never updated — vacuum rarely needed. Queries that filter by date prune to one partition. Old partitions can be detached and archived. Use TimescaleDB for automatic hypertable management with built-in compression, continuous aggregates, and data tiering. Add BRIN index on `created_at` (very efficient for naturally ordered time-series data).

**S23.** You need zero-downtime major PostgreSQL version upgrade (e.g., PG 14 → PG 16). How do you do it?
> — `pg_upgrade` requires downtime. Zero-downtime approaches: (1) **Logical replication**: Set up PG 16 replica using logical replication from PG 14 primary. Switch over when caught up (seconds of downtime). (2) **pglogical**: Same approach with pglogical extension. (3) **Blue-green**: Run both versions, switch connection string. Key steps: set `wal_level = logical`, create publication on old, subscription on new, sync sequences manually (sequences are not replicated), verify data, promote new, update connection string.

**S24.** Your application has very high write throughput (100K inserts/second). PostgreSQL is struggling. What are your options?
> — (1) Use `COPY` instead of `INSERT` for bulk loads (10–100x faster). (2) Batch inserts with multi-row `INSERT INTO t VALUES (...),(...)`. (3) Disable synchronous commit for non-critical writes (`synchronous_commit = off` — up to 600ms data loss risk). (4) Use unlogged tables for temporary data. (5) Partition the write table to reduce index size. (6) Use `BRIN` indexes instead of B-tree for append-only tables. (7) Consider Citus for distributed writes. (8) Use message queue (Kafka) to buffer writes and process in batches.

---

## 25. High-Frequency Quick Reference

Questions asked in **nearly every PostgreSQL interview**, sorted by importance:

| # | Question | Frequency |
|---|---|---|
| 1 | What is MVCC? How does `xmin`/`xmax` work? | 🔴 Always |
| 2 | What are the index types in PostgreSQL? When do you use GIN vs GiST vs BRIN? | 🔴 Always |
| 3 | What is `EXPLAIN ANALYZE`? How do you read it? | 🔴 Always |
| 4 | What is `VACUUM` vs `VACUUM FULL`? Why does autovacuum matter? | 🔴 Always |
| 5 | What are the transaction isolation levels? What anomalies does each prevent? | 🔴 Always |
| 6 | What is WAL? How does it ensure durability? | 🔴 Always |
| 7 | What is the difference between streaming replication and logical replication? | 🔴 Always |
| 8 | What is a deadlock? How does PostgreSQL detect and handle it? | 🔴 Always |
| 9 | What is `SELECT FOR UPDATE`? What is `SKIP LOCKED`? | 🔴 Always |
| 10 | What is `jsonb` vs `json`? When do you use each? | 🔴 Always |
| 11 | What is a partial index? A covering index (`INCLUDE`)? | 🔴 Always |
| 12 | What is table partitioning? What are the 3 strategies? | 🔴 Always |
| 13 | What is `pg_stat_statements`? How do you find slow queries? | 🔴 Always |
| 14 | What is `DISTINCT ON`? When do you use it? | 🟠 Very Likely |
| 15 | What is a window function? `ROW_NUMBER()` vs `RANK()` vs `DENSE_RANK()`? | 🟠 Very Likely |
| 16 | What is a recursive CTE? When do you use it? | 🟠 Very Likely |
| 17 | What is transaction ID wraparound? How do you prevent it? | 🟠 Very Likely |
| 18 | What is `CREATE INDEX CONCURRENTLY`? Why can't you run it in a transaction? | 🟠 Very Likely |
| 19 | What is connection pooling? What is PgBouncer? What modes does it support? | 🟠 Very Likely |
| 20 | What is `LATERAL JOIN`? When do you need it? | 🟠 Very Likely |
| 21 | What is `hot_standby_feedback`? What is the risk of enabling it? | 🟡 Senior Level |
| 22 | What is `pg_repack`? How does it differ from `VACUUM FULL`? | 🟡 Senior Level |
| 23 | What is Row-Level Security (RLS)? How do you use it for multi-tenancy? | 🟡 Senior Level |
| 24 | What is `synchronous_commit = off`? What is the data loss risk? | 🟡 Senior Level |
| 25 | What is BRIN index? When is it more efficient than B-tree? | 🟡 Senior Level |
| 26 | What is `work_mem`? Why is setting it too high dangerous? | 🟡 Senior Level |
| 27 | What is an unused replication slot? Why is it dangerous? | 🟡 Senior Level |
| 28 | What is SSI (Serializable Snapshot Isolation)? | 🟡 Senior Level |
| 29 | What is HOT update? What conditions enable it? | 🟡 Senior Level |
| 30 | What is `pg_stat_progress_vacuum`? What does it tell you? | 🟡 Senior Level |
