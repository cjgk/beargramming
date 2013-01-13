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

##Del 2. Gjuta grunden
Det här är det näst tråkiaste, efter att faktiskt finputsa på slutet när man fått funktionaliteten på plats, men jag antar att det måste göras.

###index.html
Börja med att göra ett grundläggande html5-dokument som

- … inkluderar senaste versionen av jQuery från CDN
- … förbereder en ny script-tag som ger dig möjlighet att skriva jQuery-kod _efter_ att **document** har nått status **ready**
- … skriver ut "Jonas!" i JS-konsolen

När du skrivit ditt dokument kan du kolla på mitt här: [Jonas förslag](https://github.com/cjgk/beargramming/blob/15016a265c7b4dd84776f50273520451f762dfd3/index.html)

###Uppmärkningsstruktur
Nu är det dags att bestämma strukturen på hur det här ska se ut, kodmässigt.

###Krav på strukturen
- Ska ha knappar för att gå framåt och bakåt i listan över bilder
- Ska vara inkapslat i en div så man kan flytta den
- Det är en lista över bilder, så kapsla in dem i ett element som är semantiskt relevant

När du lagt till det kan du kolla här: 

- [Jonas förslag](https://github.com/cjgk/beargramming/blob/f649e60436d8100d718bf7e1aeb563179017f1a6/index.html) 
- [Och här är ändringarna sen sist](https://github.com/cjgk/beargramming/compare/15016a265c7b4dd84776f50273520451f762dfd3%E2%80%A6f649e60436d8100d718bf7e1aeb563179017f1a6#index.html)

##Del 3. Piffa till det lite lagom
Ja, det var ju hysteriskt fult, men vi har ju hela sminklådan med oss, så det kommer bli fint. Vi ska närma oss den slutgiltiga formen nu, så vi måste krava lite igen.

###Krav på "designen"
- Lämna bara plats för en bild
- Visa bara den första bilden
- Lägg in knapparna för att byta bild på ett sobert och användarvänligt ställe

Sånt här gör ju du dagligen, med förbundna ögon, men som vanligt kan du kolla på:

- [Jonas förslag](https://github.com/cjgk/beargramming/blob/31a914f3f8e210cb5529ac98e682e0c99b3a3067/index.html)
- [Vad som ändrat sig sen sist](https://github.com/cjgk/beargramming/compare/f649e60436d8100d718bf7e1aeb563179017f1a6%E2%80%A631a914f3f8e210cb5529ac98e682e0c99b3a3067#index.html)