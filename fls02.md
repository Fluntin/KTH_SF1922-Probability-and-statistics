\title{
Föreläsning två
}

\author{
Joakim Andén
}

2 november 2022

\section{Repetition}

Ett utfallsrum $\Omega$ består av utfall $\omega_{1}, \omega_{2}, \ldots$ Kan vara diskret eller kontinuerlig. En samling händelser, dvs. delmängd av $\Omega$ kallas en händelse och betecknas $A, B$, osv.

Operationer på händelser.

- Snitt $A \cap B$, alla utfall som ligger i både $A$ och $B$ - motsvarar händelsen att både $A$ och $B$ inträffar.

■ Union $A \cup B$, alla utfall som ligger i minst en av $A$ och $B$ - motsvarar händelsen att minst en av $A$ och $B$ inträffar.

- Komplement $A^{*}=\Omega \backslash A$, alla utfall som inte ligger i $A$ (men ligger i $\Omega$ ) - motsvarar händelsen att $A$ inte inträffar.

Räkneregler för händelser:

- Snitt distribuerar över union: $A \cap(B \cup C)=(A \cap B) \cup(A \cap C)$.

■ Union distribuerar över snitt: $A \cup(B \cap C)=(A \cup B) \cap(A \cup C)$.

- De Morgans lagar

$$
(A \cap B)^{*}=A^{*} \cup B^{*} \quad(A \cup B)^{*}=A^{*} \cap B^{*} .
$$

Sannolikhetsbegreppet kan tolkas olika beroende på användningsområde och filosofisk läggning. Vanligast är frekvenstolkningen (sannolikheten $\mathrm{P}(A)$ är den relativa frekvensen av $A$, dvs. hur ofta $A$ förekommer vid repeterade slumpmässiga försök) och subjektiva tolkningen (sannolikheten $\mathrm{P}(A)$ motsvarar hur "troligt" vi anser att det är att $A$ inträffar).

Notera att $P(A)$ inte är en vanlig funktion (dvs. en funktion som tar ett tal eller vektor som argument och ger ett annat tal ut) eftersom den tar en delmängd av $\Omega$ som argument. En sådan funktion kallar för en mängdfunktion.

\section{Kolmogorovs axiomsystem}

Oavsett tolkning vill vi att sannolikhetsmåttet $\mathrm{P}(A)$ är logiskt sammanhängande, så vi kräver att (i) $0 \leq \mathrm{P}(A) \leq 1$,

(ii) $\mathrm{P}(\Omega)=1$, och

(iii) om $A_{1}, A_{2}, \ldots$ är en samling parvis oförenliga händelser (dvs. $A_{i} \cap A_{j}=\varnothing$ för alla i,j) så har vi att

$$
P\left(A_{1} \cup A_{2} \cup \cdots\right)=P\left(A_{1}\right)+P\left(A_{2}\right)+\cdots .
$$

Det sista axiomet kallas uppräknelig additivitet. Ett specialfall av axiom (iii) är att $\mathrm{P}(A \cup B)=\mathrm{P}(A)+\mathrm{P}(B)$ förutsatt att $A \cap B=\varnothing$. Sammantaget bildar dessa Kolmogorovs axiomsystem och ligger till grunden för mycket av sannolikhetsteorin.

Utöver tolkningarna vi såg i föregående föreläsning finns det en annan tolknings av sannolikhetsbegreppet som kan underlätta intuitionen: masstolkningen. I detta fall tolkar vi $\Omega$ som en delmängd i tre eller två dimensioner och vilket gör att $A \subset \Omega$ också är en delmängd i ett sådant rum. Vi tolkar nu $\mathrm{P}(A)$ som volymen eller arean relativt $\Omega$. Givet konstant densitet är denna då proportionerlig mot massan av $A$. Omvänt kan vi säga att om vi tar massan av $A$ och delar med massan av $\Omega$ så får vi $\mathrm{P}(A)$. Om vi nu väljer en godtycklig punkt på måfå i $\Omega$ så hamnar vi i delmängden $A$ med sannolikhet $P(A)$. (Vi kan visualisera detta som att vi kastar en pil på mängden $\Omega$ och "träffar" delmängden med en viss sannolikhet.)

Vi kan nu visa ett par enkla satser.

Sats 1. (Komplementsatsen) $P\left(A^{*}\right)=1-P(A)$

Bevis. Eftersom $A$ och $A^{*}$ är oförenliga $\left(A \cap A^{*}=\varnothing\right)$ har vi att

$$
\mathrm{P}\left(A \cup A^{*}\right)=\mathrm{P}(A)+\mathrm{P}\left(A^{*}\right),
$$

men $A \cup A^{*}=\Omega$, så $\mathrm{P}\left(A \cup A^{*}\right)=\mathrm{P}(\Omega)=1$, vilket ger $\mathrm{P}\left(A^{*}\right)=1-\mathrm{P}(A)$.

Följdsats 2. $P(\varnothing)=0$

Bevis. Sätt $A=\Omega$. Då är $A^{*}=\varnothing$ och vi får $\mathrm{P}(\varnothing)=1-\mathrm{P}(\Omega)=0$.

![](https://cdn.mathpix.com/cropped/2022_11_15_80366f91bd85ffafac6cg-02.jpg?height=447&width=876&top_left_y=1869&top_left_x=619)

Sats 3. (Additionssatsen) $P(A \cup B)=P(A)+P(B)-P(A \cap B)$

Bevis. Satsen gäller trivialt då $A$ och $B$ är oförenliga eftersom vi då har $\mathrm{P}(A \cap B)=$ $P(\varnothing)=0$ och kan tillämpa axiom (iii). Problemet är alltså när $A \cap B \neq \varnothing$. Om vi ritar upp venndiagrammet ovan och ser att när vi tar summan $\mathrm{P}(A)+\mathrm{P}(B)$ så har vi räknat $\mathrm{P}(A \cap B)$ "dubbelt". Det är detta som vi måste korrigera för när vi vill beräkna $P(A \cup B)$

Ett sätt att utnyttja axiom (iii) är att skriva om $A \cup B$ som en annan union av två delmängder som är oförenliga. Om vi betraktar Venndiagrammet ovan ser vi att ett alternativ skulle kunna vara $A \cup\left(A^{*} \cap B\right)$, eftersom $A \cap\left(A^{*} \cap B\right)=\left(A \cap A^{*}\right) \cap B=\varnothing \cap B=$ $\varnothing$. Låt oss visa att detta ger samma händelse med hjälp av räknereglerna.

Enligt unionens distributivitet har vi

$$
A \cup\left(A^{*} \cap B\right)=\left(A \cup A^{*}\right) \cap(A \cup B)=\Omega \cap(A \cup B)=A \cup B,
$$

där vi har använt att $A \cup A^{*}=\Omega$ och snittet mellan $\Omega$ och en godtycklig händelse är händelsen själv ( $\Omega$ inträffar alltid). Unionen av $A$ och $B$ kan alltså ersättas med unionen av $A$ och $A^{*} \cap B, B$ med $A$ borttaget (kan också skrivas $B \backslash A$ ). Enligt axiom (iii) har vi då

$$
\mathrm{P}(A \cup B)=\mathrm{P}\left(A \cup\left(A^{*} \cap B\right)\right)=\mathrm{P}(A)+\mathrm{P}\left(A^{*} \cap B\right) .
$$

Det återstår alltså att beräkna $\mathrm{P}\left(A^{*} \cap B\right)$.

Ȧterigen betraktar vi Venndiagrammet. Det ser ut som att $B$ kan delas upp i två disjunkta delmängder (dvs. två oförenliga händelser): $A^{*} \cap B$ och $A \cap B$. Låt oss visa att detta stämmer.

Vi har alltså

$$
(A \cap B) \cup\left(A^{*} \cap B\right)=\left(A \cup A^{*}\right) \cap B=\Omega \cap B=B
$$

där vi återigen använt distributionsregeln för snitt samt att $A \cup A^{*}=\Omega$ och att snittet mellan $\Omega$ och godtycklig händelse ger samma händelse igen. Enligt axiom (iii) har vi då, eftersom $(A \cap B) \cap\left(A^{*} \cap B\right)=\left(A \cap A^{*}\right) \cap(B \cap B)=\varnothing \cap B=\varnothing$,

$$
\mathrm{P}(B)=\mathrm{P}\left((A \cap B) \cup\left(A^{*} \cap B\right)\right)=\mathrm{P}(A \cap B)+\mathrm{P}\left(A^{*} \cap B\right),
$$

dvs. att

$$
\mathrm{P}\left(A^{*} \cap B\right)=\mathrm{P}(B)-\mathrm{P}(A \cap B) .
$$

Om vi stoppar in detta i uttrycket för $P(A \cup B)$ får vi den sökta identiteten.

Notera att i beviset ovan så använde vi Venndiagrammet för att bygga upp intuitionen, men sedan tillämpade axiomen och mängdlärans räkneregler för att visa att intuitionen stämde.

Följdsats 4. (Booles olikhet) $P(A \cup B) \leq P(A)+P(B)$

Bevis. Tillämpa additionssatsen och axiom (i) som ger att $\mathrm{P}(A \cap B) \geq 0$.

Man kan generalisera både additionssatsen och Booles olikhet till tre eller flera händelser med hjälp av induktion. 

\section{Den klassiska sannolikhetsdefinitionen}

Antag att utfallsrummet $\Omega$ är ändligt med $m$ möjliga utfall $\omega_{1}, \omega_{2}, \ldots, \omega_{m}$. Ett naturligt sätt att definiera en sannolikhetsfunktion är då att anta att varje utfall har samma sannolikhet:

$$
\mathrm{P}\left(\left\{\omega_{1}\right\}\right)=\mathrm{P}\left(\left\{\omega_{2}\right\}\right)=\cdots=\mathrm{P}\left(\left\{\omega_{m}\right\}\right)=1 / m .
$$

Sannolikhetsmåttet $P$ kallas då det likformiga sannolikhetsmåttet över $\Omega$. Denna situation uppstår ofta på grund av symmetrier (hos mynt, tärningar, dragning av kort, osv.) eller när det inte finns någon anledning att ett utfall är troligare än ett annat (den så kallade likgiltighetsprincipen).

Låt oss anta att vi har någon händelse $A \subset \Omega$. Sannolikheten $\mathrm{P}(A)$ beror då endast på hur många utfall som $A$ består av:

$$
\begin{array}{rlr}
\mathrm{P}(A) & =\sum_{\omega \in A} \mathrm{P}(\{\omega\}) \quad \text { (enskilda utfall är oförenliga) } \\
& =\sum_{\omega \in A} \frac{1}{m}=\frac{|A|}{m}
\end{array}
$$

Om vi betecknar antalet utfall i $|A|$ med $g$, dvs. antalet gynnsamma utfall får vi formeln

$$
\mathrm{P}(A)=\frac{g}{m} \text {. }
$$

Detta brukar kallas den klassiska sannolikhetsdefinitionen. Tekniskt sett är det inte en definition utan en konsekvens av det likformiga sannolikhetsmåttet, men vi kallar det för den klassiska sannolikhetsdefinitionen av historiska skäl.

\section{Kombinatorik}

För att få fram intressanta värden på $m$ och $g$ behöver vi ett par verktyg för att räkna utfall (eller val, som vi kommer att se strax). Dessa härstammar från kombinatorik, som omfattar ett helt forskningsfält inom matematiken. Vi kommer att nöja oss med ett par enkla formler för dragning av element ur en mängd, vilket kan göras på ett par olika sätt.

Antag först att vi måste göra ett antal val, ett efter varandra. I det första valet har vi $n_{1}$ alternativ och i det andra har vi $n_{2}$ alternativ. På en restaurang kanske vi har $n_{1}$ stycken förrätter att välja på och $n_{2}$ stycken efterrätter. Det totala antalet möjliga alternativ (beställningar i restaurangen) är då $n_{1} n_{2}$. Med tre val har vi på samma sätt $n_{1} n_{2} n_{3}$ om det tredje valet innefattar $n_{3}$ alternativ. Denna formel kan generaliseras till godtyckligt antal val och kallas multiplikationsprincipen. 

![](https://cdn.mathpix.com/cropped/2022_11_15_80366f91bd85ffafac6cg-05.jpg?height=436&width=469&top_left_y=210&top_left_x=492)

Låt oss nu anta att vi har en mängd med $n$ element. Det finns $n$ sätt att välja ett element ur mängden. Vi skriver ner vilket element vi valde och lägger tillbaka det. Om vi nu väljer ett andra element finns det återigen $n$ sätt att välja det på. Vi skriver ner vilket element och lägger tillbaka det. Sedan fortsätter vi tills vi har en lista med $k$ element.

![](https://cdn.mathpix.com/cropped/2022_11_15_80366f91bd85ffafac6cg-05.jpg?height=393&width=1090&top_left_y=1007&top_left_x=447)

Antalet sätt vi kan välja $k$ element från en mängd med $n$ element förutsatt att vi lägger tillbaka elementet varje gång är då

$$
\underbrace{n \cdot n \cdots \cdots n}_{k \text { gånger }}=n^{k},
$$

enligt multiplikationsprincipen eftersom vi har $n$ alternativ varje gång vi väljer. Notera att detta förutsätter att ordningen spelar roll i vår lista, dvs. att en lista med samma element i en annan ordning räknas som ett annat "val". Detta förfarande kallas därför för dragning med återläggning av k element ur $n$ med hänsyn till ordning.

![](https://cdn.mathpix.com/cropped/2022_11_15_80366f91bd85ffafac6cg-05.jpg?height=474&width=918&top_left_y=2072&top_left_x=430)

Om vi inte lägger tillbaka ett element efter att vi dragit det från mängden får vi ett annat totalt antal alternativ. I detta fall har vi först $n$ val, sedan $n-1$ val, sedan $n-2$ val, osv. tills vi har endast $n-k+1$ val (sista gången har vi samlat på oss $k-1$ element, så det finns $n-k+1$ kvar i mängden). Detta ger totalt

$$
n \cdot(n-1) \cdots(n-k+1)
$$

antal sätt. Notera att ordningen vi väljer elementen fortfarande spelar roll. Detta förfarande kallas dragning utan återläggning av $k$ element ur $n$ med hänsyn till ordning.

Ovanstående formel kan skrivas om med hjälp av fakultetsnotationen

$$
n !=n \cdot(n-1) \cdots \cdot 2 \cdot 1,
$$

vilket ger totalt

$$
\frac{n !}{(n-k) !}
$$

sätt för dragning utan återläggning med hänsyn till ordning. Denna formel kan vara användbar för att förenkla vissa resultat men man ska akta sig för att använda den i numeriska sammanhang - $n$ ! är ett väldigt stort tal även för små $n$ och kan skapa precisionsproblem i beräkningar med ändlig precision.

![](https://cdn.mathpix.com/cropped/2022_11_15_80366f91bd85ffafac6cg-06.jpg?height=537&width=1049&top_left_y=1236&top_left_x=424)

En konsekvens av detta är att antalet sätt man kan ordna $n$ element är $n$ ! eftersom detta motsvarar dragning utan återläggning av $n$ element ur $n$ med hänsyn till ordning. Vi kan använda denna formel för att derivera antalet sätt att dra $k$ element ur $n$ med återläggning utan hänsyn till ordning (dvs. vi kan betrakta detta som dragning av en mängd, inte som en lista eller sekvens).

Antag att vi dragit $k$ element ur $n$ med återläggning. Vi vet nu att det finns $k$ ! olika sätt att ordna dessa element. Med andra ord finns det $k$ ! "kopior" av vår lista som kan anses ekvivalenta. Det totala antalet sätt vi kan utföra dragning av $k$ element ur $n$ utan återläggning och utan hänsyn till ordning är då

$$
\frac{n \cdot(n-1) \cdots(n-k+1)}{k !}=\frac{n !}{k !(n-k) !}=\left(\begin{array}{l}
n \\
k
\end{array}\right) \text {. }
$$

Detta tal brukar benämnas antalet kombinationer av $k$ element bland $n$ eller binomialkoefficienten $\left(\begin{array}{l}n \\ k\end{array}\right)$. Ovanstående resonemang fungerar dock inte när det gäller dragning med återläggning utan hänsyn till ordning efter som vi kan få samma element flera gånger. Vi kommer inte att derivera denna formel i kursen.

Exempel 5. Vad är sannolikheten att vi drar fyra kort ur en kortlek och att alla är ess? Vad är sannolikheten att vi drar två kort och båda är ess?

En kortlek har 52 kort varav fyra ess. Vi drar alltså fyra kort från kortleken utan återläggning. Antag först att detta sker utan hänsyn till ordning, vilket är rimligt eftersom vi egentligen bara bryr oss om vilka korten är, inte $i$ vilken ordning de valdes. Det finns då $m=\left(\begin{array}{c}52 \\ 4\end{array}\right)$ sätt att välja fyra kort. Eftersom leken bara har fyra ess finns det bara $g=1$ gynnsamt utfall (eftersom $\left(\begin{array}{l}4 \\ 4\end{array}\right)=1$ ), vilket ger

$P($ av 4 dragna kort är 4 ess $)=\frac{g}{m}=\frac{1}{\left(\begin{array}{c}52 \\ 4\end{array}\right)}=\frac{4 \cdot 3 \cdot 2 \cdot 1}{52 \cdot 51 \cdot 50 \cdot 49}=\frac{1}{270725} \approx 3.96 \cdot 10^{-6}$.

Alternativt kan vi dra korten med hänsyn till ordning. Vi har då $m=52 ! /(52-4) !=$ $52 \cdot 51 \cdot 50 \cdot 49$. Antalet gynnsamma utfall blir då $4 !=4 \cdot 3 \cdot 2 \cdot 1$ eftersom det finns 4! olika sätt att ordna de fyra essen. Sannolikheten blir dock återigen

$$
P(\text { av } 4 \text { dragna kort är } 4 \text { ess })=\frac{g}{m}=\frac{4 \cdot 3 \cdot 2 \cdot 1}{52 \cdot 51 \cdot 50 \cdot 49} \text {. }
$$

Båda modellerna (dragning med eller utan hänsyn till ordning) fungerar i detta fall och ger samma resultat eftersom de speglar samma verkliga förlopp.

Om vi nu drar två kort och gör detta utan hänsyn till ordning får vi $m=\left(\begin{array}{c}52 \\ 2\end{array}\right)$ medan $g=\left(\begin{array}{l}4 \\ 2\end{array}\right)$, vilket ger

$$
P(\text { av } 2 \text { dragna kort är } 2 \text { ess })=\frac{g}{m}=\frac{4 \cdot 3}{2 \cdot 1} \cdot \frac{2 \cdot 1}{52 \cdot 51}=\frac{1}{221} \text {. }
$$

Exempel 6. (Dragning utan återläggning ur en urna) En populär modell inom statistiken är dragning utan återläggning ur en urna. Vi antar att vi har b blåa kulor och $r$ röda kulor i en urna och drar $n$ kulor från denna utan återläggning. Vad är sannolikheten att vi erhåller $k$ blåa kulor?

![](https://cdn.mathpix.com/cropped/2022_11_15_80366f91bd85ffafac6cg-07.jpg?height=666&width=1157&top_left_y=1884&top_left_x=495)

Antalet möjliga utfall är $m=\left(\begin{array}{c}b+r \\ n\end{array}\right)$ eftersom det totala antalet kulor är $b+r$. När det gäller antalet gynnsamma utfall så måste vi tänka på att det är antalet blåa kulor som räknas, inte vilka specifika kulor vi drar. Från det perspektivet finns det $\left(\begin{array}{l}b \\ k\end{array}\right)$ sätt att välja $k$ blåa kulor ur urnan. De resterande $n-k$ kulor måste dras från de r röda kulorna, vilket kan göras på $\left(\begin{array}{c}r \\ n-k\end{array}\right)$ sätt. Multiplikationsprincipen ger då totalt $g=\left(\begin{array}{c}b \\ k\end{array}\right)\left(\begin{array}{c}r \\ n-k\end{array}\right)$ gynnsamma fall och vi får

![](https://cdn.mathpix.com/cropped/2022_11_15_80366f91bd85ffafac6cg-08.jpg?height=177&width=882&top_left_y=578&top_left_x=616)

Exempel 7. Vi kan modellera dragning av kort ur en kortlek som dragning ur en urna. Låt oss återgå till sannolikheten att dra fyra ess ur kortleken. I urnmodellen ovan har vi då att blått motsvarar ess och rött motsvarar icke-ess, vilket ger $b=4$, $r=48$. Fallen som diskuterades $i$ det föregående exemplet är då $n=k=4$ och $n=k=2$.

Vi kan också betrakta fallet att vi drar fyra kort men att bara två är ess, vilket då ger $n=4, k=2$ och har sannolikhet

$$
P(a v 4 \text { dragna kort är } 2 \text { ess })=\frac{\left(\begin{array}{c}
4 \\
2
\end{array}\right)\left(\begin{array}{c}
48 \\
2
\end{array}\right)}{\left(\begin{array}{c}
52 \\
4
\end{array}\right)}=\frac{1}{40}=0.025 \text {. }
$$

Exempel 8. (Dragning med återläggning ur en urna) En variant på den ovanstående modellen fås om vi lägger tillbaka varje kula innan vi drar en ny. Det finns då $m=(b+r)^{n}$ möjliga utfall (vid varje dragning finns $b+r$ olika kulor $i$ urnan).

Nu finns det flera sätt vi kan erhålla k blåa kulor utav de $n$ vi dragit. Vi skulle kunna först dra k blåa kulor, sedan $n-k$ röda. Eller skulle vi kunna dra en blå kula, sedan en röd, sedan $k-1$ blåa kulor och sedan $n-k-2$ röda kulor, osv. Totalt sett finns det då $\left(\begin{array}{l}n \\ k\end{array}\right)$ olika sekvenser av blåa och röda kulor. Vi kan också se detta som att av n möjliga "positioner" i dragningssekvensen så väljer vi k stycken för de blåa.

Varje sådan sekvens kan innehålla olika distinkta kulor från urnan. Mer konkret kan vi välja de blåa kulorna på b $b^{k}$ sätt och de röda på $r^{n-k}$ sätt. Enligt multiplikationsprincipen får vi då $g=\left(\begin{array}{l}n \\ k\end{array}\right) b^{k} r^{n-k}$, vilket ger

$$
P(a v n \text { med återläggning dragna kulor är } k \text { blåa })=\frac{\left(\begin{array}{l}
n \\
k
\end{array}\right) b^{k} r^{n-k}}{(b+r)^{n}} \text {. }
$$

\section{Betingade sannolikheter}

Om vi vet att en händelse redan inträffat, vad kan vi då säga om en annan händelses sannolikhet? Med andra ord, vad är sannolikheten av $A$ givet att $B$ inträffat? Detta kallas en betingad sannolikhet och betecknas $P(A \mid B)$ (läses "sannolikheten av $A$ givet $B^{\prime \prime}$ ). Vi kan till exempel betrakta sannolikheten att det har regnat under de senaste dygnet givet att trottoaren är våt. Ett annat exempel är sannolikheten att ett diagnostiskt test ger ett positivt svar givet att patienten är sjuk.
![](https://cdn.mathpix.com/cropped/2022_11_15_80366f91bd85ffafac6cg-09.jpg?height=1160&width=1050&top_left_y=392&top_left_x=662)

Vad för egenskaper söker vi hos $\mathrm{P}(A \mid B)$ ? Om $A \cap B=\varnothing$ så borde vi ha $\mathrm{P}(A \mid B)=0$ eftersom att $B$ inträffar gör det omöjligt för $A$ att inträffa. Om $A \subset B$ borde $\mathrm{P}(A \mid B)$ vara större än noll och rimligtvis större än $P(A)$ eftersom vi har vet att $A$ utgör en större del av $B$ jämfört med $\Omega$. Àt andra hållet har vi att $P(B \mid A)$ borde vara ett eftersom $B$ måste inträffa när $A$ redan inträffat. Om ingetdera gäller, dvs. att $A \cap B \neq$ $\varnothing$ och $A \cap B^{*} \neq \varnothing$, borde $\mathrm{P}(A \mid B)$ bero på $\mathrm{P}(A \cap B)$ eftersom delen av $A$ utanför $B$, dvs. $A \cap B^{*}$ inte kan inträffa.

En naturlig definition som har dessa egenskaper är

$$
\mathrm{P}(A \mid B)=\frac{\mathrm{P}(A \cap B)}{\mathrm{P}(B)}
$$

vilket också är hur betingade sannolikheter definieras Det är alltså kvoten mellan sannolikheten att både $A \cap B$ inträffar och sannolikheten att $B$ inträffar - man kan se detta som en relativ sannolikhet.

Notera att $P(A \mid B)$ som sannolikhetsmått, med $B$ fixt, uppfyller alla tre av Kolmogorovs axiom. Med andra ord har vi $\mathrm{P}(A \mid B) \geq 0, \mathrm{P}(B \mid B)=1$ ( $B$ ersätter $\Omega$ som utfallsrum när vi betingar med avseende på $B)$ och $\mathrm{P}(A \cup C \mid B)=\mathrm{P}(A \mid B)+\mathrm{P}(C \mid B)$ om $A \cap C=\varnothing$. En konsekvens av detta är att alla satser vi bevisat för vanliga (obetingade) sannolikhetsmått också gäller för betingade sannolikheter, så länge vi håller den betingade händelsen $B$ fixt. Till exempel har vi att $\mathrm{P}\left(A^{*} \mid B\right)=1-\mathrm{P}(A \mid B)$ och $\mathrm{P}(A \cup C \mid B)=\mathrm{P}(A \mid B)+\mathrm{P}(C \mid B)-\mathrm{P}(A \cap C \mid B)$

Två användbara omformuleringar är

$$
\mathrm{P}(A \cap B)=\mathrm{P}(A \mid B) \mathrm{P}(B) \text { och } \mathrm{P}(A \cap B)=\mathrm{P}(B \mid A) \mathrm{P}(A) .
$$

Sannolikheten att $A$ och $B$ båda inträffar är alltså lika med sannolikheten att $B$ inträffar gånger sannolikheten att $A$ inträffas givet $B$ (och vice versa).

Exempel 9. Låt oss återigen beräkna sannolikheten att vi drar fyra ess från en kortlek, men den här gången med hjälp av betingade sannolikheter.

Låt $A_{i}$ beteckna händelsen att det i:te kortet vi drar är ett ess. Vi har då för det första kortet att det finns 4 ess att välja från och 52 kort totalt i leken, vilket ger

$$
P\left(A_{1}\right)=4 / 52 \text {. }
$$

Efter att vi har dragit det första esset finns det 51 kort kvar i leken, varav 3 är ess. Detta ger

$$
P\left(A_{2} \mid A_{1}\right)=3 / 51 \text {. }
$$

Vidare har vi

$$
P\left(A_{3} \mid A_{1} \cap A_{2}\right)=2 / 50 \text { och } P\left(A_{4} \mid A_{1} \cap A_{2} \cap A_{3}\right)=1 / 49 \text {. }
$$

Den sökta sannolikheten är nu $P\left(A_{1} \cap A_{2} \cap A_{3} \cap A_{4}\right)$, vilket kan beräknas som

$$
\begin{aligned}
P\left(A_{1} \cap A_{2} \cap A_{3} \cap A_{4}\right) &=P\left(A_{4} \mid A_{1} \cap A_{2} \cap A_{3}\right) P\left(A_{1} \cap A_{2} \cap A_{3}\right) \\
&=P\left(A_{4} \mid A_{1} \cap A_{2} \cap A_{3}\right) P\left(A_{3} \mid A_{1} \cap A_{2}\right) P\left(A_{1} \cap A_{2}\right) \\
&=P\left(A_{4} \mid A_{1} \cap A_{2} \cap A_{3}\right) P\left(A_{3} \mid A_{1} \cap A_{2}\right) P\left(A_{2} \mid A_{1}\right) P\left(A_{1}\right) \\
&=\frac{1}{49} \cdot \frac{2}{50} \cdot \frac{3}{51} \cdot \frac{4}{52} \\
&=\frac{1}{270725},
\end{aligned}
$$

dvs. samma resultat som innan.

Betingade sannolikheter kan vara kniviga att ha att göra med. Se, till exempel, Monty Hall-problemet och trefångarsproblemet. Iaktta därför stor försiktighet vid hantering av betingade sannolikheter (skriv upp alla möjliga utfall, rita venndiagrammet, sätta upp sanningsvärdestabeller, osv.).

Antag nu att vi kan dela upp utfallsrummet $\Omega$ i ett antal händelser $H_{1}, H_{2}, \ldots H_{n}$ som är parvis oförenliga (dvs. att $H_{i} \cap H_{j}=\varnothing$ för alla $i$, j) och $H_{1} \cup H_{2} \cup \cdots \cup H_{n}=\Omega$. Detta kallas en partition av $\Omega$. Kan se detta som en samling hypoteser i vår modell där bara en av hypoteserna kan stämma. I så fall kan $P(A)$ (den obetingade sannolikheten för $A)$ att skrivas med hjälp av de betingade sannolikheterna $\mathrm{P}\left(A \mid H_{1}\right), \mathrm{P}\left(A \mid H_{2}\right), \ldots, \mathrm{P}\left(A \mid H_{n}\right)$ 

![](https://cdn.mathpix.com/cropped/2022_11_15_80366f91bd85ffafac6cg-11.jpg?height=488&width=832&top_left_y=209&top_left_x=641)

Sats 10. (Lagen om total sannolikhet) Låt $H_{1}, H_{2}, \ldots, H_{n}$ bilda en partition av $\Omega$. Då gäller

$$
P(A)=\sum_{i=1}^{n} P\left(A \mid H_{i}\right) P\left(H_{i}\right) .
$$

Bevis. Eftersom $A \cap \Omega=A$ har vi att $A=A \cap \bigcup_{i=1}^{n} H_{i}=\bigcup_{i=1}^{n}\left(A \cap H_{i}\right)$ genom distributivitet. Händelserna i denna union är oförenliga $\left(\left(A \cap H_{i}\right) \cap\left(A \cap H_{j}\right)=A \cap\left(H_{i} \cap H_{j}\right)=\varnothing\right)$, så vi kan använda axiom (iii), vilket ger

$$
\mathrm{P}(A)=\mathrm{P}\left(\bigcup_{i=1}^{n}\left(A \cap H_{i}\right)\right)=\sum_{i=1}^{n} \mathrm{P}\left(A \cap H_{i}\right)=\sum_{i=1}^{n} \mathrm{P}\left(A \mid H_{i}\right) \mathrm{P}\left(H_{i}\right),
$$

där vi i sista ledet använt definitionen av $\mathrm{P}\left(A \mid H_{i}\right)$.

Ofta har vi tillgång till en viss betingad sannolikhet $\mathrm{P}(A \mid B)$ men är intresserad av den omvända, dvs. $\mathrm{P}(B \mid A)$. Vi kanske känner till sannolikheten att marken är våt givet att det har regnat under de senaste dygnet (avdunstningen sker enligt en viss känd process) men är intresserad av betingningen åt andra hållet: sannolikheten att det har regnat under det senaste dygnet givet att marken är våt. Genom att flytta om termerna i identiteten $\mathrm{P}(A \cap B)=\mathrm{P}(A \mid B) \mathrm{P}(B)=\mathrm{P}(B \mid A) \mathrm{P}(A)$ får vi

$$
\mathrm{P}(B \mid A)=\frac{\mathrm{P}(A \mid B) \mathrm{P}(B)}{\mathrm{P}(A)} .
$$

Denna formel kallas Bayes sats eller Bayes regel.

Det viktiga att notera här är hur $\mathrm{P}(A)$ och $\mathrm{P}(B)$ spelar in. Låt oss anta att det är mycket sannolikt att marken är våt $(A)$ givet att det regnat under det senaste dygnet $(B)$, dvs. att $P(A \mid B)$ är stort (nära ett). Detta behöver inte nödvändigtvis betyda att $P(B \mid A)$ också är stort. Vi kanske befinner oss i Atacamaöknen och har därför ett $P(B)$ nära noll. Alternativt kanske står mitt i ett konstbevattnat vetefält, vilket ger ett $\mathrm{P}(A)$ nära ett. I båda fallen får vi att $\mathrm{P}(B \mid A)$ är liten. Med andra ord kan vi inte med stor säkerhet konstatera att det har regnat bara för att marken är våt i dessa fall, vilket verkar rimligt.

Vi kan generalisera formeln ovan med hjälp av en partition av $\Omega$. Sats 11. (Bayes sats) Givet en partition $H_{1}, H_{2}, \ldots, H_{n}$ av $\Omega$ har vi

$$
P\left(H_{i} \mid A\right)=\frac{P\left(A \mid H_{i}\right) P\left(H_{i}\right)}{\sum_{j=1}^{n} P\left(A \mid H_{j}\right) P\left(H_{j}\right)} .
$$

Exempel 12. (Sensitivitet och specificitet av diagnostiskt test) Diagnostiska test för olika sjukdomar brukar utvärderas med avseende på deras sensitivitet, sannolikheten att testet ger ett positivt svar för en person som har sjukdomen, och specificitet, sannolikheten att testet ger ett negativt svar för en person som inte har sjukdomen. Om vi betecknar händelsen att personen har sjukdomen med $A$ och ett positivt testsvar med $B$ ser vi att sensitiviteten motsvarar $P(B \mid A)$ och specificiteten motsvarar $P\left(B^{*} \mid A^{*}\right)$.

Antag att ett $P C R$-test för covid-19 har sensitivitet $P(B \mid A)=0.9$ och specificitet $P\left(B^{*} \mid A^{*}\right)=0.995$. Om en person tar testet och får ett positivt provsvar, vad är då sannolikheten att personen har sjukdomen?

Tyvärr kan vi inte svara på denna fråga utan en till variabel: sannolikheten $P(A)$ att personen har sjukdomen över huvudtaget. Om personen vid tidpunkten för testet befann sig i Sverige i slutet av maj 2020 beräknades prevalensen av covid-19 bland befolkningen vara $0.3 \%, d v s . P(A)=0.003$. Bayes sats ger då

$$
P(A \mid B)=\frac{P(B \mid A) P(A)}{P(B \mid A) P(A)+P\left(B \mid A^{*}\right) P\left(A^{*}\right)}=\frac{0.9 \cdot 0.003}{0.9 \cdot 0.003+(1-0.995)(1-0.003)} \approx 0.35,
$$

eftersom $P\left(B \mid A^{*}\right)=1-P\left(B^{*} \mid A^{*}\right)$. Ett positivt testsvar ger då ungefär $35 \%$ sannolikhet att personen har sjukdomen.

I slutet av april 2020 beräknades prevalensen vara runt $0.9 \%$, vilket $\operatorname{ger} P(A)=$ 0.009. Detta skulle då ge

$$
P(A \mid B)=\frac{0.9 \cdot 0.009}{0.9 \cdot 0.009+(1-0.995)(1-0.009)} \approx 0.62 .
$$

Här ger alltså ett positivt testsvar sannolikheten $62 \%$ att personen är sjuk.