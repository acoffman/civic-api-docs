---
title: CIViC API Reference

toc_footers:
  - <a href='https://civicdb.org'>Back to CIViC</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

search: true

language_tabs:
  - shell: Request
  - json: Response

includes:
  - endpoint_types
  - genes
  - variants
  - evidence_items
  - variant_groups
  - assertions
  - linking
  - meta
---

# Introduction

CIViC provides a simple API that can be utilized over HTTP in the programming language of your choice or even at the command line.

The CIViC API attempts to be RESTful whenever appropriate which hopefully makes it intuitive to use. There are four main entities in the system that a user may interact with: Genes, Variants, Variant Groups, and Evidence Items. These entities form a hierarchy that is reflected in the API endpoints. A Gene has one or more Variants, each of which may have one or more Evidence Items. Variants may also be collected into Variant Groups.

This documentation provides example requests and responses for most endpoints. The responses are edited for brevity, but should include instances of each top level key for reference. You can toggle between viewing a request and its corresponding response using the tabs on the right of the page.

