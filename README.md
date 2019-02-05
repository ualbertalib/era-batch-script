# era-batch-script
Google Apps script used to convert investigation documents to ingest-ready batch spreadsheets

This script is based on JavaScript and designed to meet a specific output. See batch ingest template for example.

## HEADERS

**file_name**: Only contains file name, no path directory.

**title**: Self-explanatory. 	

**alternate_title**: Assumption here is that this is used when early versions of an article use a slightly different name than the final published version.

**type**: Controlled vocabulary. Investigation validation requires one of the following:

- book
- chapter
- conference_poster
- conference_paper
- dataset
- image
- article
- learning_object
- report
- research_material
- review

**publication_status:** Leave blank unless the item is 'in-press'.

**owner_id:** Should always be '1'. 

**languages:** Controlled vocab. Use one of the following:
- english
- french
- spanish
- chinese
- german
- italian
- russian
- ukrainian
- japanese
- no_linguistic_content
- other

**creators:** List of authors, last name, comma, first initial, and pipe. (e.g. 'Cockcroft, D.|Grant, K.|Stang, M.')

**subjects:** List related subject headings or keywords, separated by a pipe "|" character. these are taken from sources in the following order: (1) the article or publisher website (2) web of knowledge or an appropriately reputable subject repository (e.g. Hein) (3) PubMed (4) U of A discovery system (Ebsco discovery).  if you are unable to locate keywords from these sources, you may leave the field blank.

**date_created:** Year published.

**description:** Abstract. If unavailable, use the first paragraph of the material.

**community_id:** Use corresponding id to name in communityList sheet (https://docs.google.com/spreadsheets/d/1ov7tu_3Lwjbp11x74i429SNtbBZIe4_u8b17E1vkCOQ/edit#gid=0).

**collection_id:** Use corresponding id to name in collectionList sheet (https://docs.google.com/spreadsheets/d/1ToxcezgwpHgA1jrklJ-mdx8LkOc6F7Mk7zAzvhIn1Ek/edit#gid=0).

**contributors:** An additional contributor could be a consortium, governmental organization, not-for-profit, funding agency (i.e. "Canadian Academic Research Libraries (CARL)")

**places:** If associated with a geographic location.

**time_periods:** If associated with a specific period of time.

**citations:**

**source**

**related_item**

**license:** Controlled vocab. Use one of the following:
- attribution_noncommercial_4_0_international
- attribution_4_0_international
- attribution_noncommercial_noderivatives_4_0_international
- attribution_noncommercial_sharealike_4_0_international
- attribution_noderivatives_4_0_international
- attribution_sharealike_4_0_international
- cc0_1_0_universal
- public_domain_mark_1_0

**license_text**

**visibility:** Controlled vocab. Use one of the following:
- public
- authenticated
- embargo

**embargo_end_date**

**visibility_after_embargo**			
