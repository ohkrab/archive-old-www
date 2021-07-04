---
---

# Migration

Migration resource is a single migrate operation.

```hcl
migration "<reference>" {
  version = "<version>"

  up {
	sql = "..."
  }

  down {
	sql = "..."
  }
}
```

- `<reference>` - is a migration reference name to use when connecting to other resources
- `<version>` - name that will be used to identify migration in the database, can only be digits, alphanumeric characters and underscores
- `up` / `down` - migration direction, contains SQL code to be executed

## Example

```hcl
migration "create_tenants" {
  version = "20060102150405"

  up {
	sql = "CREATE TABLE tenants(name VARCHAR PRIMARY KEY)"
  }

  down {
	sql = "DROP TABLE tenants"
  }
}
```

