---
layout: "elkaliases"
page_title: "Provider: Elkaliases"
sidebar_current: "docs-elkaliases-index"
description: |-
  A provider for ElkAliases Server.
---

# ElkAliases Provider

The ElkAliases provider gives the ability to add aliases to index and data-stream to a ElasticSearch server

With the current provider from elasticstack, the only place where it is possible to declare aliases is in the index template creation.
This approach doesn't allow us to add aliases to indexes that are already created, since the template is used only at the creation of a new index and doesn't apply to already existing ones.
To solve this problem, we have created this provider, which enables you through the `elkaliases_index_aliases` resource to add aliases to existing indices.

Use the navigation to the left to read about the available resources.

## Usage

```hcl
provider "elkaliases" {
  url   = "http://localhost:9200"
  token = "token"
}
```

### Environment Variables
Provider settings can be specified via environment variables as follows:

```shell
export ELASTICSEARCH_ENDPOINT=http://localhost:9200
export ELASTICSEARCH_API_KEY=token
```

## Argument Reference

The following arguments are supported:

* `url` - (Required) Url to the ElasticSsearch API
* `token` - (Required) Authentication token to the ElasticSearch API
* `insecure` - (Optional) Skip server certification verification
