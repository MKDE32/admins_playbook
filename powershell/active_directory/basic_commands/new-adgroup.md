# EXAMPLE
```
new-adgroup -description:"this is the accounting group" -groupcategory:"security" -groupscope:"global" -path "dc=example,dc=com"-samaccountname:"accounting" -server:"dc1.example.com"
```

# FLAGS
## GROUP CATEGORY
| Value          | Purpose                                                        |
| -------------- | -------------------------------------------------------------- |
| `Security`     | ✅ Used for **permissions** (files, folders, apps, etc.)        |
| `Distribution` | 📧 Used for **email distribution lists only** (no permissions) |

## GROUP SCOPE
| Scope         | Members can come from | Can be used in | Typical Use                                       |
| ------------- | --------------------- | -------------- | ------------------------------------------------- |
| `Global`      | Same domain only      | Any domain     | 👤 Users grouped by department (e.g., Accounting) |
| `DomainLocal` | Any domain            | Same domain    | 📁 Assign permissions to resources in one domain  |
| `Universal`   | Any domain            | Any domain     | 🌍 Multi-domain environments                      |








