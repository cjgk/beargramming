#Projekt "Snurr, snurr"

**Idag ska vi sätta ihop en liten JavaScript-karusell som loopar runt ett valfritt antal bilder. Det kommer dels ta upp i vilken ordning man bör göra grejer, dels lite olika JS-grejer, som t.ex. events och timers och sån skit. Jag kommer såklart använda jQuery (1.8.3), för jag är för lat för att göra det i riktig JS.**

_Du och jag, vi använder Chrome när vi utvecklar i JS._

##Del 1. Planeringen
Det första du måste göra är att få klart för dig vad fan du ska göra. Har du ingen specifikation kommer allt gå åt helvete. 

###Beskrivning av Projektet
Vi vill göra en webbsideskomponent som kan visa ett odefinierat antal bilder, en i taget.

###Krav på projektet
- Listan över bilder ska inte behöva hårdkodas i HTML
- Användaren ska själv kunna stega sig igenom bilderna
- Om användaren inte har JavaScript påslaget ska hen fortfarande kunna se bilderna

##Del 2. Gjuta grunden
Det här är det näst tråkiaste, efter att faktiskt finputsa på slutet när man fått funktionaliteten på plats, men jag antar att det måste göras.

###index.html
Börja med att göra ett grundläggande html5-dokument som

- … inkluderar senaste versionen av jQuery från CDN
- … förbereder en ny script-tag som ger dig möjlighet att skriva jQuery-kod _efter_ att **document** har nått status **ready**
- … skriver ut "Jonas!" i JS-konsolen

När du skrivit ditt dokument kan du kolla på mitt här: [XYZ]

###Uppmärkningsstruktur
Nu är det dags att bestämma strukturen på hur det här ska se ut, kodmässigt.

###Krav på strukturen
- Ska ha knappar för att gå framåt och bakåt i listan över bilder
- Ska vara inkapslat i en div så man kan flytta den
- Det är en lista över bilder, så kapsla in dem i ett element som är semantiskt relevant