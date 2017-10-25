# vragen route53
---
## Waar staat NS voor in de term NS Record
+++
Name server
---
## Waar worden NS records voor gebruikt? 
+++
Om vanuit een Top level domain server door te verwijzen naar de DNS server voor een specifiek domain
---
## Wat is een A record 
+++
Een A record is een adres record .. dit is het record dat doorverwijst naar een ip adres bij een fqdn 
---
## Wat is een TTL record . 
+++
Een Time to Live record geeft aan hoe lang een A record geldig is . Dit wordt gebruikt in geval van DNS caching 
+++
Wat is de default TTL (veel voorkomende ) van de meeste a records.. 
2 dagen .
---
## Wat is een CNAME? 
+++
Een CNAME wordt gebruikt om het ene domain naar het andere te resolven 
---
## Wat is een Alias record.
+++
Een alias record is bijna gelijk aan een CNAME met het verschil dat een alias record wel naar een zone apex (naked zone) kan verwijzen en een CNAME niet (CNAME kan alleen resolven naar een A Record) 
+++
Alias records zijn uniek voor AWS en veranderen mee met wijzigingen in de AWS resources waar ze naar verwijzen 
---
## Als je binnen route53 een domain registreert welke records krijg je dan automatisch??
+++
1 soa record en 4 NS records.. 
---
## Welke routing policies kent route53??
+++
* Simple 
* Weighted
* Latency
* Failover
* Geolocation
---
## Wat zijn de karakteristieken van de verschillende routing policies
+++
Simple : een a record dat naar een endpoint (loadbalancer, webserver)  verwijst. Platte verwijzing .. geen enkele routing intelligentie
+++
Weighted : Hierbij kun je aangeven hoeveel van het verkeer naar het ene en hoeveel er naar het andere endpoint gaat ( meerdere eindpoints mogelijk) .. (wordt ook gebruikt voor AB testing)
de percentage worden op dag basis berekend. Niet per minuut 
Je hebt een apart record nodig per endpoint
+++
Latency: bij latency based routing wordt er gekeken naar de latency van de route tussen de aanvrager en de verschillende endpoints
+++
Failover: routeert in eerste instantie naar je A site en bepaald op basis van een Health check of het verkeer geswitcht moet worden naar een B site . 
+++
Geolocation: routering gebaseerd op de geografische locatie van je gebruikers . 

---
# opdracht 
+++
Maak met behulp van de tot nu toe behandelede middelen (EC2, S3, Route53.... ) een hosting oplossing voor onze tech blog 
+++
### Voorwaarden 

* 1) Het uitvallen van een regio binnen aws moeten worden overleeft. 
* 2) Pieken in verkeer moeten worden opgevangen. 
* 3) te benaderen via <yournamehere>.fredforet.nl
* 4) Niet meteen geharmend wordt .. (denk aan sec. groups, policies ed.)

+++

Over een uur gaan we de verschillende oplossingen bespreken
... tik tok tik tok .. duurt lang ... 

als je de source files van de blog nodig hebt dan hoor ik het graag
+++



