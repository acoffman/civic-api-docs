---
title: CIViC API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='https://cvic.genome.wustl.edu'>Back to CIViC</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

search: true
---

# Introduction

CIViC provides a simple API that can be utilized over HTTP in the programming language of your choice or even at the command line.

The CIViC API attempts to be RESTful whenever appropriate which hopefully makes it intuitive to use. There are four main entities in the system that a user may interact with: Genes, Variants, Variant Groups, and Evidence Items. These entities form a hierarchy that is reflected in the API endpoints. A Gene has one or more Variants, each of which may have one or more Evidence Items. Variants may also be collected into Variant Groups.

**Disclaimer**: While CIViC is in beta, the API is subject to change in ways that might break existing scripts. When we officially launch, we will version the API such that breaking or non-backwards compatible changes will not not affect current users.

# Genes

For most users, the primary entry point for the CIViC API will be the Genes endpoint. This endpoint allows a user to retrieve information about what genes are in CIViC as well as get lists of variants for specific genes.

## Get a list of genes

```shell
curl "https://civic.genome.wustl.edu/api/genes"
```

> The above command returns JSON structured like this:

```json
```

This endpoint returns a listing of genes in CIViC that contain at least one evidence item. Returned gene listings contain variant ids which can be used to query for more detailed variant information.
This endpoint is *paginated* by default. You can use the `count` and `page` parameters to iterate through all the variants.

### HTTP Request

`GET https://civic.genome.wustl.edu/api/genes`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
page | 1 | Which page of results to return
count | 25 | How many genes to return on a single page


## Get details for a specific gene.

```shell
curl "https://civic.genome.wustl.edu/api/genes/ALK?identifier_type=entrez_symbol"
```

> The above command returns JSON structured like this (truncated for clarity):

```json
{
  "id":1,
  "name":"ALK",
  "entrez_id":238,
  "description":"ALK amplifications, fusions and mutations have been shown to be driving events in non-small cell lung cancer. While crizontinib has demonstrated efficacy in treating the amplification, mutations in ALK have been shown to confer resistance to current tyrosine kinase inhibitors. Second-generation TKI's have seen varied success in treating these resistant cases, and the HSP90 inhibitor 17-AAG has been shown to be cytostatic in ALK-altered cell lines.",
  "variants":[
    {
      "name":"EML4-ALK L1152R",
      "id":307,
      "evidence_items":{
        "accepted_count":1,
        "rejected_count":0,
        "submitted_count":0
      }
    },
    {
      "name":"EML4-ALK",
      "id":5,
      "evidence_items":{
        "accepted_count":3,
        "rejected_count":0,
        "submitted_count":1
      }
    },
    {
      "name":"EML4-ALK AMPLIFICATION",
      "id":170,
      "evidence_items":{
        "accepted_count":3,
        "rejected_count":0,
        "submitted_count":0
      }
    }
  ],
  "variant_groups":[],
  "aliases":[
    "NBLST3",
    "CD246"
  ],
  "sources":[
    {
      "citation":"Rossi et al., 2014, Int. J. Oncol.",
      "pubmed_id":"24889366",
      "source_url":"http://www.ncbi.nlm.nih.gov/pubmed/24889366"
    },
    {
      "citation":"Shaw et al., 2013, J. Clin. Oncol.",
      "pubmed_id":"23401436",
      "source_url":"http://www.ncbi.nlm.nih.gov/pubmed/23401436"
    }
  ]
}
```

This endpoint retrieves details about a specific gene.

Not that the default behavior of this endpoint is to use internal CIViC ids. If you want to use Entrez ids or gene symbols, you need to specify the identifier_type parameter.

### HTTP Request

`GET https://civic.genome.wustl.edum/api/genes/:id`

### URL Parameters

Parameter | Valid Values |  Description
--------- | --------- | -----------
identifier_type | `entrez_id`, `entrez_symbol`, `civic_id`  | Type of gene identifier used in your query.

# Variants

The variants endpoint allows users to enumerate all of the variants present in CIViC as well as retrieve more detailed information on a specific variant. A common use case would be to get a list of variants for a gene
using the genes endpoint and then fetching detailed information for each variant via the variants endpoint.

## Get a list of variants

```shell
curl "https://civic.genome.wustl.edu/api/variants
```

> The above command returns JSON structured like this:

```json
```

This endpoint returns a listing of variants in CIViC that contain at least one evidence item. This endpoint is *paginated* by default. You can use the `count` and `page` parameters to iterate through all the variants.

### HTTP Request

`GET https://civic.genome.wustl.edu/api/genes`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
page | 1 | Which page of results to return
count | 25 | How many variants to return on a single page


## Get details for a specific variant.

```shell
curl "https://civic.genome.wustl.edu/api/variants/8
```

> The above command returns JSON structured like this (truncated for clarity):

```json
```

This endpoint retrieves details about a specific variant, given its internal CIViC id.

### HTTP Request

`GET https://civic.genome.wustl.edum/api/variants/:id`

# Evidence Items

The evidence items endpoint allows users to enumerate all of the evidence items present in CIViC as well as retrieve more detailed information on a specific evidence item. 

## Get a list of evidence items

```shell
curl "https://civic.genome.wustl.edu/api/evidence_items
```

> The above command returns JSON structured like this:

```json
```

This endpoint returns a listing of evidence items in CIViC. This endpoint is *paginated* by default. You can use the `count` and `page` parameters to iterate through all the evidence items.

### HTTP Request

`GET https://civic.genome.wustl.edu/api/evidence_items`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
page | 1 | Which page of results to return
count | 25 | How many evidence items to return on a single page


## Get details for a specific evidence item.

```shell
curl "https://civic.genome.wustl.edu/api/evidence_items/1
```

> The above command returns JSON structured like this (truncated for clarity):

```json
```

This endpoint retrieves details about a specific evidence item, given its internal CIViC id.

### HTTP Request

`GET https://civic.genome.wustl.edum/api/evidence_items/:id`

