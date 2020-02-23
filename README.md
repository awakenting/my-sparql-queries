# my-sparql-queries
This is a collection of SPARQL queries that I tried in the Wikidata Query Service 

You can copy them and try them out directly on https://query.wikidata.org/

## Resources on SPARQL
- great tutorial with lots of examples https://www.wikidata.org/wiki/Wikidata:SPARQL_tutorial
- project which makes use of SPARQL queries to show interesting information about scientific people, topics, papers etc: https://tools.wmflabs.org/scholia
  - extra bonus: everything shown on scholia that is based on a query has a link to the underlying query, you can find it in the lower left corner of a table, bar chart etc.


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
