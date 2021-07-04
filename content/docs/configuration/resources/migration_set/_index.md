---
---

# Migration Set

Migration Set is a collection of migrations.

```hcl
migration_set "<reference>" {
  migrations = [
    ...
  ]
}
```

- `<reference>` - migration set reference name
- `migrations` - list of [migrations]({{< ref "docs/configuration/resources/migration" >}}) references

## Example

```hcl
migration_set "private" {
  migrations = [
    migration.create_tenants
  ]
}

migration "create_tenants" {
  version = "20200628"

  up {
    sql = "CREATE TABLE tenants(name varchar PRIMARY KEY)"
  }

  down {
    sql = "DROP TABLE tenants"
  }
}
```

