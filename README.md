# era-batch-script
Google Apps script used to convert investigation documents to ingest-ready batch spreadsheets

This script is based on JavaScript and designed to meet a specific output. See batch ingest template for example. The headers listed below only include those needed to be passed from the investigation sheet to the manifest for ingest. Many fields exist in the investigation spreadsheet only to aid the investigatory process.

XSL templates are stored here only for backup purposes, and are not updated. They contain the correct headers + all the validations.

Always refer to the [Google Apps Script documentation](https://developers.google.com/apps-script/) when attempting to fix an issue. Many of the bugs present are a result of language updates.

## MANIFEST HEADERS

This section outlines the correct output to be found in the batch manifest. Much of the work is already done by the investigation script, the following provides the necessary information to fix bugs or to manually add items to a manifest.

**file_name**: Only contains file name, no path directory.

**title**: Self-explanatory. 	

**alternate_title**: Assumption here is that this is used when early versions of an article use a slightly different name than the final published version.

**type**: Controlled vocabulary. Investigation validation requires one of the following:

- book
- chapter
- conference_workshop_poster
- conference_workshop_presentation
- dataset
- image
- article
- learning_object
- report
- research_material
- review

**publication_status:** Controlled vocab. Use one of the following for articles only:
- draft
- published
- submitted

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

**creators:** List of authors, last name, comma, full first name, and pipe. (e.g. 'Cockcroft, Daniel|Grant, Kaitlyn|Stang, Michaela')

**subjects:** List related subject headings or keywords, separated by a pipe "|" character. these are taken from sources in the following order: (1) the article or publisher website (2) web of knowledge or an appropriately reputable subject repository (e.g. Hein) (3) PubMed (4) U of A discovery system (Ebsco discovery).  if you are unable to locate keywords from these sources, you may leave the field blank.

**date_created:** Year published.

**description:** Abstract. If unavailable, use the first paragraph of the material.

**community_id:** Use corresponding id to name in [communityList sheet](https://docs.google.com/spreadsheets/d/1ov7tu_3Lwjbp11x74i429SNtbBZIe4_u8b17E1vkCOQ/edit#gid=0). MANDATORY FIELD

**collection_id:** Use corresponding id to name in [collectionList sheet](https://docs.google.com/spreadsheets/d/1ToxcezgwpHgA1jrklJ-mdx8LkOc6F7Mk7zAzvhIn1Ek/edit#gid=0). MANDATORY FIELD

**contributors:** An additional contributor could be a consortium, governmental organization, not-for-profit, funding agency (i.e. "Canadian Academic Research Libraries (CARL)")

**places:** If associated with a geographic location.

**time_periods:** If associated with a specific period of time.

**citations:** Full APA citation of item, including DOI.

**source:** "The described resource may be derived from the related resource in whole or in part." This likely refers to chapters drawn from a book, etc.

**related_item:** This field should contain the DOI for the original publication. 

**license:** Controlled vocab. Use one of the following:
- attribution_noncommercial_4_0_international
- attribution_4_0_international
- attribution_noncommercial_noderivatives_4_0_international
- attribution_noncommercial_sharealike_4_0_international
- attribution_noderivatives_4_0_international
- attribution_sharealike_4_0_international
- cc0_1_0_universal
- public_domain_mark_1_0

**license_text:** Used for when users need a customized rights statement other than the CC licenses provided.

**visibility:** Controlled vocab. If an item is/was embargoed, mark it as so. In the rare case that it should have CCID protection, use 'authenticated'. 
- public
- authenticated
- embargo

**embargo_end_date:** Fill this field only if the visibility is set to 'embargo'. If visibility is set to 'public', this field should be empty. Using the latest publication date available, add the embargo period to calculate when the item is set to become available. Although the investigation script should not allow you to input dates any other way, ensure that the format is YYYY/MM/DD.

**visibility_after_embargo:** Controlled vocab; controls whether or not the public is able to see the item after the embargo period has ended. This field should not be filled if the item is not embargoed. Should be one of the following:
- public
- private

## LINKS

Edit with caution. Access master script by clicking Tools>Script Editor.

[individualInvestigationTemplate](https://docs.google.com/spreadsheets/d/14csVDxJj_Vx3VxVxtihEwnNE45zlZIh9lRn_oTi7DCI/edit#gid=0)

[groupInvestigationTemplate](https://docs.google.com/spreadsheets/d/1Un4hGETy6WxVOpsMtr30tPDG2usAXFVXloIaFLoHO2E/edit#gid=0)

[postprintDepositTemplate](https://docs.google.com/spreadsheets/d/1N-rSnQgCpWYYqAjvRZVFRmcSwY4vtGYhXAHqzUCmB0Y/edit#gid=0)

[collectionList](https://docs.google.com/spreadsheets/d/1ToxcezgwpHgA1jrklJ-mdx8LkOc6F7Mk7zAzvhIn1Ek/edit#gid=0)

[communityList](https://docs.google.com/spreadsheets/d/1ov7tu_3Lwjbp11x74i429SNtbBZIe4_u8b17E1vkCOQ/edit#gid=0)

[batch ingest template](https://docs.google.com/spreadsheets/d/178o_-ZEV3Ii-IzJ0AcJQTQqFsH3Ew2WCgyj2aZw99iY/edit#gid=0)


## FURTHER DOCUMENTATION

[ERA Wiki](https://sites.google.com/a/ualberta.ca/era-mediated-deposit/)

[Jupiter Controlled Vocabularies](https://github.com/ualbertalib/jupiter/tree/master/config/controlled_vocabularies)
