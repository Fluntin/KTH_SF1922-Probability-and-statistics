\title{
Föreläsning ett
}

\author{
Joakim Andén
}

31 oktober 2022

\section{Översikt}

Denna kurs innefattar två huvudämnen. Det första är sannolikhetsteori och handlar om att beskriva slumpen, eller mer specifikt slumpmässiga förlopp. Dessa präglas av en viss osäkerhet där vi inte kan säga exakt hur ett förlopp (eller matematiskt förhållande) ser ut. Sannolikhetsteorin fokuserar därför istället på sannolikheten att någonting inträffar på ett visst sätt och på detta vis kan en sannolikhetskalkyl utvecklats.

Till exempel kan vi ta Ohms lag:

$$
U=R \cdot I,
$$

dvs. spänningen $(U)$ är lika med resistans $(R)$ gånger ström $(I)$. Detta är en deterministisk modell (dvs. ej slumpmässigt).

I verkligheten stämmer dock aldrig denna relation exakt utan vi har olika typer av mätfel. Till exempel så kan temperaturvariationer ge upphov till små skillnader i spänningen. Skillnader från formeln ovan kan också uppstå om vi har orenheter i resistorn eller ledningen. Dessa skillnader kan modelleras som en variabel $Z$. Vi får då

$$
U=R \cdot I+Z .
$$

Det viktiga här är att värdet på $Z$ i regel är okänt men vi kan ändå ha en uppfattning om vilka värden den kan anta och med vilka sannolikheter. Detta är då en stokastisk modell eller slumpmodell.

Den andra delen av kursen använder sannolikhetsteorin för att extrahera information från data och använda detta för att dra olika slutsatser. Detta kallas för statistisk inferens. I modellen ovan kan det handla om att bestämma $R$ givet olika mätvärden av $U$ och $I$. Utöver detta kan det finnas olika parametrar i beskrivningen av $Z$ som behöver skattas för att ge en komplett modell. Vi skulle alltså kunna använda datan för att svara på följande frågor: "hur stor är resistensen i systemet?", "är resistensen mindre än 100 ohm?", "hur stort mätfel har vi i genomsnitt?" eller "hur många mätningar måste vi ta för att bestämma resistensen med en osäkerhet på högst 1 ohm?". 

\section{Tillämpningar}

Sannolikhetsteori och statistik kan användas i ett stort antal tillämpningar:

■ Opinionsundersökningar: "31\% av väljarna tänker rösta på Socialdemokraterna med $2 \%$ felmarginal."

■ Kvalitetskontroll: "En dos läkemedel innehållet $5 \pm$ 0.03mg av den aktiva substansen."

■ Pris på försäkringspremier eller optioner: "Vilket pris garanterar vinst med 95\% sannolikhet (förutsett att vår modell stämmer)?".

■ Vetenskapliga slutsatser: "Hur väl stämmer mätdatan överens med hypotesen att metangasutsläppen i Sibirien har ökat med 5\% mellan 2010 och 2019?".

■ Modellering av priser: Bostadspriser som funktion av olika variabler plus en slumpmässig term

$$
Y=a_{1} x_{1}+x_{2} x_{2}+\cdots+Z \text {, }
$$

där $Y$ är priset i kronor, $x_{1}$ är antalet rum, $x_{2}$ är boytan, osv. Om vi anpassar $a_{1}, a_{2}$, osv. till data, hur säkra kan vi vara på att de ger rätt pris när vi tillämpar på nya data?

■ Maskininlärning: Bygg modeller från data som förutsäger (predikterar) egenskaper eller värden hos andra, ej än observerade, data. Exempel: "Vad är sannolikheten att en $32 \times 32-$ bild föreställer en katt?"

\section{Utfall och händelser}

Informellt sett är ett slumpmässigt försök ett "oförutsägbart förlopp" - även om det upprepas under exakt samma omständigheter kan vi inte (eller vill inte) förutsäga resultatet från gång till gång. (Det finns andra tolkningar av slump-och sannolikhetsbegreppen, se nedan.)

Grundläggande begrepp inom sannolikhetsteorin är utfall, utfallsrum och händelser. Ett utfall är resultatet av ett slumpmässigt försök. Mängden av alla möjliga utfall kallas utfallsrummet. En samling utfall (dvs. en delmängd av utfallsrummet) kallar för en händelse. (Notera att "utfall" och "händelse' inte är synonyma inom sannolikhetsteorin.) Konventionen är att beteckna utfall med variablerna $\omega_{1}, \omega_{2}, \ldots$, utfallsrummet med $\Omega$ och händelser med $A, B, \ldots$

Exempel 1. Vid ett tärningskast kan de olika utfallen bestå av antalet ögon på tärningen. Detta ger då

$$
\begin{aligned}
&\omega_{1}=\text { "tärningen har ett öga" } \\
&\omega_{2}=\text { "tärningen har två ögon" } \\
&\vdots \\
&\omega_{6}=\text { "tärningen har sex ögon" }
\end{aligned}
$$

med utfallsrummet

$$
\Omega=\left\{\omega_{1}, \omega_{2}, \ldots, \omega_{6}\right\} .
$$

Några händelser kan då vara

$$
\begin{aligned}
&A=\text { "antalet ögon är udda" }=\left\{\omega_{1}, \omega_{3}, \omega_{5}\right\} \\
&B=\text { "antalet ögon är minst fem" }=\left\{\omega_{5}, \omega_{6}\right\} \\
&C=\text { "antalet ögon är exakt sex" }=\left\{\omega_{6}\right\} .
\end{aligned}
$$

Notera att i det sista fallet har vi en händelse $C$ med ett enda utfall $\omega_{6}$.

Utfallsrum kommer i väsentligen två former: diskreta och kontinuerliga. Om $\Omega$ är ändligt eller uppräkneligt oändlig kallas det för ett diskret utfallsrum. Annars (dvs. om $\Omega$ är ouppräkneligt oändligt) kallas $\Omega$ för ett kontinuerligt utfallsrum. (Kom ihåg att en uppräkneligt oändlig mängd är en mängd där vi kan ge varje element ett positivt heltal som "etikett'.)

Exempel 2. Vi kan betrakta följande utfallsrum:

$$
\begin{aligned}
& \text { Antalet ögon vid ett tärningskast } \\
& \text { diskret (ändligt, } 6 \text { möjliga utfall) } \\
& \text { Antalet kast tills vi får en etta } \\
& \text { diskret (uppräkneligt oändligt) } \\
& \text { Antalet ögon vid vid } n \text { tärningskast } \\
& \text { diskret (ändligt, } 6^{n} \text { utfall) } \\
& \text { Tiden kvar i minuter till slutet av föreläsningen kontinuerligt }(\Omega=[0,120)) \\
& \text { Vinkeln en tappad synål bildar med en fix linje kontinuerligt }(\Omega=[0, \pi)) \\
& \text { på ett papper }
\end{aligned}
$$

Informellt är $\Omega$ ett kontinuerligt utfallsrum om utfallen kan ligga "oändligt nära varandra". Som innan är händelser fortfarande en delmängd av utfallsrummet. I det sista exemplet ovan skulle kunna ha händelsen "vinkeln är mellan än $\pi / 4$ och $3 \pi / 4$ " vilket skulle motsvara delmängden $[\pi / 4,3 \pi / 4)$.

\section{Snitt, union och komplement}

Vi har nu sett olika exempel på utfallsrum och händelser. Hur kombinerar vi dessa på olika sätt? Här kan vi använda begrepp från mängdläran eftersom $A$ och $B$ är delmängder av utfallsrummet $\Omega$.

Till exempel kanske vi har två händelser $A$ och $B$ och vill beskriva vad som händer om båda inträffar. Detta kallar för snittet av $A$ och $B$ och skrivs

$$
\begin{aligned}
A \cap B &=\text { "både } A \text { och } B \text { inträffar" } \\
&=\{\text { alla utfall som ligger i både } A \text { och } B\} \\
&=\{\omega \in \Omega: \omega \in A \text { och } \omega \in B\} .
\end{aligned}
$$

Detta motsvarar ett logiskt "och" (dvs. "AND" i boolesk logik). Vi kan generalisera detta till $n>2$ händelser

$$
A_{1} \cap A_{2} \cap \cdots \cap A_{n}=\left\{\omega \in \Omega: \omega \in A_{1}, \omega \in A_{2}, \ldots, \omega \in A_{n}\right\},
$$

vilket också kan skrivas

$$
\bigcap_{i=1}^{n} A_{i} .
$$

Om $A \cap B=\varnothing$ (dvs. snittet av $A$ och $B$ är den tomma mängden) så innehåller $A$ och $B$ inte några gemensamma utfall och vi säger att $A$ och $B$ är oförenliga. Med andra ord så kan $A$ och $B$ inte inträffa samtidigt. (Inom mängdläran kallas $A$ och $B$ för disjunkta mängder.)

Ett annat sätt att kombinera $A$ och $B$ är att ta unionen, vilket motsvarar händelsen att $A$ eller $B$ inträffar. Vi skriver detta som

$$
\begin{aligned}
A \cup B &=\text { "minst en av } A \text { eller } B \text { inträffar" } \\
&=\{\text { alla utfall som ligger } \text { i } A \text { eller } B\} \\
&=\{\omega \in \Omega: \omega \in A \text { eller} \omega \in B\} .
\end{aligned}
$$

Detta motsvarar ett logiskt "eller" (dvs. "OR" i boolesk logik). Notera att detta skiljer sig från "exklusivt eller", dvs. "antingen ... eller...". Händelsen ovan tillåter att både $A$ och $B$ inträffar samtidigt. Med andra ord har vi $A \cap B \subset A \cup B$.

Som innan kan vi generalisera unionen till $n>2$ händelser:

$$
A_{1} \cup A_{2} \cup \cdots \cup A_{n}=\left\{\omega \in \Omega: \omega \in A_{1} \text { eller } \omega \in A_{2} \text { eller } \cdots \text { eller } \omega \in A_{n}\right\}
$$

vilket också kan skrivas

$$
\bigcup_{i=1}^{n} A_{i} .
$$

Om vi endast har en händelse $A$ kan vi definiera dess komplement (inom $\Omega$ ), dvs. att $A$ inte händer, genom

$$
\begin{aligned}
A^{\star} &=\text { "A inträffar inte" } \\
&=\{\text { alla utfall som inte ligger } \text { i } A\} \\
&=\{\omega \in \Omega: \omega \notin A\} .
\end{aligned}
$$

Detta motsvarar logiskt "inte" (dvs. "NOT" i boolesk logik). Komplementet kan också skrivas som $A^{\complement}, \complement A, \Omega \backslash A$ eller $\Omega-A$. De senare två uttrycken är användbara när det inte framgår tydligt vilket rum som komplementet ska tas med avseende på (dvs. när det inte är klart vad som är utfallsrummet).

Med hjälp av definitionerna ovan kan vi nu definiera "exklusivt eller" som $(A \cup B) \backslash$ $(A \cap B)$, dvs. unionen av $A$ och $B$ där vi har tagit bort snittet.

\section{Euler-och venndiagram}

För att visualisera olika händelser inom ett utfallsrum kan det vara bra att rita bilder som illustrerar relationerna mellan händelserna. Dessa kallas då eulerdiagram (ett eulerdiagram där alla händelser överlappar med varandra kallas för ett venndiagram). Notera att även om dessa kan vara bra för att bygga intuition om olika händelser så kan de också leda till fel slutsatser om man inte är försiktig. Därför är det alltid säkrast att använda mängdlärans räkneregler (se nedan). 
![](https://cdn.mathpix.com/cropped/2022_11_15_24cfd38a0410681387a3g-5.jpg?height=962&width=788&top_left_y=217&top_left_x=663)

Komplement
![](https://cdn.mathpix.com/cropped/2022_11_15_24cfd38a0410681387a3g-5.jpg?height=1258&width=788&top_left_y=756&top_left_x=663)

Ett annat sätt att illustera relationen mellan händelser är genom sanningsvärdestabeller där vi markerar med "S" ("sant") om en händelse inträffar och "F" ("falskt") annars. 

\begin{tabular}{cccc}
$A$ & $B$ & $A \cap B$ & $A \cup B$ \\
\hline $\mathrm{S}$ & $\mathrm{S}$ & $\mathrm{S}$ & $\mathrm{S}$ \\
$\mathrm{S}$ & $\mathrm{F}$ & $\mathrm{F}$ & $\mathrm{S}$ \\
$\mathrm{F}$ & $\mathrm{S}$ & $\mathrm{F}$ & $\mathrm{S}$ \\
$\mathrm{F}$ & $\mathrm{F}$ & $\mathrm{F}$ & $\mathrm{F}$
\end{tabular}

\section{Mängdlärans räkneregler}

Om vi har mer komplicerade relationer mellan händelser kan vi ofta skriva om dessa med hjälp av ett par räkneregler. Dessa kan bevisas genom att skriva upp sanningsvärdestabellerna och verifiera att de är ekvivalenta.

Först har vi att snitt distribuerar över union, dvs. att

$$
A \cap(B \cup C)=(A \cap B) \cup(A \cap C) .
$$

I vänsterledet har vi händelsen " $A$ och minst en av $B$ eller $C$ inträffar" medan i högerledet har vi att minst en av " $A$ och $B$ inträffar" eller " $A$ och $C$ inträffar" inträffar.

![](https://cdn.mathpix.com/cropped/2022_11_15_24cfd38a0410681387a3g-6.jpg?height=377&width=851&top_left_y=1140&top_left_x=645)

Vi har också att union distribuerar över snitt, dvs. att

$$
A \cup(B \cap C)=(A \cup B) \cap(A \cup C) .
$$

I vänsterledet har vi att minst en av "A inträffar" eller "B och $C$ inträffar" inträffar. Högerledet ger att "minst en av $A$ eller $B$ inträffar" och "minst en av $A$ eller $C$ inträffar".

![](https://cdn.mathpix.com/cropped/2022_11_15_24cfd38a0410681387a3g-6.jpg?height=358&width=857&top_left_y=1886&top_left_x=626)

Till sist har vi De Morgans lagar som säger att

$$
\begin{aligned}
(A \cap B)^{\star} &=\text { " } A \text { och } B \text { inträffar inte båda två" } \\
&=\text { "minst en av } A^{\star} \text { eller } B^{\star} \text { inträffar" } \\
&=A^{\star} \cup B^{\star} .
\end{aligned}
$$

samt

$$
\begin{aligned}
(A \cup B)^{\star} &=\text { "varken } A \text { eller } B \text { inträffar" } \\
&=\text { "både } A^{\star} \text { och } B^{\star} \text { inträffar" }
\end{aligned}
$$

$$
\begin{aligned}
& A^{\star} \cap B^{\star}
\end{aligned}
$$

![](https://cdn.mathpix.com/cropped/2022_11_15_24cfd38a0410681387a3g-7.jpg?height=694&width=805&top_left_y=447&top_left_x=671)

\section{Sannolikhet}

Vi tilldelar nu varje händelse $A \subset \Omega$ ett värde mellan noll och ett som vi kallas $A$ :s sannolikhet. Detta värde betecknas med $P(A)$.

Frågan är nu hur vi väljer $A$ ? Vad är egentligen en sannolikhet? Det finns olika tolkningar av sannolikhetsbegreppet. En vanlig tolkning är frekvenstolkningen:

Om vid $N$ slumpmässiga försök $A$ inträffar $N_{A}$ av gångerna sätter vi $P(A)=$ $\lim _{N \rightarrow+\infty} N_{A} / N, d v s . P(A)$ är den relativa frekvensen av $A$ när antalet försök går mot oändligheten.

Frekvenstolkningen är naturlig för vissa fenomen som tärningskast, kortspel eller olika fysikaliska förlopp. För andra påståenden som "chansen för regn på lördag är $80 \%$ " eller "Donald Trump vann valet 2020 med $10 \%$ sannolikhet" blir frekvenstolkningen problematisk. Då passar en subjektiv tolkning (också kallad bayesiansk tolkning) bättre:

Sannolikheten $P(A)$ motsvarar hur "troligt" vi anser det är att händelsen A inträffar.

Detta ger en bredare definition av sannolikhet men kan vara lite för "personlig" för att beskriva till exempel fysikaliska fenomen (en sönderfallande cesiumatom bryr sig inte så mycket om vad vi "tror".)

Valet av tolkning beror på tillämpningen och studeras flitigt inom sannolikhetsteorins epistemilogi (en del av den matematiska filosofin). Oavsett tolkning ska vi se att man kan räkna på samma sätt med de resulterande sannolikheterna så länge de följer ett par grundläggande regler.