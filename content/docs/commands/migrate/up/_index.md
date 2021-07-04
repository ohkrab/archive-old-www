---
title: up
---

# Migrate up

The `migrate up` command migrates all pending migration for a given migration set.

After successful migration its `version` is put into database migration table (by default `schema_migrations`).
At the beginning of an operation advisory lock is acquired to prevent other migrations to run simultaneously.

{{<hint>}}
💡 Migrations are executed in the order defined by migration set, NOT lexicographically.
<br>
💡 When migration table does not exist it will be created
{{</hint>}}


## Usage

```sh
krab migrate up [set]
```

### Options

- `set` - name of the set to migrate.

## Example

For `default` [migration set]({{< ref "docs/configuration/resources/migration_set" >}}) you would use:

```sh
krab migrate up default
```

