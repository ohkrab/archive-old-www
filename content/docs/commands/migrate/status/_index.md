---
title: status
---

# Migrate status

The `migrate status` command displays currently applied/pending migrations.

## Usage

```sh
krab migrate status [set]
```

### Options

- `set` - name of the set to migrate.

### Example output

```sh
krab migrate status animals

✔ v1 create_animals
✔ v2 create_animals_view
- v3 seed_animals
```

