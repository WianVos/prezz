# vragen ec2
---
## Waar staat ec2 voor ? 
+++
Amazon Elastic Compute Cloud .. 
---
## Welke vier catagorieen instance typen zijn er binnen EC2? 
+++
* On Demand
* Reserved capacity
* Spot instances 
* Dedicated hosts 
---
## Wat is duurder On Demand instances of Spot Instances? 
+++
On Demand is de duurste optie binnen ec2 
---
## Wat is de tijdseenheid waarin je EC2 capaciteit afrekend??
+++
vroeger per uur .. nu per seconde
--- 
## Welke instance types zijn er binnen EC2
+++
# DR Mc GIFT PX
+++
* D Dense Storage
* R Ram intensive (memory optimized)
* M Main choice for general compute
* C Compute Optimized
* G Graphics intensive
* I High speed storage (IOPS)
* F FPGA (Field programmable gate array)
* T Cheap general purpose (T2.micro)
* P Graphics (think Pics ???? wutt ?? )
* X eXtreme Memory 
---
## wat is EBS
+++
EBS staat voor elastic block storage 
+++ 
## Hoe verschilt dit van EC2
+++
EBS kun je gebruiken als normale disk space en b.v. een os op installeren . 
EC2 is puur voor objecten 
---
## Welke typen EBS volumes zijn er? 
+++
* SSD 
..* GP2 < 10.000 IOPS
..* IO1 > 10.000 IOPS
* HDD
..* ST1 Frequent Access
..* SC1 less Frequent Access
..* Magnetic cheap infrequent access 
---
## welke EBS volumes kunnen worden gebruikt als boot volumes in EC2??
+++
* GP2
* IO1
* Magnetic
---
## Wat is een spot instance ? 
+++
Een instance waarbij je een prijs opgeeft .. wanneer de actuele (markt) prijs voor een instance (al naar geland de bezetting van de region) onder je gestelde max prijs zakt wordt deze opgestart .. stijgt de prijs er boven dan wordt deze getermineerd ..
---
## Betaal je de volle uurprijs als je een spot instance termineert ? 
+++
Ja .. als je het zelf doet wel .. als amazon het doet betaal je het laatste uur niet .
---
##Wat zijn de kenmerken van ON Demand ec2 instances
+++
* geen verplichtingen / niet vooraf betaald
* Applicaties met een korte termijn character of veel pieken en dalen in gebruik
* Ontwikkel / test capaciteit. 
---
## Hoe maak je een amazon Ami
+++
Stop machine -> snapshot -> maak van de snapshot ami. 

---
## Kunnen encrypted Ami’s gedeeld worden?
+++
Nee
+++
Waarom niet?
+++ 
De encryptie key wordt bewaard in je account 
---

## Is een snapshot van een encrypted volume ook ge-encrypt? 
+++
Ja ….. duh 
---
## Wat zijn de selectie criteria voor een Ami? 
+++
* Regio
* os
* architectuur(x32/x64)
* launch permission 
* root device storage
---
## Wat gebeurt er als je een instance stopt en start 
+++
De Ami wordt geboot op een andere hypervisor in het datacentrum van amazon
---
## Kun je extra volumes toevoegen aan een instance store instance na lancering? 
+++
Ja .. maar alleen ebs volumes
---
## Kun je instance store instances stoppen? 
+++
Nee.. alleen terminaten of rebooten
---
## Verschijnen instance store volumes in het volume menu ? 
+++
Nope .. ze kunnen ook niet gedettached worden .. 
---
## Hoe worden EBS backed instances gecreëerd..? 
+++
Vanaf een snapshot van een EBS volume 
---
## Hoe wordt een Instance store instance gecreëerd? 
+++
Vanaf een volume template opgeslagen op S3 … 
Dit duurt langer
---
## Wat is een andere naam voor instance store volumes? 
+++
Ephemeral Storage .. 
---
## Ben je je data kwijt als een instance store backed instance er uit klapt? 
+++
Ja .. 
+++
Dit is niet het geval bij EBS backed instances 

## Wat is raid 0 ? 
+++
Stripe … 
+++
## Wat is raid 1 ?
+++
Mirror
+++
Wat is raid 5 ?
+++
Striped with parity check
Goed bij reads .. slecht bij writes
+++
Wat is Raid 10 ??
+++
Striped en Mirrored … redundant en hoog performant. :-)
---
## Kun je een raid opstelling creëren in een amazon instance ? 
+++
Ja ..  met meerdere ebs volumes
---
## Hoe kun je een snapshot maken van een raid array ? 
+++
Met een Application Consistent snapshot .
---
## Wat is een application consistent snapshot? 
+++
Een snapshot van alle EBS volumes in het array waarbij :
* het filesysteem in bevroren staat verkeerde
* de raid array niet gemount was .
* de instance uit stond 

---
## What are the two types of loadbalancers:
+++
Application load balancers and classic load balancers
---
## What is the difference between classic and application loadbalancers
+++
Application load balancers are L7 
Classic is layer 4 
---
## Do elb’s have an ip-address ? 
+++
Yes but it is nog given to the user.. instead only a dns name is available
---

## What is cloud watch 
+++
Cloud watch is monitoring for ec2

---
## What is the standard monitoring interval for cloud watch monitoring ??
+++
5 mins the detailed one is 1 minute
 
---
##What are the main function categories of cloud watch
+++
*Dashboards
*Alarms
*Events and Logs
---
## What is the difference between cloud watch and cloud trail ? 
+++
Watch is for monitoring , trail is for auditing.
---
## What do you need to have in order to use the AWS Cli?
+++
A acces_key_id and secret_acces_key

---
##Op welke scope worden IAM roles aangemaakt .
+++
Global .. IAM is een global dienst 

---
## Kun je IAM rollen later aan een EC2 instance hangen ? 
+++
Ja dat kan .. je kunt rollen aanbrengen en vervangen 
---
## Kun de de aws cli gebruiken zonder access_key_id en secret_access_key? 
+++
Ja dat kan door de juiste role aan de instance waar je op aangelogd bent te hangen 
---
## Als je een script mee wil geven aan de start procedure van een instance, waar doe je dat dan ???
+++
In het user data veld onder de kop advanced details tijden het starten van de instance 
---
## via welke url kun je meta data over een EC2 instance ophalen vanaf de instantie zelf. ?
+++
http://169.254.169.254/latest/meta-data

---
## Wat het je nodig om een autoscaling group op te zetten .. 
+++
Even elastic load balancer en een launch configuration 
---
## Hoe voeg je meerdere availability zones toe aan je autoscaling group? 
+++
Door de subnets toe te voegen tijdens de creatie van de group
---
## Welke twee health check types kent een auto scaling group ? 
+++
EC2 en ELB .. 
---
## Hoe wordt de scaling binnen een scaling group geregeld ?
+++ 
Dmv alarms .. b.v. 90% cpu over een periode van 5 minuten 
---
## Op welke schaal kun je je site / applicatie middels autoscaling groups beschermen tegen uitval ? 
+++
Autoscaling groups kunnen alleen uitvallende machines en availability zones opvangen .. voor hele regio’;s heb je route53 nodig 
---
##Wat is een placement group binnen ec2 ? 
+++
Een logische groepering van machines binnen een availability zone welke daardoor gebruik kan maken van 10GBPS networking. 
+++
Dit gebruik je vooral voor applicaties als Cassandra of Hadoop 
---
##Kan een Placement group worden geplaatst over meerder availability zones heen?? 
+++
Nee .. 
---
##Zijn er nog speciale eisen aan de naamgeving van placement groups? 
+++
Ja .. de naam moet uniek zijn binnen je account 
---
## Kun je alle typen machines lanceren binnen een placement group 
+++
Nee .. alleen CPU/Memory/Storage optimized en GPU instances kunnen hiervoor worden gebruikt . 	
+++
Amazon raad aan om binnen een placement group homogeen te blijven met het type machine 
---
##Kun je placement groups samenvoegen ? 
+++
Nee .. dat kan niet . 
---
## Kun je instances toevoegen aan placement groups ? 
+++
Nee , je kun wel machines in je placement group lanceren , maar een draaiende instance toevoegen kan niet . 
---
## wat is EFS (Elastic File System ) 
+++
Efs is een shared filesystem dat mee groeit met het gebruik
---
##Welke protocol wordt gebruikt voor EFS? 
+++
NFS (V4) 
In Principe is EFS een metered pay as you go nfs service 
---
## wat zijn de karakterestieken van een security group ten aanzien van netwerk verkeer. 
+++
al het inbound traffic wordt geblockeerd
al het outbound traffic wordt toegelaten
---
## hoeveel ec2 instances kun je koppelen aan een security group
+++
onbeperkt
---
## Hoeveel security groepen kun je koppelen aan 1 ec2 instance
+++
onbeperkt 
---
## kun je specifieke ipadressen toelaten middels een security group ? 
+++
Ja je kunt een specifiek ip toegang verschaffen tot een machine middels een security group
+++ 
Wat niet kan is een specifiek ip-adress blokkeren