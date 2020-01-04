---
---
#Laddningstid och användbarhet

Uppgiften handlar om att undersöka och analysera olika webbplatsers laddningstid.

##Urval

Denna gången utgick jag från en annan fritidssysselsättning som för stunden har fått lite mer utrymme, nämligen World of Warcraft. Jag valde tre olika sidor som jag besöker ganska ofta med anknytning till spelet:

- [Icy Veins](http://www.icy.veins.com) [(screenshot)](img/screenshot-icyveins.png)
- [Wowhead](http://www.wowhead.com) [(screenshot)](img/screenshot-wowhead.png)
- [WowDB](http://www.wowdb.com) [(screenshot)](img/screenshot-wowdb.png)

##Metod

Analysen genomfördes m.h.a. två verktyg. Dels Googles [PageSpeed Insights](developers.google.com/speed/pagespeed/insights/) samt devtoolsen i Google Chrome.
Jag analyserade varje huvudsida samt två undersidor till denna tre gånger och noterade testvärdena i ett kalkylblad. Jag noterade även de rödmarkerade förbättringsförslag som PageSpeed gav mig.

##Resultat

[Kalkylblad](https://docs.google.com/spreadsheets/d/1fxFnUqRrv_3m-kxLWTmVNwrRbC9Kx6r0PCD8HSVrsIs/edit?usp=sharing)

Icy Veins klarade sig väldigt bra (73/97). Sidan laddar snabbt (1-1.5s) och mängden överförd data var låg (1,5MB). Den enda förbättringen som föreslogs var att skjuta upp inläsninen av bilder som inte visas på skärmen (för mobila enheter). 

Wowhead mätte inte lika bra (4/38) och här fanns det en gedigen lista med förbättringsförslag. Jag har valt ut några nedan. Fler finns i kalkylbladet. Laddningstiden låg på 2,5s och mängen överförd data runt 3MB.

* Ta bort resurser som blockerar renderingen
* Skjut upp inläsning av bilder som inte visas på skärmen
* Koda bilder effektivt
* Använd bilder med rätt storlek
* Skicka statiska tillgångar med en effektiv cachelagringspolicy

Inte heller Wowdb var lysande (12/68). Laddningstiden låg även här runt 2,5s och mängden överförd data runt 1MB. Förbättringarna som föreslogs var:

* Minska svarstiden till servern
* Ta bort resurser som blockerar renderingen
* Skicka statiska tillgångar med en effektiv cachelagringspolicy
* Se till att all text förblir synlig medan webteckensnitten läses in

##Analys

Sidorna både ser och mäter väldigt annorlunda. Både Icy Veins och Wowhead är stora sidor med väldigt mycket bilder, dock med väldigt olika resultat. Med tanke på förbättringsförslagen så verkar Icy Veins hantera sina bilder på ett bättre sätt, både gällande kodning och bildstorlek.
Wowdb mätte även den sämre. Detta är dock en sida utan en massa bilder så här bör prestandan lida p.g.a. av något annat. Sett till förbättringsförslagen så verkar inte servern hänga med ordentligt, samt att sidan inte är kodad på ett effektivt sätt.

Det finns ett par punkter som dök upp för samtliga tre sidor:

* Skicka statiska tillgångar med en effektiv cachelagringspolicy
* Ta bort resurser som blocker renderingen
* Skjut upp inläsning av bilder som inte visas på skärmen (på de sidor som använde sig av bilder)

Rangordning

1. Icy Veins
2. Wowdb
3. Wowhead

Icy Veins får riktigt bra mätresultat och känns snabb och är således min vinnare. Wowhead är raka motsatsen och hamnar därmed sist.

Sett till sidorna jag arbetat med så upplever jag både wowhead och wowdb som något sega, medans Icy Veins känns bättre. Utifrån detta skulle jag säga att jag anser en snabb sida ha en laddningstid på < 2s.

##Referenser
[PageSpeed Insights](developers.google.com/speed/pagespeed/insights/)

##Övrigt

Johan Eng, jag har utfört uppgiften ensam.