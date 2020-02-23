# my-sparql-queries
This is a collection of SPARQL queries that I tried in the Wikidata Query Service (https://query.wikidata.org/)

## Resources on SPARQL
- great tutorial with lots of examples https://www.wikidata.org/wiki/Wikidata:SPARQL_tutorial
- 


## Queries

- List of german schools with coordinates:
```SPARQL
SELECT ?school ?schoolLabel ?coordinates
WHERE {
  ?school wdt:P31/wdt:P279* wd:Q3914 .
  ?school wdt:P17 wd:Q183 .
  OPTIONAL {?school wdt:P625 ?coordinates .}
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],de" }
}
```
