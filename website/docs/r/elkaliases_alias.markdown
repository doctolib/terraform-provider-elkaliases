---
layout: "elkaliases"
page_title: "ElkAliases: elkaliases-alias"
sidebar_current: "docs-elkaliases-resource-elkaliases_alias"
description: |-
  Create an index template
---

# alkaliases\_index

The ``elkaliases_alias`` resource creates aliases in an index

## Usage

```hcl
resource "elkaliases_alias" "name" {
  index = "name"

  alias {
    name = "test"
    filter = jsonencode({
      "match" = {
        "event.dataset" = "test"
      }
    })
  }

  alias {
    name = "name"
  }
}
```

## Argument Reference

* `index` - (Required) Index or data stream in which create the aliases.
* `alias` - (Required) Alias to create in the index or data stream.
  * `name` - (Required) Name of the alias.
  * `filter` - (Optional) Filter to apply to the alias.
