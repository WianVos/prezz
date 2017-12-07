# vragen Databases
---
## Welke database varianten zijn er binnen Amazon RDS

+++
* SQL server
* Oracle
* MySql
* Postgresql
* aurora
* MariaDB

---
## Welke Vijf diensten zijn er binnen het AWS database aanbod
+++
* OLTP: RDS
* OLAP: REDSHIFT
* NoSql: Dynamodb
* Caching: Elasticache
* DMS: Database Migration Services

---
## Welke twee versies van Elasticache zijn er 

+++
* Redis
* Memcached
---

## Was is DMS
+++
Database Migration service
---
## Welke dienst gebruik je voor OLTP
+++
Amazon RDS een een of andere vorm

---
## Wat is RedShift
+++
Datawharehousing 
---
## Welke database service schaalt on the fly?

+++
DynamoDB

---
## wat is het verschil tussen automated and snapshot backups binnen RDS
+++
Automated backups geven een point in time restore mogenlijkheid en zijn verbonden aan de database 
Snapshots niet deze zijn gebruiker geinstantieerd en blijven bewaard nadat de database al weg is .  
---
## Welke twee modi kent DynamoDB
+++
* document
* key/value

---
## welke twee read policies zijn er binnen DynamoDB
+++
* eventually consitent
* Strong consistantcy

---
## Wat is Redshift
+++
Amazon AWS datawharehousing oplossing (OLAP)
---

## Hoe groot kan redshift worden ? 

+++
160 GB per node. 128 Nodes 
---
## wat zijn de drie hoofd kenmerken van Redshift
+++
* Columnar data storage
* Advanced compression
* MPP; Massively Parallel Processing


---
## is Redshift Highly available?
+++
Nee. Redshift is gebonden aan 1 availability zone

---
## wat doet elasticache?
+++
 Elasticache cached veel bevraagde data in in-memory cache waardoor het de database ontlast
---
## Wat is aurora
+++
Aurora is een mysql compatible database service 
---
## welke twee replica varianten zijn er mbt aurora
+++
* aurora read replicas
* mysql read replicas
---
## wat zijn de scaling parameters van aurora db
+++
min 10GB max 64TB
max 32vCPUs en 244GB memory
---
## hoeveel copieen van je data krijg je standaard voor een aurora db ? 
+++
minimaal 6 . 
2 copieen per az 3 az's minimaal 
---
## waar staat SQS voor? 
+++
Simple Queing Service
+++
Wat is het ? 
+++ 
Een online message Queue
---
## Welke typen queues zijn er binnen sqs
+++
* standard queue's 
* Fifo queue's
---
## Waar staat SWF voor
+++
Simple workflow service 
---
## wat is sns
+++
Simple notification service . is een webservice die developers in staat stelt om gebruikers berichten te sturen
---
## Wat doet elastic transcoder
+++
video omzetten van het ene naar het andere format
---
## Wat doet API Gateway
+++
Api gateway is in staat om als een aanspreekpunt te dienen voor meerdere achterliggende api's. 

---
## Welke drie kinesis diensten zijn er ? 
+++
* Streams
* FireHose
* Analytics
---
## what does Kinesis streams do ? 
+++
slaat inkomede streaming data op (voor een korte periode) en wacht op consumers om de data op te halen
---
## wat is een shard mbt. kinesis
+++
Shards zijn units binnen streams die data aannemen . Het aantal shards binnen je setup bepaalt de capaciteit van de stream. 
---
## wat zijn de afgifte opties voor Kinesis Firehose?
+++
* s3 bucket storage 
* Amazone Lambda     
* elastic search
---
