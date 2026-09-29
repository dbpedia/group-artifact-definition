# Group & artifact definitions

Group and artifact definitions for knowledge graph datasets published on the DBpedia Databus.

Each directory in [`datasets/`](datasets/) contains the dataset’s definitions and a README linking to its current publication.

## Definitions

Groups describe datasets and their shared metadata, such as descriptions and licenses. Artifacts describe the individual data products within a group. Where applicable, definitions also include rules for splitting data into artifacts and partitions.

### Name Resolution

Databus account, group, and artifact names are derived from the Turtle definition.

- Account/user and group are taken from the `databus:Group` IRI.
- Artifacts are taken from the objects of `rule:hasArtifact`.
- If an artifact IRI is relative, it is resolved below the group IRI.
- If an artifact IRI is already a full Databus artifact IRI, it is used directly.

The Databus base URL is not derived from the account/user. It is provided by the consuming application or deployment environment, so the same definition can be used with different Databus instances during development, testing, or production publishing.

## DBpedia and live fusion datasets

The goal for the next generation of releases is to define artifacts around use cases. The earlier structure mixed technical criteria, such as literals versus objects, with names derived from DIEF extractors and their Scala implementations.

Community input is welcome to help shape artifacts around how people use the data.

### How it works

Groups define dataset metadata, such as `dct:description`, and serve as templates for version metadata, such as `dct:license`. Artifacts define the individual data products within each group.

The original content-variant scheme used the following graph values:

- Wikipedia snapshots (`dbpedia-wikipedia-kg-snapshot`): `graph=dbpedia-org`, `graph=de-dbpedia-org`, `graph=fr-dbpedia-org`, etc.
- Wikidata snapshots (`dbpedia-wikidata-kg-snapshot`): `graph=wikidata-dbpedia-org`.

The `partition` value is derived from the SHACL definition: use the prefixed property name with the colon replaced by a hyphen (for example, `skos:broader` becomes `partition=skos-broader`). For `rdf:type`, use the object’s prefixed name instead (for example, `skos:Concept` becomes `partition=skos-Concept`).

### Original artifact structure

The earlier DBpedia releases used these artifacts:

```text
geo-coordinates-mappingbased
instance-types
Mappingbased-literals  (dbo)
Mappingbased-objects (dbo)
Specific-mappingbased-properties
anchor-text
article-templates
categories
citations
commons-sameas-links
disambiguations
wikipedia-links
infobox-property-definitions
page
persondata
infobox-properties
interlanguage-links
redirects
wikilinks
homepages
images
geo-coordinates
external-links
labels
revisions
topical-concepts
```

## Feedback

Artifact definitions aim to support concrete use cases. Suggestions and feedback are welcome through [GitHub issues](https://github.com/dbpedia/group-artifact-definition/issues).
