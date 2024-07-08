# Wiki Development Log

## Wiki Catalog Schema

### 2024.07.05 - DCAT2 import to wiki

**Imported DCAT properties and classes to wiki [MediaWiki:Smw_import_dcat](https://ruisdael-catalog.citg.tudelft.nl/index.php?title=MediaWiki:Smw_import_dcat)**
categories (classes):
* [Category:Dataset](https://ruisdael-catalog.citg.tudelft.nl/index.php?title=Category:Dataset)
* 
Imported properties
* dcat:contactPoint - USE - point to Agent 
* dcat:theme 
* dcat:keyword - USE? - with controlled vocabulary
* dcat:landingPage 
* dcat:temporalResolution - RESEARCH
* dcat:temporal - RESEARCH
* dcat:distribution - RESEARCH
* dcat:publisher - USE
* dcat:spatial - RESEARCH

### 2024.07.08 - Other Complementary On

### category Dataset: mandatory, recommended, optional

mandatory:
* dct:title (mandatory)
* dct:description (mandatory)

recommended:
* dcat:contactPoint -> foaf:Agent
* dcat:theme - with controlled vocabulary (include later)
* dcat:keyword - with controlled vocabulary  (include later)

optional:
* <s>adms:identifier</s> use dct:identifier instead
* dcat:landingPage (include later)
* dcat:temporalResolution (include later)
* cdt:accessRights
* dct:identifier 
* dct:publisher -> foaf:Agent
* dct:creators -> foaf:Agent
* dcat:temporal -> dct:periodOfTime
* dcat:spatial -> dct:Location
* dcat:distribution  (dont include)


### category foaf:Agent

### category dct:PeriodOfTime 

### category dct:Location


### 2024.07.08 - Other Complementary Ontology terms to import to wiki 

**Imported DCMI Metadata Terms to [MediaWiki:Smw_import_dcterms](https://ruisdael-catalog.citg.tudelft.nl/index.php?title=MediaWiki:Smw_import_dcterms)**



* foaf:Agent

To import properties:
* dct:title (mandatory)
* dct:description (mandatory)


Notes on vocabulary import:

* skos:scopeNote values can be represented by SMW [Has_property_description](https://www.semantic-mediawiki.org/wiki/Help:Special_property_Has_property_description) property
