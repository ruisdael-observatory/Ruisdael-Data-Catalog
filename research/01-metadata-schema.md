# Finding a Schema for the Ruisdael Data Catalog

Andre Castro, 2024.06.27


In order to build a data catalog we need to decide upon what terms and schema we will use to describe the catalog resources, mainly the datasets.

I see two possible options

## A: [Data Catalog Vocabulary DCAT](https://www.w3.org/TR/vocab-dcat-3/)  & [DCAT-AP Application Profile](https://semiceu.github.io/DCAT-AP/releases/3.0.0/)

* 👍  recommended by Dutch and EU organizations( see https://data.overheid.nl/en/ondersteuning/open-data/dcat  https://op.europa.eu/nl/web/eu-vocabularies/dcat-ap) 

### [Data Catalog Vocabulary DCAT](https://www.w3.org/TR/vocab-dcat-3/) 

#### Most relevant DCAT classes  (for our data catalog context) : 
* [dcat:Dataset](https://www.w3.org/TR/vocab-dcat-3/#Class:Dataset)
*  (implied) [dcat:Catalog](https://www.w3.org/TR/vocab-dcat-3/#Class:Catalog) is collections of metadata about datasets, data services, or other resource types
* * possibly: 
     * [dcat:Distribution](https://www.w3.org/TR/vocab-dcat-3/#Class:Distribution) *represents an accessible form of a dataset such as a downloadable file.*  for representing dataset assets such as files
     * [dcat:DataService](https://www.w3.org/TR/vocab-dcat-3/#Class:Data_Service) *represents a collection of operations accessible through an interface (API) that provide access to one or more datasets or data processing functions.*


### [DCAT-AP Application Profile](https://semiceu.github.io/DCAT-AP/releases/3.0.0/)

> the prime objective of the Application Profile is to enhance data findability and promote reusability. To achieve this goal, datasets should be coherently documented. To enable this, the Application Profile considers several essential aspects, including among others:
>
>    Understanding the data or service structure, and how to get access to the data
>    Information on scope or purpose of the data
>   Legal information
>   Knowledge on data publishers, and any other agents involved
>   Knowledge of data availability and change policies


an application that provides metadata MUST (relevant items for Ruisdael catalog):

(@andrecastro0o Bold - most relevant)
>    Provide a description of the **Catalogue**, including at least the mandatory properties specified for the class [Catalogue](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#Catalogue).
>     Provide descriptions of **Datasets** in the Catalogue, including at least the mandatory properties for the class [Dataset](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#Dataset).
>     Provide descriptions of Distributions, if any, of Datasets in the Catalogue, including at least the mandatory properties for the class [Distribution](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#Distribution).
>     Provide descriptions of Data Services, if any, of Datasets in the Catalogue, including at least the mandatory properties for the class [Data Service](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#DataService).
>     Provide descriptions of all organisations involved in the descriptions of Catalogue and Datasets, including at least the mandatory properties for the class [Agent](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#Agent).

### DCAT-AP Main entities: core classes and properties (mandatory/recommend)
Classes:

*  [Agent](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#Agent) - person or organization
    * mandatory: [name](http://xmlns.com/foaf/0.1/name)
    * mandatory: [type](http://purl.org/dc/terms/type)  	The nature of the agent. - **Use: CV**   
*  [Catalogue](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#Catalogue) 
    * 
*  [Dataset](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#Dataset) |
    * mandatory: [description](https://www.w3.org/TR/vocab-dcat-3/#Property:resource_description)
    * mandatory: [title](https://www.w3.org/TR/vocab-dcat-3/#Property:resource_title)
    * [access rights](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#Dataset.accessrights) 
    * [contact point](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#Dataset.contactpoint)
    * [creator](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#Dataset.creator) ,
    * [dataset distribution](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#Dataset.datasetdistribution) , 
    * [description](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#Dataset.description) ,
    *  [documentation](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#Dataset.documentation) ,
    *  [geographical coverage](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#Dataset.geographicalcoverage) We might need to use instances of Geometry 
       * For an extensive geometry (i.e., a set of coordinates denoting the vertices of the relevant geographic area), the property [locn:geometry](https://www.w3.org/TR/vocab-dcat-3/#Property:location_geometry) [[LOCN](https://www.w3.org/TR/vocab-dcat-3/#bib-locn)] SHOULD be used.
       * For a geographic bounding box delimiting a spatial area the property [dcat:bbox](https://www.w3.org/TR/vocab-dcat-3/#Property:location_bbox) SHOULD be used.
       * For the geographic center of a spatial area, or another characteristic point, the property [dcat:centroid](https://www.w3.org/TR/vocab-dcat-3/#Property:location_centroid) SHOULD be used.
    *  [identifier](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#Dataset.identifier) 
    *  [landing page](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#Dataset.landingpage) ,
    * ? [provenance](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#Dataset.provenance) , [publisher](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#Dataset.publisher)
    *  ?[release date](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#Dataset.releasedate) , [sample](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#Dataset.sample) , 
    * ?[source](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#Dataset.source) , [spatial resolution](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#Dataset.spatialresolution) , 
    * [temporal coverage](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#Dataset.temporalcoverage) ,
        * [Property:period_start_date](https://www.w3.org/TR/vocab-dcat-3/#Property:period_start_date  )
    * [temporal resolution](https://www.w3.org/TR/vocab-dcat-3/#Property:dataset_temporal_resolution) , 
    * [title](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#Dataset.title) , 
    * [type](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#Dataset.type) , 


**Geolocation properties denoting a geo-point lat,lon,alt, or polygons,  might need to include: *what properties to use for those?***



![DCAT-AP diagram](https://semiceu.github.io/DCAT-AP/releases/3.0.0/html/overview.jpg)

### controlled vocs for DCAT properties
See https://semiceu.github.io/DCAT-AP/releases/3.0.0/#controlled-vocabularies-to-be-used 

## B: [DataCite Metadata Schema](https://datacite-metadata-schema.readthedocs.io/en/4.5/)
* 👎  mixes terms and schema under 1 single XML (👎 👎 ) representation
   * Q: isn't there a JSON/JSON-ld representation of the schema? 
* 👎   does not differentiate between classes and properties (that's not how RDF based schemas or SMW(wiki) works)
  
See DataCite Mandatory Properties[](https://datacite-metadata-schema.readthedocs.io/en/4.5/properties/overview/#table-1-datacite-mandatory-properties) and compare to DCAT-AP classes + properties