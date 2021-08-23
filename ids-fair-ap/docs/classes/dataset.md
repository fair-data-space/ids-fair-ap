# Dataset

## Title

This property contains a name given to the Dataset. This property can be repeated for parallel language versions of the name. 

| URI | Range | Card | 
| - | - | - |
| `dct:title` | `rdfs:Literal` | `1..n` |  

**RDF Examples**

=== "Turtle"
    ```SPARQL
    @prefix dct: <http://purl.org/dc/terms/> .

    <https://piveau.eu/set/data/test-dataset>
        dct:title "DCAT-AP 2 Example Dataset 2"@en .

    ```
=== "RDF/XML"
    ```xml
    <rdf:RDF xmlns:dct="http://purl.org/dc/terms/">
        <rdf:Description rdf:about="https://piveau.eu/set/data/test-dataset">
            <dct:title xml:lang="en">DCAT-AP 2 Example Dataset 2</dct:title>
        </rdf:Description>
    </rdf:RDF>
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
=== "N-Triples"
    ```SPARQL
    <https://piveau.eu/set/data/test-dataset> <http://purl.org/dc/terms/title> "DCAT-AP 2 Example Dataset 2"@en .
    ```

!!! tip "Frontend Representation"
    DCAT-AP 2 Example Dataset 2


## Spatial / Geographical Coverage