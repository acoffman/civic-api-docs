# Metadata endpoints

All core CIViC entities support several metadata endpoints that allow users to view discussion, revision history, and moderation history.

These endpoints can be accessed by appending an additional path segment onto a detail view URL.
For example, to see the discussion thread for the Variant with CIViC id 5, you could access the endpoint:

`https://civicdb.org/api/variants/5/comments`

Additionally, due to the hierarchical nature of CIViC entities, you can append the type of a child entity to the detail view of a parent entity in order to view the children.

For example, you could get all of the `variants` for a specific `gene` by querying `https://civicdb.org/api/genes/:gene_id/variants`
or all the `evidence_items` for a specific `variant` at the path `https://civicdb.org/api/variants/:variant_id/evidence_items`.

### Endpoint Types
```shell
curl https://civicdb.org/api/genes/49/comments
```

```json
[
  {
    "id": 247,
    "text": "Note that there appears to be some confusion in the literature about the coordinates and nomenclature for WT1 mutations and the selection of representative transcripts.  This may stem in part from the fact that “The WT1 gene encodes numerous protein isoforms. Two translational start sites have been identified, a standard methionine and a non-AUG leucine, which adds 68 amino-terminal residues” (http://genesdev.cshlp.org/content/12/20/3217.full).  This confusion is propagated by the use of ambiguous terms \"Exon 7\" and \"Exon 9\" mutations in the literature, often used without additional information to help reduce ambiguity.  To help clarify these variants, here are some representative primer sequences used to amplify \"Exon 7\" and \"Exon 9\" of WT1 (http://www.ncbi.nlm.nih.gov/pubmed/19221039).\n\n    >7F\n    CTCCAGTGCTCACTCTCCCTC\n    >7R\n    CCTTAGCAGTGTGAGAGCCTG\n    >9F\n    GTGAGGCAGATGCAGACATTG\n    >9R\n    AGCCACGCACTATTCCTTCTC",
    "title": "",
    "created_at": "2015-09-03T00:52:11.617Z",
    "updated_at": "2015-09-03T00:52:11.617Z",
    "user": {
      "id": 15,
      "email": "malachig@gmail.com",
      "name": "Malachi Griffith",
      "last_seen_at": "2017-01-05T21:29:19.166Z",
      "username": "MalachiGriffith",
      "role": "admin",
      "avatar_url": "https://secure.gravatar.com/avatar/a4d9fc3b05d58cf3d3ba51dc30bb61d6.png?d=identicon&r=pg&s=32",
      "avatars": {
        "x128": "https://secure.gravatar.com/avatar/a4d9fc3b05d58cf3d3ba51dc30bb61d6.png?d=identicon&r=pg&s=128",
        "x64": "https://secure.gravatar.com/avatar/a4d9fc3b05d58cf3d3ba51dc30bb61d6.png?d=identicon&r=pg&s=64",
        "x32": "https://secure.gravatar.com/avatar/a4d9fc3b05d58cf3d3ba51dc30bb61d6.png?d=identicon&r=pg&s=32",
        "x14": "https://secure.gravatar.com/avatar/a4d9fc3b05d58cf3d3ba51dc30bb61d6.png?d=identicon&r=pg&s=14"
      },
      "area_of_expertise": "Research Scientist",
      "orcid": "0000-0002-6388-446X",
      "display_name": "MalachiGriffith",
      "created_at": "2015-02-26T22:25:34.692Z",
      "url": "http://genome.wustl.edu/people/individual/malachi-griffith/",
      "twitter_handle": "malachigriffith",
      "facebook_profile": null,
      "linkedin_profile": "malachigriffith",
      "bio": "Dr. Griffith is an Assistant Professor of Genetics and Assistant Director of the McDonnell Genome Institute at Washington University School of Medicine. Dr Griffith has extensive experience in the fields of genomics, bioinformatics, data mining, and cancer research. His research is focused on improving the understanding of cancer biology and the development of personalized medicine strategies for cancer using genomics and informatics technologies. The Griffith lab develops bioinformatics and statistical methods for the analysis of high throughput sequence data and identification of biomarkers for diagnostic, prognostic and drug response prediction. The Griffith lab uses CIViC to interpret variants identified in cases examined by the WASHU Genomics Tumor Board. He is a co-creator of the CIViC resource.",
      "featured_expert": true,
      "accepted_license": null,
      "signup_complete": null
    },
    "html": "<p>Note that there appears to be some confusion in the literature about the coordinates and nomenclature for WT1 mutations and the selection of representative transcripts.  This may stem in part from the fact that “The WT1 gene encodes numerous protein isoforms. Two translational start sites have been identified, a standard methionine and a non-AUG leucine, which adds 68 amino-terminal residues” (<a href=\"http://genesdev.cshlp.org/content/12/20/3217.full\">http://genesdev.cshlp.org/content/12/20/3217.full</a>).  This confusion is propagated by the use of ambiguous terms “Exon 7” and “Exon 9” mutations in the literature, often used without additional information to help reduce ambiguity.  To help clarify these variants, here are some representative primer sequences used to amplify “Exon 7” and “Exon 9” of WT1 (<a href=\"http://www.ncbi.nlm.nih.gov/pubmed/19221039\">http://www.ncbi.nlm.nih.gov/pubmed/19221039</a>).</p>\n\n<pre><code>&gt;7F\nCTCCAGTGCTCACTCTCCCTC\n&gt;7R\nCCTTAGCAGTGTGAGAGCCTG\n&gt;9F\nGTGAGGCAGATGCAGACATTG\n&gt;9R\nAGCCACGCACTATTCCTTCTC\n</code></pre>\n"
  },
  {
    "id": 249,
    "text": "Renneville et al., 2009, Cancer (http://www.ncbi.nlm.nih.gov/pubmed/19536888)\n\n    >7F-2\n    CAGTGCTCACTCTCCCTCAA\n    >7R-2 \n    TAGCAGTGTGAGAGCCTGGA\n    >9F-2\n    TGCAGACATTGCAGGCATGGCAGG\n    >9R-2\n    GCACTATTCCTTCTCTCAACTGAG-3′\n\nVirappane et al., 2008, J. Clin. Oncol. (http://www.ncbi.nlm.nih.gov/pubmed/18591546)\n\n    >7F-3\n    GACCTACGTGAATGTTCACATG\n    >7R-3\n    ACCAACACCTGGATCAGACCT\n    >9F-3\n    TGCAGACATTGCAGGCATGGCAGG\n    >9R-3\n    GCACTATTCCTTCTCTCAACTGAG",
    "title": "",
    "created_at": "2015-09-03T01:16:55.412Z",
    "updated_at": "2015-09-03T01:16:55.412Z",
    "user": {
      "id": 15,
      "email": "malachig@gmail.com",
      "name": "Malachi Griffith",
      "last_seen_at": "2017-01-05T21:29:19.166Z",
      "username": "MalachiGriffith",
      "role": "admin",
      "avatar_url": "https://secure.gravatar.com/avatar/a4d9fc3b05d58cf3d3ba51dc30bb61d6.png?d=identicon&r=pg&s=32",
      "avatars": {
        "x128": "https://secure.gravatar.com/avatar/a4d9fc3b05d58cf3d3ba51dc30bb61d6.png?d=identicon&r=pg&s=128",
        "x64": "https://secure.gravatar.com/avatar/a4d9fc3b05d58cf3d3ba51dc30bb61d6.png?d=identicon&r=pg&s=64",
        "x32": "https://secure.gravatar.com/avatar/a4d9fc3b05d58cf3d3ba51dc30bb61d6.png?d=identicon&r=pg&s=32",
        "x14": "https://secure.gravatar.com/avatar/a4d9fc3b05d58cf3d3ba51dc30bb61d6.png?d=identicon&r=pg&s=14"
      },
      "area_of_expertise": "Research Scientist",
      "orcid": "0000-0002-6388-446X",
      "display_name": "MalachiGriffith",
      "created_at": "2015-02-26T22:25:34.692Z",
      "url": "http://genome.wustl.edu/people/individual/malachi-griffith/",
      "twitter_handle": "malachigriffith",
      "facebook_profile": null,
      "linkedin_profile": "malachigriffith",
      "bio": "Dr. Griffith is an Assistant Professor of Genetics and Assistant Director of the McDonnell Genome Institute at Washington University School of Medicine. Dr Griffith has extensive experience in the fields of genomics, bioinformatics, data mining, and cancer research. His research is focused on improving the understanding of cancer biology and the development of personalized medicine strategies for cancer using genomics and informatics technologies. The Griffith lab develops bioinformatics and statistical methods for the analysis of high throughput sequence data and identification of biomarkers for diagnostic, prognostic and drug response prediction. The Griffith lab uses CIViC to interpret variants identified in cases examined by the WASHU Genomics Tumor Board. He is a co-creator of the CIViC resource.",
      "featured_expert": true,
      "accepted_license": null,
      "signup_complete": null
    },
    "html": "<p>Renneville et al., 2009, Cancer (<a href=\"http://www.ncbi.nlm.nih.gov/pubmed/19536888\">http://www.ncbi.nlm.nih.gov/pubmed/19536888</a>)</p>\n\n<pre><code>&gt;7F-2\nCAGTGCTCACTCTCCCTCAA\n&gt;7R-2 \nTAGCAGTGTGAGAGCCTGGA\n&gt;9F-2\nTGCAGACATTGCAGGCATGGCAGG\n&gt;9R-2\nGCACTATTCCTTCTCTCAACTGAG-3′\n</code></pre>\n\n<p>Virappane et al., 2008, J. Clin. Oncol. (<a href=\"http://www.ncbi.nlm.nih.gov/pubmed/18591546\">http://www.ncbi.nlm.nih.gov/pubmed/18591546</a>)</p>\n\n<pre><code>&gt;7F-3\nGACCTACGTGAATGTTCACATG\n&gt;7R-3\nACCAACACCTGGATCAGACCT\n&gt;9F-3\nTGCAGACATTGCAGGCATGGCAGG\n&gt;9R-3\nGCACTATTCCTTCTCTCAACTGAG\n</code></pre>\n"
  },
  {
    "id": 250,
    "text": "It looks like the three papers being used to obtain evidence items are possibly referring to a WT1 protein sequence that looks like this one:\nhttp://www.uniprot.org/blast/?about=P19544-1.  Renneville et al., 2009, Cancer (http://www.ncbi.nlm.nih.gov/pubmed/19536888) actually refers to P19544 and NM_024426.",
    "title": "",
    "created_at": "2015-09-03T01:33:55.202Z",
    "updated_at": "2015-09-03T01:33:55.202Z",
    "user": {
      "id": 15,
      "email": "malachig@gmail.com",
      "name": "Malachi Griffith",
      "last_seen_at": "2017-01-05T21:29:19.166Z",
      "username": "MalachiGriffith",
      "role": "admin",
      "avatar_url": "https://secure.gravatar.com/avatar/a4d9fc3b05d58cf3d3ba51dc30bb61d6.png?d=identicon&r=pg&s=32",
      "avatars": {
        "x128": "https://secure.gravatar.com/avatar/a4d9fc3b05d58cf3d3ba51dc30bb61d6.png?d=identicon&r=pg&s=128",
        "x64": "https://secure.gravatar.com/avatar/a4d9fc3b05d58cf3d3ba51dc30bb61d6.png?d=identicon&r=pg&s=64",
        "x32": "https://secure.gravatar.com/avatar/a4d9fc3b05d58cf3d3ba51dc30bb61d6.png?d=identicon&r=pg&s=32",
        "x14": "https://secure.gravatar.com/avatar/a4d9fc3b05d58cf3d3ba51dc30bb61d6.png?d=identicon&r=pg&s=14"
      },
      "area_of_expertise": "Research Scientist",
      "orcid": "0000-0002-6388-446X",
      "display_name": "MalachiGriffith",
      "created_at": "2015-02-26T22:25:34.692Z",
      "url": "http://genome.wustl.edu/people/individual/malachi-griffith/",
      "twitter_handle": "malachigriffith",
      "facebook_profile": null,
      "linkedin_profile": "malachigriffith",
      "bio": "Dr. Griffith is an Assistant Professor of Genetics and Assistant Director of the McDonnell Genome Institute at Washington University School of Medicine. Dr Griffith has extensive experience in the fields of genomics, bioinformatics, data mining, and cancer research. His research is focused on improving the understanding of cancer biology and the development of personalized medicine strategies for cancer using genomics and informatics technologies. The Griffith lab develops bioinformatics and statistical methods for the analysis of high throughput sequence data and identification of biomarkers for diagnostic, prognostic and drug response prediction. The Griffith lab uses CIViC to interpret variants identified in cases examined by the WASHU Genomics Tumor Board. He is a co-creator of the CIViC resource.",
      "featured_expert": true,
      "accepted_license": null,
      "signup_complete": null
    },
    "html": "<p>It looks like the three papers being used to obtain evidence items are possibly referring to a WT1 protein sequence that looks like this one:\n<a href=\"http://www.uniprot.org/blast/?about=P19544-1\">http://www.uniprot.org/blast/?about=P19544-1</a>.  Renneville et al., 2009, Cancer (<a href=\"http://www.ncbi.nlm.nih.gov/pubmed/19536888\">http://www.ncbi.nlm.nih.gov/pubmed/19536888</a>) actually refers to P19544 and NM_024426.</p>\n"
  }
]

```

Endpoint | Purpose | Example
--------- | ------- | -----------
`/comments` | View discussion for an entity  | /api/genes/1/comments
`/suggested_changes` | View proposed revisions for an entity | /api/genes/6/suggested_changes
`/revisions` | View the entire revision history for an entity. | /api/genes/6/revisions


### Supported endpoints for CIViC entities

CIViC Entity | Base Path | Supported Endpoints
--------- | ------- | ------- 
Genes | `/api/genes/:gene_id` | `/comments`. `/suggested_changes`, `/revisions`, `/variants`
Variants | `/api/variants/:variant_id` |`/comments`. `/suggested_changes`, `/revisions`, `/evidence_items`
Evidence Items | `/api/evidence_items/:eid` |`/comments`. `/suggested_changes`, `/revisions`
Variant Groups |`/api/variant_groups/:variant_group_id` |`/comments`. `/suggested_changes`, `/revisions`
