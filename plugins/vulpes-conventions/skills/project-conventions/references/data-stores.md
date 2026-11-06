# Data stores

Select the store by the kind of data.\
Each record MUST have one store as its source of truth.

| Kind | Default | Use it for | Source of truth |
| --- | --- | --- | --- |
| Relational | PostgreSQL | Business records, records that change together | Yes |
| Document | MongoDB | One aggregate in one document, when the shape changes from item to item | Yes |
| Cache and key-value | Redis or Valkey | Cached values, short-lived counters, locks with an expiry | No |
| Object storage | S3-compatible storage | Files | Yes, for the files |

- Write the code that reads and writes a store only in `infrastructure`.
- Run each query at least once in an integration test against the real store (Testcontainers or a compose service).
- Back up each store that is a source of truth on a schedule.\
  Use the backups of the managed service, or make your own.\
  Do a test of the restore on a schedule.
- A schema change MUST work with the old and the new version of the server at the same time.
- Change a schema in two steps.\
  First, add the new form.\
  Then, remove the old form when no version that runs uses it.
- Run a change that is not compatible with the old version only after the old version stops.

## PostgreSQL

1. Write SQL.\
   Do not use an ORM or a query builder.
2. Write SQL key words in upper case and names in lower case (PostgreSQL manual, section 4.1.1).
3. Write each schema change as an SQL migration file.\
   Use Flyway, or the migration tool of the stack (Stack tools in `SKILL.md`).
4. Run a use case with many statements in one transaction, through a unit-of-work contract in `application`.
5. When a statement fails, roll back all of the work, also when the code catches the error.
6. Do not change a migration after it ran in any environment.\
   Write a new migration.
7. Put a statement that cannot run in a transaction (`CREATE INDEX CONCURRENTLY`) in a migration of its own.\
   Mark that migration as nontransactional in the migration tool.

## MongoDB

1. Keep one aggregate in one document.\
   Do not join collections to rebuild an aggregate.
2. Give each collection a `$jsonSchema` validator.\
   When the service does not support validators (Oracle Database API for MongoDB), validate each document in the repository code.
3. Write validators and indexes as migration scripts (migrate-mongo, Mongock, or golang-migrate).
4. Run MongoDB as a replica set, also on a developer computer.\
   A transaction across documents is possible on a replica set or a sharded cluster, not on a standalone server.
5. Write the outbox document ([messaging.md](messaging.md)) in the same transaction as the change.\
   Get a lease with one `findOneAndUpdate` on a document that has no claim or an expired claim.

## Redis or Valkey

1. Do not keep the only copy of a record in the cache.
2. Give each key an expiry time.\
   Name each key `<app>:<kind>:<id>`.
3. When the cache is not available, read from the source of truth.\
   The server MUST continue to work.
4. A lock or a counter is not a cached value.\
   When the store of a lock or a counter is not available, stop the work that uses it.\
   Send 503 or `UNAVAILABLE`.
5. Valkey is a fork of Redis with the same protocol, under the BSD license.\
   Redis 8 uses RSALv2, SSPLv1, or AGPLv3.\
   Select one with the license in mind.

## Object storage

1. Use only the S3 API.\
   Do not use features of one storage provider.
2. Let browsers and apps send and get files through presigned URLs.\
   Do not send files through the server.
3. Before you sign a URL, make sure that the user can do the action on that object.\
   Give the URL a short expiry time.\
   Set the size and the type limits in the signed request.
4. Put a new upload under a separate prefix until the server validates its type and size.\
   Then make it available.
5. Set CORS on the bucket for the origins of the web app only.
6. Use one bucket for each environment.
7. On a developer computer, use SeaweedFS (Apache 2.0) or Garage (AGPL-3.0).\
   The MinIO community edition is no longer maintained.
