# Wikidata Query Service

```sparql
# wdt = wikidata truthy = property
# wd = wikidata entity = data

select ?grandeville {
  ?grandeville wdt:P31 wd:Q1549591.
} 

select ?plage {
  ?plage wdt:P31 wd:Q40080.
}

select ?plage {
  ?plage wdt:P31 wd:plage(control + space)
}

select ?plage {
  ?plage wdt:P31 wd:Q40080. # plage
  ?plage wdt:P17 wd:Q142. # france
}

select distinct ?plage ?label ?image WHERE {
  ?plage wdt:P31 wd:Q40080; 
    wdt:P17 wd:Q142;
    wdt:P18 ?image;
    rdfs:label ?label.
  FILTER(lang(?label)="fr")
}
limit 100

SELECT DISTINCT ?plage ?label ?coordinates ?location ?locationlabel ?image WHERE {
  ?plage wdt:P31 wd:Q40080;  # Instance de plage
         wdt:P17 wd:Q142;    # Située en France
         wdt:P18 ?image;     # Image associée
         wdt:P625 ?coordinates; # Coordonnées géographiques
         wdt:P131 ?location.  # Division administrative
  ?location rdfs:label ?locationlabel. # Label de la location
  ?plage rdfs:label ?label.            # Label de la plage
  
  FILTER(lang(?label) = "fr" && lang(?locationlabel) = "fr").
}
LIMIT 100

```