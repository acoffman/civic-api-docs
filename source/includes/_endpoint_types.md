# Endpoint Types

The API for consuming CIViC data can mostly be broken down into two different types of endpoints:
**index** and **detail**.

## Index

> Example of a meta section for the genes index endpoint

```shell
curl https://civic.genome.wustl.edu/api/genes
```

```json
{
  "_meta": {
    "current_page": 2,
      "per_page": "25",
      "total_pages": 11,
      "total_count": 266,
      "links": {
        "next": "https://civic.genome.wustl.edu/api/genes?count=25&page=3",
        "previous": "https://civic.genome.wustl.edu/api/genes?count=25&page=1"
      }
   }
}
```

The index endpoints provide high level overview information about a collection of entities all at once and allow a user to page through all the entities in the system.
Index endpoints provide two top-level keys in their JSON structure: `_meta` and `records`.

**Meta**

As seen to the right, the `_meta` section contains information about the total number of available records, the page size, and provides links to the `next` and `previous` page of results.
These links can be used to easily traverse all of the records in CIViC. A `null` entry for `next` (or `previous`) indicates that you have reached the end of the collection.

**Records**

The `records` section will contain the actual objects requested in the API call (ie: `genes`, `variants` or `evidence_items`)

If you do not wish to use the links in the `_meta` section, index endpoints also accept manual pagination parameters in the query string:

Parameter | Default | Description
--------- | ------- | -----------
page | 1 | Which page of results to return
count | 25 | How many records to return on a single page

## Detail

> Example of a detail response for the genes endpoint

```shell
curl https://civic.genome.wustl.edu/api/genes/19
```

```json
{
  "id": 19,
  "name": "EGFR",
  "entrez_id": 1956,
  "description": "EGFR is widely recognized for its importance in cancer. Amplification and mutations have been shown to be driving events in many cancer types. Its role in non-small cell lung cancer, glioblastoma and basal-like breast cancers has spurred many research and drug development efforts. Tyrosine kinase inhibitors have shown efficacy in EGFR amplfied tumors, most notably gefitinib and erlotinib. Mutations in EGFR have been shown to confer resistance to these drugs, particularly the variant T790M, which has been functionally characterized as a resistance marker for both of these drugs. The later generation TKI's have seen some success in treating these resistant cases, and targeted sequencing of the EGFR locus has become a common practice in treatment of non-small cell lung cancer. \nOverproduction of ligands is another possible mechanism of activation of EGFR. ERBB ligands include EGF, TGF-a, AREG, EPG, BTC, HB-EGF, EPR and NRG1-4 (for detailed information please refer to the respective ligand section). In ligand-activated cancers, Cetuximab appears to be more effective than tyrosine-kinase inhibitors (Arteaga et. al.).",
  "variants": [
    {
      "name": "S492R",
      "id": 453,
      "evidence_items": {
        "accepted_count": 4,
        "rejected_count": 0,
        "submitted_count": 0
      }
    },
    {
      "name": "3' UTR MUTATION",
      "id": 253,
      "evidence_items": {
        "accepted_count": 0,
        "rejected_count": 1,
        "submitted_count": 0
      }
    },
    {
      "name": "K467T",
      "id": 455,
      "evidence_items": {
        "accepted_count": 2,
        "rejected_count": 0,
        "submitted_count": 0
      }
    }
  ],
  "aliases": [
    "HER1",
    "ERBB1",
    "ERBB"
  ],
  "type": "gene",
  "variant_groups": [
    {
      "id": 12,
      "name": "EGFR TKI Resistance",
      "description": "EGFR pathway activation is a nearly ubiquitous hallmark of cancer. Many tyrosine kinase inhibitors have been developed to target EGFR pathway activity. One such inhibitor, erlotinib, has demonstrated efficacy in an EGFR over-active setting. However, the T790M missense mutation has shown to confer resistance to this inhibitor in cell lines and case studies.  ",
      "variants": [
        {
          "id": 34,
          "entrez_name": "EGFR",
          "gene_id": 19,
          "entrez_id": 1956,
          "name": "T790M",
          "description": "EGFR T790M was one of the very first mutations recognized to confer resistance to targeted therapies in non-small cell lung cancer. While successful in amplified EGFR, the efficacy of the first and second generation TKI's (erlotinib, gefitinib, neratinib) in treating patients harboring this mutation before treatment is notably lower. This lack of efficacy can likely be to blame for the poorer prognosis for patients with this mutation as compared to patients with wildtype EGFR or other types of EGFR mutations. Approximately half of EGFR mutant tumors with acquired resistance to TKI inhibition have been shown to harbor this mutation, implicating it as a mechanism of acquired therapy resistence. A third generation TKI (osimertinib) has been approved for the treatment of EGFR T790M mutant NSCLC. Patients positive for T790M in a plasma-based test have similar outcomes like those with tumor biopsy testing.",
          "type": "variant",
          "variant_types": [
            {
              "id": 47,
              "name": "missense_variant",
              "display_name": "Missense Variant",
              "so_id": "SO:0001583",
              "description": "A sequence variant, that changes one or more bases, resulting in a different amino acid sequence but where the length is preserved.",
              "url": "http://www.sequenceontology.org/browser/current_svn/term/SO:0001583"
            }
          ],
          "evidence_items": {
            "accepted_count": 19,
            "rejected_count": 0,
            "submitted_count": 1
          },
          "coordinates": {
            "chromosome": "7",
            "start": "55249071",
            "stop": "55249071",
            "reference_bases": "C",
            "variant_bases": "T",
            "representative_transcript": "ENST00000275493.2",
            "chromosome2": null,
            "start2": null,
            "stop2": null,
            "representative_transcript2": null,
            "ensembl_version": 75,
            "reference_build": "GRCh37"
          }
        }
      ],
      "type": "variant_group"
    }
  ],
  "lifecycle_actions": {
    "last_modified": {
      "order": 0,
      "timestamp": "2016-01-07T09:04:18.614Z",
      "user": {
        "id": 100,
        "email": "damian.rieke@charite.de",
        "name": "Damian Rieke",
        "last_seen_at": "2016-12-12T13:23:11.578Z",
        "username": "DTRieke",
        "role": "editor",
        "avatar_url": "https://secure.gravatar.com/avatar/baaffa3938cc82f434ca5561e34d3de9.png?d=identicon&r=pg&s=32",
        "avatars": {
          "x128": "https://secure.gravatar.com/avatar/baaffa3938cc82f434ca5561e34d3de9.png?d=identicon&r=pg&s=128",
          "x64": "https://secure.gravatar.com/avatar/baaffa3938cc82f434ca5561e34d3de9.png?d=identicon&r=pg&s=64",
          "x32": "https://secure.gravatar.com/avatar/baaffa3938cc82f434ca5561e34d3de9.png?d=identicon&r=pg&s=32",
          "x14": "https://secure.gravatar.com/avatar/baaffa3938cc82f434ca5561e34d3de9.png?d=identicon&r=pg&s=14"
        },
        "area_of_expertise": "Clinical Scientist",
        "orcid": "0000-0003-0027-7977",
        "display_name": "DTRieke",
        "created_at": "2015-12-14T08:37:49.264Z",
        "url": "",
        "twitter_handle": null,
        "facebook_profile": null,
        "linkedin_profile": null,
        "bio": null,
        "featured_expert": false,
        "accepted_license": null,
        "signup_complete": null
      }
    },
  },
  "sources": [
    {
      "id": 26,
      "name": "Epidermal growth factor receptor targeting in cancer: a review of trends and strategies.",
      "citation": "Yewale et al., 2013, Biomaterials",
      "pubmed_id": "23953842",
      "source_url": "http://www.ncbi.nlm.nih.gov/pubmed/23953842",
      "open_access": null,
      "pmc_id": null,
      "publication_date": {
        "year": 2013,
        "month": 11
      },
      "journal": "Biomaterials",
      "full_journal_title": "Biomaterials",
      "status": "fully curated"
    },
  ],
  "errors": {}
}
```

Detail endpoints return the full CIViC record for a single entity, specified explicitly by id.
In addition to the high level overview information returned by the index endpoint, this complete record will include information about data provenance, timestamps, and secondary relationships.
Unlike the index endpoints, detail endpoints do not have separate `_meta` and `records` sections as only a single record is returned.
