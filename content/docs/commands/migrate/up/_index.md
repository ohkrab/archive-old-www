---
title: up
---

# Migrate up

The `migrate up` command migrates all pending migration for a given migration set.
After successful migration its ID is put into database migration table (by default `schema_migrations`).
When migration table does not exist it will be created.
At the beginning of an operation advisory lock is acquired to prevent other migrations to run simultaneously.

## Usage

```sh
krab migrate <set> up
```

### Options

- `set` - name of the set to migrate.

