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

Jag är så JÄVLA LAT så jag använde LESS. Det är coolt också. För coola, lata killar.

##Del 4. Äntligen KOD!
Nu ska vi skriva lite JS! jQuery-JS, men ändå. Ledsen att harva igenom all skit först, men det är viktigt att vi har samma grund.

###Krav på funktionaliteten
- Man ska medelst knapptryck kunna hoppa en bild framåt eller bakåt
- När man når sista bilden och trycker nästa, så ska man komma till första
- Samma som ovan, fast sista bilden och tvärtom

Jag tänker som såhär: Vi har lagt alla bilder i en lista och med CSS begränsat den så man bara ser den första bilden i listan. Den första SYNLIGA bilden i listan!

Således:

- Besökaren trycker på "Nästa"
	- Scriptet letar upp den första synliga bilden i listan och gömmer den
		- Om den första synliga bilden, är den sista bilden i listan, visa alla bilder
- Besökaren trycker på "Förra"
	- Scriptet letar upp den sista gömda bilden och visar den
		- Om det inte finns någon gömd bild, göm alla bilder utom den sista i listan
		
Låter det bra? Bra!

###Doppa fötterna
Vi börjar med att att binda events till knapparna och skriver ut deras funktion i konsolen, så att vi vet att knapparna reagerar som de ska.

Så när eventet "click" sker på "Nästa" så ska det skrivas ut "next" i konsolen och likaså ska det skrivas ut "previous" i konsolen för eventet "click" på "Förra".

Du vet hur det funkar:

- [Jonas Förslag](https://github.com/cjgk/beargramming/blob/e6af731474b6cfad83a7289704ac258658a48ae6/index.html)
- [Ändringar sen sist](https://github.com/cjgk/beargramming/compare/31a914f3f8e210cb5529ac98e682e0c99b3a3067%E2%80%A6e6af731474b6cfad83a7289704ac258658a48ae6#index.html)

###Visa nästa bild (gömma första synliga)
Okej, du vet vad du ska göra! 

När man trycker på "Nästa", hitta alla bilder i vår lista som inte är gömda och göm sen den första av dem. Go go go!

Tjuvkika:

- [Jonas förslag](https://github.com/cjgk/beargramming/blob/f56286d9dc3633f9c71f532b618d9e6c7e551e95/index.html)
- [Diff](https://github.com/cjgk/beargramming/compare/e6af731474b6cfad83a7289704ac258658a48ae6%E2%80%A6f56286d9dc3633f9c71f532b618d9e6c7e551e95#index.html)

###Hantera sista bilden
Om du gjorde precis som jag gjorde i förra steget, så blev sista trycket på "Nästa" jävligt tråkigt, för det blev bara vitt. Det suger, för det stämmer inte med vår spec och då får vi inte betalt. Det måste vi greja!

I programmering finns ju inget facit, men det här funkar:

- [Jonas](https://github.com/cjgk/beargramming/blob/0f711464a833b9aed9073d137aa2f62d3c6ac422/index.html)
- [Diff](https://github.com/cjgk/beargramming/compare/f56286d9dc3633f9c71f532b618d9e6c7e551e95%E2%80%A60f711464a833b9aed9073d137aa2f62d3c6ac422#index.html)

###Baklänges då?
Jag ska kolla på Bilbo nu, så jag hinner inte skriva något om det, så det blir din hemläxa. Använd github för att göra en pull request med lösningen så ska jag kolla på den.

Andra grejer att fixa (i varsin pull request!!!):

- Slajda bilderna horisontellt istället för vertikalt
- Fixa den fruktansvärt fula övergången mellan sista och första bild när man rundar listan

Ring om det är något. När jag inte jobbar. Hej!