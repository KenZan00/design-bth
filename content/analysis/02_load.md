---
Title: Load
Description: This is our load page.
Template: index
---

Load
==========================

Denna rapporten består av en laddtidsanalys av tre webbsidor som jag själv har valt ut.

<!--- Skriv en eller två rader om vad uppgiften handlar om. -->

Urval
-----------------------
Mitt urval består av tre stycken sidor. Alla sidorna är helt olika från varandra, men har gemensamt att de är stora och omsätter relativt mycket trafik. Sidorna är valda eftersom de är bekanta till mig i vardagen.

Följande val gjordes:

<ul class="links">
  <li><a href="https://www.iaplc.com" class="site-link">International Aquatic Plants Layout Contest</a></li>
  <li><a href="https://www.ikea.se" class="site-link">IKEA.se</a></li>
  <li><a href="https://www.web.dev" class="site-link">Web.dev</a></li>
</ul>




<!--- Berätta vilka webbplatser du valt att undersöka och varför eller hur du gick tillväga när du gjorde ditt urval. -->

Metod
-----------------------
Jag började med att välja tre sidor som jag kan relatera till antingen genom vardagen eller hobbyintresse. För att ta fram den data som behövdes för jämförelse och analys användes, <a href="https://pagespeed.web.dev/" class="site-link">PageSpeed Insights</a> och inspektera-funktionen i Firefox. 

<!---  Berätta kort om din "metod", hur du gör för att utföra undersökningen. Berätta om du använder något speciellt verktyg. -->

Resultat
-----------------------

Rådata från mätningarna:

<div class="spredsheet">
    <iframe width="680" height="250" src="https://docs.google.com/spreadsheets/d/e/2PACX-1vSeqXDQTToKsqc4L3DHpZ6ahPmp71RWD2dFFjUreIvfDp9CnaaWdu_2rEdsQ_t6WJ6OJxuppYLdewy9/pubhtml?widget=true&amp;headers=false"></iframe>
</div>

![iaplc](%assets_url%/img/IAPLC.jpg){.screenshot}

### IAPLC

Mobile: 55p  Dekstop: 55p

IAPLC's webbplats har en laddningstid på 21,5s. 75st resurser på startsidan och en total storlek på 9,3MB. Webbsidan laddar in hela sidan på en gång och detta tar ur användarperspektiv en relativt lång tid. Webbplatsen skulle kunna förbättra sig genom, att endast ladda in de direkt visuella delarna, minska antal resurser, och framförallt antal MB. IAPLC har en 'Largest Contentful Paint (LCP)' på 7,2s och mycket information och bilder bidrar till att hemsidan skulle tjäna på att ladda in visuella delar bitvis för en bättre användarupplevelse.

IAPLCs hemsida håller dock ett jämnt prestandapoäng mellan mobile och desktop som landar på 55 poäng. IAPLC får icke godkänt av google pagespeed. De tre största förbättringsförslage när "Ta bort resurser som blockerar renderingen", "Använd bilder med rätt storlek", "Skicka bilder i modernare bildformat".

![ikea](%assets_url%/img/IKEA.jpg){.screenshot}

### IKEA

Mobile: 50,6p  Dekstop: 73p

IKEA's hemsida har en laddningstid på 2,4s. Den har 32,7 resurser och laddar in material eftersom man scrollar. Webbplatsen skulle kunnda förbättra sig genom att reducera javascript och css som inte används. När man laddar in hemsidan och analyserar via firefox inspect blir det många röda resurser. För att sammanfatta så ligger de flesta förbättringsförslagen på IKEAS hemsida i javascript-koden. "Minska tid att tolka js-kod", "ta bort resurser som hindrar första rendering", "Reducera javascript som inte används".

IKEA fär godkänt av google pagespeed.

![web.dev](%assets_url%/img/webdev.jpg){.screenshot}

### WEB.DEV

Mobile: 29p  Dekstop: 83p

Web.dev har en laddningstid på 2,22s vilket är den snabbaste i testet. Där finns 14,7 resurser och vid de tester som utförts laddar den in allt material på en gång. Web.dev har en Largest Contentful Paint (LCP) på 2,5s , en First Contentful Paint (FCP) på 2,1s och en hög time to first byte på 1,4s i mobile. Sammanslaget skulle hemsida ha förbättringsförslag på samtliga av dess punkter enligt google pagespeed på mobile versionen men presterar bra på desktop vilket exemplen visar på. Största kritiken är "Reducera javascript som inte används"

Web.dev får icke godkänt av google pagespeed.

<!-- Dokumentera dina resultat från din studie. Berätta vad du kom fram till, vilka resultat du hittade och observerade. -->

Analys
-----------------------

Ser man på vad de vanligaste förbättringsförslagen verkar vara på de hemsidor som vi utgår från i analysen, så är de kopplade till framförallt javascript-användande och användande av bilder. Och om vi kopplar detta direkt till de exempel som jag har arbetat med kan man samanfatta dem i att, bilder är en stor punkt för IAPLC och javascript för de två andra.

Web.dev var en stor favorit innan analysen blev färdig då de borde vara ett föredömme för webbutveckling men falerar på mobilsidan. Själv skulle jag besöka denna sida med en desktop som webbutvecklare.

IKEA presterar relativt bra med både mobil och desktop i testet, vilket jag tror är kopplat i ett smart sätt att ladda in sidan efter behov och snabbt presentera ett material för användaren. Trots en hel del felmeddelanden i inladdningen av material i nätverksanalysen presterar sidan bra.

IAPLC är extremt långsam i jämförelse med de andra två sidorna. Den laddar hela sidan på en gång innan något annat än en "loading bar" presenteras, hade jag inte varit direkt intresserad av aquascaping, hade sidan stängts ner till förmån för en ny sökning på google.se . Detta beror till stor del på antal resurser, och dålig hantering av bilder tillsammans en stor total resurs på 9,3MB, vilket är avsevärt högra än de andra webbsidorna som använder kb.

Sambandet mellan en snabbt laddad sida kan enligt min analys relateras till hur snabbt och hur länga javascript laddas in/ blockerar inladdning. Hur många resurser som laddas in och storleken på dem. Det vill säga, hur mycket rå data och information som skall laddas in och under vilka begränsningar.

<!--- Diskutera och analysera de resultaten du fann. --->

Poäng
-----------------------

Rangordningen baseras på hemsidornas poäng som mobil + desktop / 2 för att ge ett snittbetyg.

1. IKEA: 61,8 poäng
2. IAPLC 55 poäng
3. Web.dev 52 poäng

IKEA är poängmässigt viktat bäst, följt av IAPLC som kommer tvåa trots extremt lång laddningstid på desktop, följt av web.dev som tappar poäng på en svag mobile-sida.

En bra laddningstid är under 4 sekunder. En personlig åsikt om vad som är bekvämt att vänta innan man undrar "vad som händer" och börjar söka efter andra alternativ på information.


Övrigt
-----------------------

Denna rapporten är skriven av mig, Kenny Åkerup.
