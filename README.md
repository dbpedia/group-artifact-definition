# group-artifact-definition
Preliminary group/artifact definition for new fusion and new generation of release. First draft. Repo might be moved later. 

## Feedback

See below for our old structure. It was using a mix of criteria:
* technical, e.g. literals vs objects
* some names were derived from DIEF extractors (matching the scala code)

Now for next generation we are aiming to define artifacts based on use cases and therefore we are asking for input from the community (who are the users). 

## How it works
group -> used to define groups (e.g. dct:decription) and as a template for versions (e.g. dct:license ) TODO needs to be added
artifacts -> used to define artifacts. Probably needs more to generate the Version info. 
content variant: 
* for dbpedia-wikipedia-kg-snapshot we use `graph={dbpedia-org/de-dbpedia-org/fr-dbpedia-org}` 
* for dbpedia-wikidata-kg-snapshot we use graph=wikidata-dbpedia-org
Then we use `partition=$takeFromShacl` where take from shacl is either the property using the prefixed string like skos:broader like partition=skos-broader or if rdf:type then use the object like partition=skos-Concept



## Old structure
Our original artifacts of DBpedia looked like this:
```
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
