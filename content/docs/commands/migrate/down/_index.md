---
title: down
---

# Migrate down

The `migrate down` command rollbacks selected migration.
After successful operation its ID is removed from migration table.
At the beginning of an operation advisory lock is acquired to prevent other operations to run simultaneously.

## Usage

```sh
krab migrate <set> down [version]
```

### Options

- `set` - name of the set to migrate.
- `version` - migration ID to rollback.

