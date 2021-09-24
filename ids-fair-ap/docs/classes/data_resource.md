# Data Resource

The following properties SHOULD be used as properties for the [DataResource](https://international-data-spaces-association.github.io/InformationModel/docs/index.html#DataResource) class.



| Prefix | Namespace | 
| - | - | 
| `ids` | `https://w3id.org/idsa/core` | 
| `idsf` | `https://w3id.org/idsa/ap/fair` |   
| `adms` | `https://www.w3.org/ns/adms#` |   
| `dct` | `http://purl.org/dc/terms/` |
| `dcat` | `http://www.w3.org/ns/dcat#` |    
| `foaf` | `http://xmlns.com/foaf/0.1/` |   
| `rdfs` | `http://www.w3.org/2000/01/rdf-schema#` |   
| `vcard` | `http://www.w3.org/2006/vcard/ns#` |
| `xsd` | `http://www.w3.org/2001/XMLSchema#` |


## PID

Persistent identifier of the research artifact.

| URI | Range | Card | 
| - | - | - |
| `adms:identifier` | `adms:Identifier` | `1..n` |  


The identifier MUST be typed with the [DataCite ResourceIdentifierScheme](http://purl.org/spar/datacite/ResourceIdentifierScheme).


**RDF Example**

=== "Turtle"
    ```SPARQL
    <https://internationaldataspaces.org/DataResource/example-artifact>
        a ids:DataResource ;
        adms:identifier [ 
            a adms:Identifier ;
            skos:notation "http://www.doi.org/123456789"^^<http://purl.org/spar/datacite/doi> ;
            rdfs:label "DOI Identifier" 
            ] .
    ```

## License 

License of the research artifact. 

| URI | Range | Card | 
| - | - | - |
| `dct:license` | `dct:LicenseDocument` | `0..1` |  

The [SPDX License List](https://github.com/spdx/license-list-data/tree/master/rdfturtle) MUST be used.

**RDF Example**

=== "Turtle"
    ```SPARQL
    <https://internationaldataspaces.org/DataResource/example-artifact>
        a ids:DataResource ;
        dct:license <http://spdx.org/licenses/MIT-0> .
    ```

## Publisher

Publisher of the research artifact.

| URI | Range | Card | 
| - | - | - |
| `dct:publisher` | `foaf:Agent` | `1..n` |  

**RDF Example**

=== "Turtle"
    ```SPARQL
    <https://internationaldataspaces.org/DataResource/example-artifact>
        a ids:DataResource ;
        dct:publisher [ 
            a foaf:Organization ;
            foaf:homepage "https://examplepublisher.eu" ;
            foaf:name "Example Publisher Ltd."
            ] .
    ```

## Author

Corresponding authors of the research artifact.

| URI | Range | Card | 
| - | - | - |
| `dct:creator` | `vcard:Kind` | `1..n` |  


**RDF Example**

=== "Turtle"
    ```SPARQL
    <https://internationaldataspaces.org/DataResource/example-artifact>
        a ids:DataResource ;
        dct:creator [ 
            a vcard:Individual ;
            vcard:fn "Jane Doe" ;
            vcard:organization-name "Example University"
            ] .
    ```

## Contact Point

Additional contact points or authors of the research artifact.

| URI | Range | Card | 
| - | - | - |
| `dcat:contactPoint` | `vcard:Kind` | `0..n` | 

=== "Turtle"
    ```SPARQL
    <https://internationaldataspaces.org/DataResource/example-artifact>
        a ids:DataResource ;
        dcat:contactPoint [ 
            a vcard:Individual ;
            vcard:fn "John Doe" ;
            vcard:organization-name "Example University"
            ] .
    ```



## Resource Type

Type of the research artifact.

| URI | Range | Card | 
| - | - | - |
| `dct:type` | `rdfs:Resource` | `1..1` | 

A controlled vocabulary could not been established yet.

=== "Turtle"
    ```SPARQL
    <https://internationaldataspaces.org/DataResource/example-artifact>
        a ids:DataResource ;
        dct:type <http://purl.org/dc/dcmitype/Text> .
    ```

## Title


This property contains a name given to the research artifact. 
This property MAY be repeated for parallel language versions of the name. 

| URI | Range | Card | 
| - | - | - |
| `ids:title` | `rdfs:Literal` | `1..n` |  

**RDF Examples**

=== "Turtle"
    ```SPARQL
    <https://internationaldataspaces.org/DataResource/example-artifact>
        a ids:DataResource ;
        ids:title "IDS FAIR Example Artifact"@en .
    ```
=== "JSON-LD"
    ```json-ld
    [
        {
            "@id":"https://piveau.eu/set/data/test-dataset",
            "http://purl.org/dc/terms/title": [
                {
                    "@value": "DCAT-AP 2 Example Dataset 2",
                    "@language":"en"
                }
            ]
        }
    ]
    ```


## Publication Date

Publication date of research artifact. 

| URI | Range | Card | 
| - | - | - |
| `dct:issued` | `rdfs:Literal  typed  as  xsd:date ` | `1..1` |  


=== "Turtle"
    ```SPARQL
    <https://internationaldataspaces.org/DataResource/example-artifact>
        a ids:DataResource ;
        dct:issued "2020-05-25"^^xsd:Date ;
    ```

## Modification Date

Modification date of research artifact. 

| URI | Range | Card | 
| - | - | - |
| `dct:modified` | `rdfs:Literal  typed  as  xsd:date ` | `1..1` |  

=== "Turtle"
    ```SPARQL
    <https://internationaldataspaces.org/DataResource/example-artifact>
        a ids:DataResource ;
        dct:modified "2020-05-28"^^xsd:Date ;
    ```

## Description 

This property contains a description/abstract of the research artifact. 
This property MAY be repeated for parallel language versions of the name. 

| URI | Range | Card | 
| - | - | - |
| `ids:description` | `rdfs:Literal` | `1..n` |  

**RDF Examples**

=== "Turtle"
    ```SPARQL
    <https://internationaldataspaces.org/DataResource/example-artifact>
        a ids:DataResource ;
        ids:description "Description of IDS FAIR Example Artifact"@en ;
        ids:description "Beschreibung eines IDS FAIR Example Artifact"@de .
    ```

## Keyword

Keyword, describing the research artifact.

| URI | Range | Card | 
| - | - | - |
| `dcat:keyword` | `rdfs:Literal` | `0..n` | 

=== "Turtle"
    ```SPARQL
    <https://internationaldataspaces.org/DataResource/example-artifact>
        a ids:DataResource ;
        dcat:keyword "Research"@en ;
        dcat:keyword "IDS"@en .
    ```

## Endpoint

URL to access the research artifact.

| URI | Range | Card | 
| - | - | - |
| `ids:accessURL` | `rdfs:Resource` | `1..n` |  

=== "Turtle"
    ```SPARQL
    <https://internationaldataspaces.org/DataResource/example-artifact>
        a ids:DataResource ;
        ids:accessURL <https://endpointurl.eu> .
    ```

## Data Access Level

Access level of the research artifact.

| URI | Range | Card | 
| - | - | - |
| `dct:accessRights` | `dct:RightsStatement` | `1..1` | 


The [EU Access Right Vocabulary]( https://publications.europa.eu/resource/authority/access-right) MUST be used.

=== "Turtle"
    ```SPARQL
    <https://internationaldataspaces.org/DataResource/example-artifact>
        a ids:DataResource ;
        dct:accessRights <http://publications.europa.eu/resource/authority/access-right/PUBLIC> .
    ```


## Related Resource

Link or information of related resources of the research artifact.

| URI | Range | Card | 
| - | - | - |
| `dct:relation` | `rdfs:Resource` | `0..n` | 

=== "Turtle"
    ```SPARQL
    <https://internationaldataspaces.org/DataResource/example-artifact>
        a ids:DataResource ;
        dct:relation <http://relatedresource.eu> .
    ```

## File Format

File format or media type of the research artifact.


| URI | Range | Card | 
| - | - | - |
| `dcat:mediaType` | `dct:MediaType` | `0..1` | 

A official [IANA Media Type](https://www.iana.org/assignments/media-types/media-types.xhtml) MUST be used.

=== "Turtle"
    ```SPARQL
    <https://internationaldataspaces.org/DataResource/example-artifact>
        a ids:DataResource ;
        dcat:mediaType <https://www.iana.org/assignments/media-types/application/pdf> .
    ```


## Language

The language of the research artifact.

| URI | Range | Card | 
| - | - | - |
| `dct:language` | `dct:LinguisticSystem` | `0..n` | 

Resources defined by the Library of Congress (ISO 639-1, ISO 639-2) SHOULD be used. If a ISO 639-1 (two-letter) code is defined for language, then its corresponding IRI SHOULD be used; if no ISO 639-1 code is defined, then IRI corresponding to the ISO 639-2 (three-letter) code SHOULD be used.


=== "Turtle"
    ```SPARQL
    <https://internationaldataspaces.org/DataResource/example-artifact>
        a ids:DataResource ;
        dct:language <http://id.loc.gov/vocabulary/iso639-1/en> .
    ```

## Byte Size

Byte size of the research artifact.

| URI | Range | Card | 
| - | - | - |
| `ids:byteSize` | `rdfs:Literal typed as xsd:decimal.` | `0..1` | 


=== "Turtle"
    ```SPARQL
    <https://internationaldataspaces.org/DataResource/example-artifact>
        a ids:DataResource ;
        ids:byteSize "25255"^^xsd:decimal .
    ```

## Version

Version of the research artifact.

| URI | Range | Card | 
| - | - | - |
| `ids:version` | `rdfs:Literal` | `0..1` |


=== "Turtle"
    ```SPARQL
    <https://internationaldataspaces.org/DataResource/example-artifact>
        a ids:DataResource ;
        ids:version "1.0.0" .
    ```

## Provenance

Provenance information of the research artifact.

| URI | Range | Card | 
| - | - | - |
| `dct:provenance` | `dct:ProvenanceStatement ` | `0..n` |


=== "Turtle"
    ```SPARQL
    <https://internationaldataspaces.org/DataResource/example-artifact>
        a ids:DataResource ;
        dct:provenance [ 
            a dct:ProvenanceStatement ;
            rdfs:label "This is a provenance statement"@en 
            ] .
    ```


## Data Description

Semantic description of the research artifact.

| URI | Range | Card | 
| - | - | - |
| `idsf:dataDescription` | `idsf:DataDescription` | `0..1` |

See [here](/classes/csv_file/).

