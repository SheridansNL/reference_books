**In terminal**

***Whois en Reverse Whois***
Om relevante info te vinden, zoals naam, email, telefoonnr, adres etc.
```bash
$ whois example.com
```

https://viewdns.info/reversewhois om interesante domeinnamen te vinden door te zoeken op naam van het bedrijf, email, telefoonnummer.

***IP adressen***
Om achter het ipadres te komen:
$nslookup example.com

zodra je deze hebt gevonden doe je een reverse ip lookup om  domeinen te zoeken op dezelfde server.

```bash
$whois "ip adres"

#whois.cymru.com is a database that translates ip's to ASNs
$whois -h whois.cymru.com "ipadres"
```

Om ip adressen binnen de scope te vinden kan gezocht worden naar routable networks op  het internet. Autonomous System Numbers (ASN) identificeren de eigenaar van die netwerken. Door meerder querys te draaien kom je erachter of er een bepaalde range bij dezelfde eigenaar hoort.

***Certificate parsing***
Om domeinen te vinden met behulp van SSL certificaten kan gebruikt worden gemaakt van online databases als crt.sh en cert spotter. (voor een output in json voeg in de zoekbalk &outpu=json toe)

***Subdomain Enumeration***
zoek zoveel als mogelijk subdomains voor meerdere aanvalshoeken. Dit proces kan geautmatiseerd worden.
	Geinstalleerd: Amass, Sublist3r en gobuster.
Op github zijn woordlijsten te vinden. Daniel Miesseler Seclist is goed.
Ook op github een woordlijst generator Commonspeak2

Het samenvoegen van woordlijsten zorgt voor betere resultaten. Om dubbele woorden te fileteren kan je het volgende commando uitvoeren.

```bash
$sort -u wordlist1.txt wordlist2.txt
```

***Service Enumeration***
Ontdekken welke services op een server draaien doormiddel van port-scanning. Dit kan middels active scanning door gebruik te maken van nmap of masscan. (Allebei geinstalleerd)
Of passief door gebruik te maken van shodan search. Is een website (ip adres nodig)

```bash
$nmap scanme.nmap.org
```

***Directory Bruteforcing***
dirsearch of gobuster voor het bruteforcen van directories op webservers. Reacties van servers:
	In de 200 range: de directorie of file bestaat en je kan erheen browsen
	404: bestaat niet
	403: forbidden en dus beschermd. Dit kan interessant zijn

Met eyewitness of snapper kan je automatisch screenshots maken van webpagina's middels een url lijst.

***web spidering***
