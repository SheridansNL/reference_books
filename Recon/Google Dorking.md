Begin met het verkennen van het doelwit. 
- Maak blader door de pagina's bekijk de functionaliteiten, maak een account aan etc.

De google search engine heeft een ingebouwde query taal. Type in de zoekbalk:
- **Site:** voor specifieke resultaten van een gespecificeerde pagina. (bijv. print site:python.org)
- **inurl:** om verborgen pagina's te kunnen vinden (bijv. inurl:"/course/jumpto.php" site:example.com)
- **intitle:** om specifieke strings in een pagina titel te vinden, zoals bijvoorbeeld file-listing pagina's (bijv. intitle:"index of" site:example.com)
- **link:** om pagina's te vinden die verwijzen naar een specifiek onderwerp op bijvoorbeeld een wikipedia pagina. (bijv. link:"https://en.wikipedia.org/wiki/ReDos")
- **filetype:** het vinden van pagina's met een specifieke file extensie. Super handig voor hackers! Voor bijvoorbeeld *.log files*. (bijv. filetype:log site:example.com)
- Wildcard *: (bijv. hoe te hacken * met google) 
- Quotes "": om een exacte match te forceren
- Or (|): Het pipe karakte | kan gebruikt worden om het een of het ander of beide  te zoeken. Deze is handig voor sites. (Bijv. "how to hack" site:(reddit.com | stackoverflow.com) of een onderwerp die op verschillende manieren geschreven kan worden zoals een afkorting en voluit)
- Minus -: om bepaalde resultaten uit te zonderen (bijv. "how to hack" -php)

Subdomeinen  zoeken
	* *.example.com

Kibana is een visualisatie tool om server status te monitoren en vaak te vinden onder app/kibana. Om te kijken of deze kwetsbaar is kan het volgende worden geprobeerd.
	site:example.com inurl:app/kibana

Zoeken naar extensies, zoals log, php, cfm, asp, jsp en pl (script bestanden)
	site:example.com ext:php

het is ook mogelijk om op inhoud van zon bestand te zoeken.
	site:example.com ext:txt password

**Zie de google exploit database voor meer!**
	