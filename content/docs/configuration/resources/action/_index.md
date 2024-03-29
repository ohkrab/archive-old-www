---
---

# Action

Action resource is a custom SQL operation that will be executed.

```hcl
action "<namespace>" "<name>" {
  arguments {
    ...
  }

  sql = "..."
}
```

- `<namespace>` - is a action namespace
- `<name>` - is a migration reference name to use when connecting to other resources
- `arguments` block (optional) - define arguments that can be used in `sql` as a variable, see [Resource arguments]({{< ref "docs/configuration/resource-arguments" >}}) for more details
- `sql` - code to be executed

## Arguments 

These attributes can be used with arguments:

- `sql`


## Example

```hcl
action "view" "refresh" {
  arguments {
    arg "name" {
      description = "Materialized view to be refreshed"
    }
  }

  sql = "REFRESH MATERIALIZED VIEW {{ .Args.name | quote_ident }}"
}
```

