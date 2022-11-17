\title{
Föreläsning åtta
}

\author{
Joakim Andén
}

21 november 2022

\section{Approximation av fördelningar}

En tillämpning av centrala gränsvärdessatsen som vi presenterade i föregående föreläsning är för att approximera några av de föreläsningar vi sett tidigare. Låt först $X \sim \operatorname{Bin}(n, p)$. Vi har sett att $X$ kan skrivas som en summa av $n$ stycken oberoende och likafördelade stokastiska variabler $Y_{1}, Y_{2}, \ldots, Y_{n}$ med $Y_{i} \sim \operatorname{Ber}(p)$. Utfallet $Y_{i}=1$ motsvarar att det $i$ :te försöket lyckades medan $Y_{i}=0$ betyder att det misslyckades. Summan $X=Y_{1}+Y_{2}+\ldots Y_{n}$ är då det totala antalet lyckade försök, vilket har fördelning $\operatorname{Bin}(n, p)$. Detta håller eftersom $\operatorname{Bin}(1, p)=\operatorname{Ber}(p)$ och summan $U+V$ av två binomialfördelade stokastiska variabler $U \sim \operatorname{Bin}(n, p)$ och $V \sim \operatorname{Bin}(m, p)$ har fördelningen Bin( $n+m, p)$ (tillämpning av den diskreta faltningsformeln).

Från detta fick vi att $\mathrm{E}[X]=\mathrm{E}\left[Y_{1}\right]+\mathrm{E}\left[Y_{2}\right]+\ldots+\mathrm{E}\left[Y_{n}\right]=p+p+\ldots+p=n p$ samt att $\mathrm{V}[X]=\mathrm{V}\left[Y_{1}\right]+\mathrm{V}\left[Y_{2}\right]+\ldots+\mathrm{V}\left[Y_{n}\right]=p(1-p)+p(1-p)+\ldots+p(1-p)=n p(1-p)$ eftersom $Y_{1}, Y_{2}, \ldots, Y_{n}$ är oberoende. Från $V[X]=n p(1-p)$ får vi då att $D[X]=$ $\sqrt{n p(1-p)}$

En annan konsekvens av denna uppdelning är att vi kan tillämpa den centrala gränsvärdessatsen för $n$ stort. Då har vi att $X$ approximativt har fördelningen $N(E[X], D[X])=$ $N(n p, \sqrt{n p(1-p)})$. Hur bra approximationen är beror så klart på vad man ska ha den till, men en tumregel är att den håller ganska bra då $n p(1-p) \geq 10$.

Denna approximation kan vara bra att ha för att beräkna sannolikheter som rör binomialfördelningar. $\operatorname{Om} X \sim \operatorname{Bin}(215,0.6)$, till exempel, så kanske vi vill beräkna $\mathrm{P}(X \leq 120)$. Då har vi

$$
\mathrm{P}(x \leq 120)=\sum_{x=0}^{120} p_{x}(x)=\sum_{x=0}^{120}\left(\begin{array}{c}
215 \\
x
\end{array}\right) 0.6^{x} 0.4^{215-x} .
$$

Detta går att beräkna, men det är inte lätt och kräver ofta tillgång till dator och en del tålamod. Om vi istället använder normalapproximationen ovan får vi att $E[X]=$ $215 \cdot 0.6=129$ samt $D[X]=\sqrt{215 \cdot 0.6 \cdot 0.4} \approx 7.18$. Vi har då att $X$ är approximativt $N(129,7.18)$-fördelad, vilket då ger

$$
\begin{aligned}
P(X \leq 120) &=P\left(\frac{X-129}{7.18} \leq \frac{120-129}{7.18}\right) \\
& \approx P((Z \leq-1.25)=\Phi(-1.25)=1-\Phi(1.25) \approx 0.1006,
\end{aligned}
$$

där $Z \sim N(0,1)$.

En annan (och ännu mer användbar) tillämpning är för att beräkna kvantiler. Låt oss säga att i fallet ovan vi söker ett värde $x$ så att $\mathrm{P}(X>x)=0.10$. Detta fås då genom

$$
\begin{aligned}
\mathrm{P}(X>x) &=\mathrm{P}\left(\frac{X-129}{7.18}>\frac{x-129}{7.18}\right) \\
& \approx \mathrm{P}\left(Z>\frac{x-129}{7.18}\right)=0.10 .
\end{aligned}
$$

Detta uppfylls då genom att sätta $(x-129) / 7.18=\lambda_{0.10}$ eftersom $\mathrm{P}\left(Z>\lambda_{0.10}\right)=$ $0.10$. Alltså har vi den approximativa $0.10-\mathrm{kvantilen} x=129+7.18 \lambda_{0.10} \approx 129+$ $7.18 \cdot 1.28 \approx 138.2$.

Vi kan härleda liknande relationer för Poissonfördelningen. Låt $X \sim \operatorname{Bin}(\mu)$. När vi härledde Poissonfördelningen såg vi att den kunde approximeras av $\operatorname{Bin}(n, \mu / n)$ för stort $n$. Vi fick detta från Poissonmodellen där $X$ är antalet händelser som inträffar i intervallet $[0,1]$ givet att händelserna inträffar oberoende av varandra och att en händelse inträffar på intervallet $[t, t+h]$ med sannolikhet $h$ för små $h$. Binomialapproximation fås då genom att dela upp intervallet $[0,1]$ i $n$ lika stora delar, där var och en har sannolikhet $\mu / n$ att innehålla en händelse.

Om vi kopplar ihop denna approximation med centrala gränsvärdessatsen ser vi att $\operatorname{Bin}(n, \mu / n)$ kan approximeras med N $(n \cdot \mu / n, \sqrt{n \cdot \mu / n \cdot(1-\mu / n)})=\mathrm{N}(\mu, \sqrt{\mu(1-\mu / n)}$. För stora $n$ är $\mu / n$ försumbar och vi får approximationen $N(\mu, \sqrt{\mu})$. Med samma tumregel som för normalapproximation av binomialfördelningen får vi att denna approximation stämmer ganska bra då $\mu \geq 10$.

\section{Från sannolikhetsteori till statistik}

Hittills har kursen behandlat sannolikhetsteori, dvs. vi har studerat olika modeller för slumpmässiga förlopp genom begrepp som händelser, sannolikhetsmått och stokastiska variabler. Med hjälp av dessa modeller kan vi bland annat beräkna sannolikheten att ett visst förlopp sker (till exempel att en händelse inträffar eller en stokastisk variabel antar ett visst värde) eller andra relevanta storheter (till exempel väntevärdet och variansen hos en viss stokastisk variabel). Vi utgår alltså från en viss modell och härleder egenskaper hos data som genereras av modellen.

Inom statistiken utgår vi istället från datamängden och försöker dra slutsatser om dessa. I vissa fall gäller det att sammanfatta datapunkterna på olika sätt, vilket kallas beskrivande statistik. I andra fall vill vi bygga en modell för hur datapunkterna har genererats (ofta i form av en fördelning hos en stokastisk variabel), vilket kallas statistisk inferens. Denna kurs kommer att fokusera till stor del på detta senare fall men vi börjar med ett par grundläggande begrepp inom beskrivande statistik då dessa kommer upp ofta också inom inferensen. 

\section{Beskrivande statistik}

Inom den beskrivande statistiken söker vi olika sätt att sammanfatta en viss datamängd

$$
\left\{x_{1}, x_{2}, \ldots, x_{n}\right\} .
$$

Vi behöver inte göra några antaganden gällande datamängdens härkomst (dvs. som utfallen hos en stokastisk variabel), utan är intresserad av datamängden i sig.

En användbar sammanfattning av datapunkterna fås genom histogrammet definierad på klassgränserna $g_{1}, g_{2}, \ldots, g_{m+1}$ som ges av

$$
f_{i}=\left|\left\{j: g_{i} \leq x_{j}<g_{i+1}\right\}\right| \text { för } i=1,2, \ldots, m \text {, }
$$

där beteckningen $|A|$ avser kardinaliteten hos mängden $A$, dvs. antalet element i $A$. Variabeln $f_{i}$ kallas den absoluta frekvensen för klassen $\left[g_{i}, g_{i+1}\right]$ och vi definierar också den relativa frekvensen $p_{i}=f_{i} / n$. Ofta ser vi till att klassbredden $h_{i}=g_{i+1}-g_{i}$ hålls konstant. Värdena för $f_{i}$ eller $p_{i}$ kan sedan plottas i ett stolpdiagram för att få en översikt.

![](https://cdn.mathpix.com/cropped/2022_11_17_2aa4f50f6cb13f62d6d8g-03.jpg?height=637&width=1177&top_left_y=1237&top_left_x=474)

Vi diskuterade tidigare lägesmått, spridningsmått och beroendemått för stokastiska variabler. Dessa har också motsvarigheter för datamängder. Vi kan, till exempel, definiera det aritmetiska medelvärdet (eller stickprovsmedelvärdet)

$$
\bar{x}=\frac{1}{n} \sum_{i=1}^{n} x_{i},
$$

stickprovsvariansen

$$
s^{2}=\frac{1}{n-1} \sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)^{2}
$$

och stickprovets standardavvikelse

$$
s=\sqrt{\frac{1}{n-1} \sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)^{2}} .
$$

(I både stickprovsvariansen och stickprovets standardavvikelse kan vi ersätta $n-1$ med $n$, men det visar sig att $n-1$ är mer gynnsamt från ett inferensperspektiv).

För att förenkla formlerna ovan inför vi beteckningen $Q$ för kvadratsumman kring det aritmetiska medelvärdet

$$
Q=\sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)^{2},
$$

vilket ger $s^{2}=Q /(n-1)$. En trevlig egenskap är att

$$
\begin{aligned}
Q &=\sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)^{2}=\sum_{i=1}^{n} x_{i}^{2}-2 \bar{x} \sum_{i=i}^{n} x_{i}+n \bar{x}^{2} \\
&=\sum_{i=1}^{n} x_{i}^{2}-n \bar{x}^{2}=\sum_{i=1}^{n} x_{i}^{2}-\frac{1}{n}\left(\sum_{i=1}^{n} x_{i}\right)^{2}=\sum_{i=1}^{n} x_{i}^{2}-n \bar{x}^{2} .
\end{aligned}
$$

(Detta kan jämföras med formeln $\mathrm{V}[X]=\mathrm{E}\left[X^{2}\right]-\mathrm{E}[X]^{2}$ för variansen av en stokastisk variabel.)

Vi kan också ha datapunkter som består av par $\left(x_{i}, y_{i}\right)$ och hela datamängden blir då

$$
\left\{\left(x_{1}, y_{1}\right),\left(x_{2}, y_{2}\right), \ldots,\left(x_{n}, y_{n}\right)\right\} .
$$

I detta fall kan vi beräkna stickprovskovariansen

$$
c_{x y}=\frac{1}{n-1} \sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)\left(y_{i}-\bar{x}\right)
$$

och stickprovets korrelationskoefficient

$$
r=\frac{c_{x y}}{s_{x} S_{y}},
$$

där $s_{x}$ och $s_{y}$ syftar på stickprovsstandardavvikelserna för $x$ respektive $y$. Som innan kan vi förenkla summan i $c_{x y}$ som

$$
\sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)\left(y_{i}-\bar{y}\right)=\sum_{i=1}^{n} x_{i} y_{i}-n \overline{x y} .
$$

Avslutningsvis noterar vi att terminologin kan vara lite förvirrande. Vi har alltså definierat begreppen väntevärde, varians och så vidare för en stokastisk variabel $X$. Som vi sett i tidigare föreläsningar kan vi ha en modell med flera oberoende kopior av $X_{1}, X_{2}, \ldots, X_{n}$ av $X$ och beräkna dess aritmetiska medelvärde

$$
\bar{x}=\frac{1}{n} \sum_{i=1}^{n} x_{i},
$$

vilket också är en stokastisk variabel. Vi kommer också att se alldeles strax att det går att beräkna en stickprovsvarians utifrån dessa $X_{1}, X_{2}, \ldots, X_{n}$ som även denna är en stokastisk variabel.

Medelvärdena, varianserna och så vidare som vi definierat i denna del avser som sagt datamängder, och det finns en viktig länk här. Värdena som tillhör datamängden kan nämligen ses som utfall av deras stokastiska motparter. Till exempel kan $\bar{x}$ ses som ett utfall av $\bar{X}$. Strikt sett behöver inte detta vara fallet inom den beskrivande statistiken (eftersom den endast förhåller sig till datamängder), men det kan vara bra att veta hur kopplingen ser ut.

Vi kan också beräkna kvantiler på datamängden. Om vi sorterar värdena $x_{1}, x_{2}, \ldots, x_{n}$ och benämner de sorterade värdena $x_{(1)}, x_{(2)}, \ldots, x_{(n)}$ så har vi att det minsta värdet är $\min \left(x_{1}, x_{2}, \ldots, x_{n}\right)=x_{(1)}$ och det största värdet är $\max \left(x_{1}, x_{2}, \ldots, x_{n}\right)=x_{(n)}$. Vi kan då definiera $\alpha-k v a n t i l e n \tilde{x}_{\alpha} \operatorname{som} x_{(n-\lfloor\alpha n\rfloor)}$ där $\lfloor a\rfloor$ är a rundat nedåt. Det finns alternativa definitioner för dessa kvantiler som interpolerar mellan olika värden i de fall $\alpha n$ inte är ett heltal. När $n$ är tillräckligt stort ger alla dessa definitioner i stort sett samma resultat, så vi håller oss till definitionen ovan i kursen (notera att kursboken använder en lite annorlunda definition).

Låt oss anta att vi har en datamängd

$$
x_{1}=0.63, x_{2}=0.14, x_{3}=0.98, x_{4}=0.82, x_{5}=0.61 \text {. }
$$

Vi sorterar denna och får

$$
x_{(1)}=0.14, x_{(2)}=0.61, x_{(3)}=0.63, x_{(4)}=0.82, x_{(5)}=0.98 \text {. }
$$

Enligt formeln ovan har vi $\tilde{x}_{0.50}=x_{(3)}=0.63$ eftersom $5-\lfloor 0.5 \cdot 5\rfloor=5-2=3$. På samma sätt får vi $\tilde{x}_{0.25}=x_{(4)}=0.82$ och $\tilde{x}_{0.75}=x_{(2)}=0.61$. Dessa kvantiler har speciella namn: $\tilde{x}_{0.50}$ kalla medianen, $\tilde{x}_{0.25}$ kallas den övre kvartilen och $\tilde{x}_{0.75}$ kallas den undre kvartilen. Genom att subtrahera den undre kvartilen från den övre fås interkvartilavståndet $\tilde{x}_{0.25}-\tilde{x}_{0.75}$.

Medianer och kvartiler har den bra egenskapen att de i regel är mer robusta mot mycket små eller mycket stora värden. Detta kan jämföras med det aritmetiska medelvärdet som i regel är mer känsligt.

\section{Introduktion till statistisk inferens}

Den grundläggande frågan inom statistisk inferens är: hur kan vi dra olika slutsatser från data? Ofta handlar dessa slutsatser om olika modeller för datamängden eller om olika parametrar för dessa modeller. Generellt antar vi att en stokastisk variabel har en viss fördelning som beror på en viss parameter och använder sedan data för att passa denna parameter.

Låt oss ta som motiverande exempel, en opinionsundersökning. Utav alla röstberättigade individer i Sverige (cirka $7.5$ miljoner människor) väljer vi 1000 stycken och ber dem svara ja eller nej på en viss fråga (till exempel: Borde Sverige begära utträde ur EU?). Antag att 450 av dessa 1000 svarar ja och 550 svarar nej. Vad säger detta om antalet röstberättigade i Sverige, populationen, som skulle svarat samma på den frågan? En viktig fråga att besvara är om proportionen av ja-svar inom populationen överstiger $0.50$, vilket då skulle ge en uppfattning om resultatet vid en folkomröstning.

Låt oss beteckna andelen inom populationen som skulle svara ja som p. Målet är alltså att skatta p. Ett direkt sätt är att helt enkelt beräkna andelen inom vårt stickprov som svarat ja. Vi betecknar detta $p_{\text {obs }}^{\star}$ (notationen kommer att förklaras strax) och får då

$$
p_{\text {obs }}^{\star}=450 / 1000=0.45 \text {. }
$$

För att denna skattning ska vara användbar måste vi veta mera. Hur bra är denna skattning, dvs. hur nära ligger den det "sanna" värdet? Vad skulle hända om vi repeterade undersökningen med ett annat urval av tillfrågade? Skulle svaret skilja sig markant? Hur ser fördelningen på skattningen ut mer allmänt? Om vi återgår till frågan om $p>0.50$ så ligger skattningen $0.45$ ganska nära $0.50$. Ett fel större än $0.05$ skulle då göra opinionsundersökningen relativt värdelös för att förutsäga utfallet av en folkomröstning.

Dessa frågor kan delvis besvaras genom att betrakta en statistisk modell över förloppet. Denna modell utgår från den sökta parametern $p$ och definierar en stokastisk variabel $p^{*}$ som motsvarar vår skattning. Vad utgör källan till slumpmässigheten i denna modell? Urvalet av utfrågade personer. Om vi har otur råkar vi välja 1000 personer som alla svarar ja på frågan (eller som alla svarar nej), men detta är ganska osannolikt.

I regel kan vi betrakta urvalet som dragning från en urna med röda (svar: ja) och blåa (svar: nej) kulor, eftersom identiteten hos personerna inte spelar någon roll utöver deras svar. Vi frågar inte varje person mer en än gång, så det är en dragning utan återläggning. I vårt fall är sannolikheten att dra samma person två gånger så pass liten (eftersom det totala antalet röstberättigade personer, mer än sju miljoner, är stort med avseende på urvalets storlek, ett tusen). Vi kan därför approximera urvalet som dragning med återläggning. Detta ger att antalet positiva svar $X$ har fördelningen Bin $(1000, p$ ). (Dragning utan återläggning skulle istället gett en hypergeometrisk fördelning.)

Vi skattar då $p$ som $p^{\star}=X / 1000$. Notera att detta är en stokastisk variabel eftersom den beror på det slumpmässiga urvalet vi gjort. I det konkreta utfallet vi diskuterade ovan har vi $x=450$, vilket ger $p_{\text {obs }}^{\star}=0.45$, alltså det observerade utfallet av den stokastiska variabeln $p^{\star}$. (Man skulle kunna tro att den vanliga konventionen för stokastiska variabler med stora och små bokstäver skulle gälla här, vilket skulle ge $P^{\star}$ och $p^{\star}$, men så är det tyvärr inte.) Vi kan nu betrakta väntevärdet för $p^{\star}, \mathrm{E}\left[p^{\star}\right]=\mathrm{E}[X] / 1000=1000 p / 1000=p$, eftersom väntevärdet för en $\operatorname{Bin}(n, p)-$ fördelad stokastisk variabel är np. Med andra ord så ligger skattningen i genomsnitt runt det sanna värdet $p$.

Hur ser spridningen ut? En $\operatorname{Bin}(n, p)$-fördelad stokastisk variabel har varians $n p(1-$ p), vilket i detta fall ger

$$
\mathrm{V}\left[p^{\star}\right]=\mathrm{V}\left[\frac{X}{1000}\right]=\frac{\mathrm{V}[X]}{1000^{2}}=\frac{1000 p(1-p)}{1000^{2}}=\frac{p(1-p)}{1000} .
$$

Standardavvikelsen är då $\mathrm{D}\left[p^{\star}\right]=\sqrt{p(1-p) / 1000}$ och beror på den okända parametern $p$. Eftersom vi inte känner till $p$ kan vi betrakta det maximala värdet på standardavvikelsen. I detta fall maximeras standardavvikelsen av $p=0.5$, vilket ger $\mathrm{D}\left[p^{\star}\right]=\sqrt{0.5^{2} / 1000} \approx 0.016$, dvs. ett fel på $1.6 \%$.

Om vi emellertid antar att vår skattning $p_{\text {obs }}^{\star}$ är nära det sanna värdet kan vi använda dess värde istället för $p$. Vi får då $\sqrt{0.45 \times 0.55 / 1000} \approx 0.016$. (Vårt antagande att $p_{\text {obs }}^{\star}$ kan då ses som rimligt då standardavvikelsen är relativt liten.) Vår skattning på 45\% kan då anses som någorlunda korrekt, med en approximativ standardavvikelse på $1.6 \%$. Vi ser att skattningen $p_{\text {obs }}^{\star}=0.45$ så pass nära det värde $p=0.50$ som ger maximal standardavvikelse att denna approximation inte gör så stor skillnad, men så är inte alltid fallet (i vissa skattningar kan standardavvikelsen bli godtyckligt stor).

\section{Punktskattning}

Låt oss nu formalisera och generalisera metoden ovan så att vi kan tillämpa den på andra problem. Allmänt har vi en stokastisk variabel $X$ med en okänd fördelning. Ofta vet vi att fördelningen tillhör en viss familj men har en okänd parameter (som ovan, där $X$ var binomialfördelad med okänd parameter p). Oavsett beror på på någon parameter $\theta$ i något parameterrum $\Sigma_{\theta}$ som vi är intresserade av att skatta.

För att lösa denna uppgift har vi ett stickprov av $X$ bestående av $n$ oberoende stokastiska variabler $x_{1}, x_{2}, \ldots, x_{n}$ med samma fördelning som $X$ (de behöver egentligen inte ha samma fördelning, men borde alla bero på samma parameter $\theta$ ). Detta stickprov har ett utfall av formen $x_{1}, x_{2}, \ldots, x_{n}$, dvs. $n$ reella värden. Givet dessa stickprov har vi en funktion $g\left(x_{1}, x_{2}, \ldots, x_{n}\right)$ så att

$$
\theta_{\mathrm{obs}}^{\star}=g\left(x_{1}, x_{2}, \ldots, x_{n}\right),
$$

är en skattning av parametern $\theta$. Detta värde kallas en punktskattning av $\theta$. Om vi istället tillämpar $g$ på de stokastiska variablerna $X_{1}, X_{2}, \ldots, X_{n}$ får vi

$$
\theta^{\star}=g\left(X_{1}, X_{2}, \ldots, X_{n}\right),
$$

vilket är en stickprovsvariabel som motsvarar punktskattningen $\theta_{\text {obs. }}^{\star}$. (Ibland skrivs detta lite slarvigt som $\theta^{\star}=\theta^{\star}\left(X_{1}, X_{2}, \ldots, X_{n}\right)$, och $\theta_{\text {obs }}^{\star}=\theta^{\star}\left(x_{1}, x_{2}, \ldots, x_{n}\right)$, dvs. funktionen $g$ ersätts av "funktionen" $\theta^{\star}$.) Funktionen $g$ är alltså ett "recept" på en skattning av parametern $\theta$ givet vissa värden. Om den tillämpas på stokastiska variabler får vi stickprovsvariabeln $\theta^{\star}$, en annan stokastisk variabel. Om den tillämpas på utfall får vi punktskattningen $\theta_{\text {obs }}^{\star}$.

Givet $\theta^{\star}$ kan vi nu undersöka dess täthetsfunktion (se nedan), dess egenskaper och beräkna dess väntevärde $E\left[\theta^{\star}\right]$, varians $\vee\left[\theta^{\star}\right]$ och så vidare. Detta ger oss då en uppfattning om hur själva skattningen $\theta_{\text {obs }}^{\star}$ skulle bete sig om vi repeterade försöket. Varje repetition skulle då ge en annan skattning och de skulle då vara fördelade enligt $\theta^{\star}$.

![](https://cdn.mathpix.com/cropped/2022_11_17_2aa4f50f6cb13f62d6d8g-08.jpg?height=597&width=1071&top_left_y=718&top_left_x=576)

Exempel 1. I opinionsundersökningen ovan hade vi att den sökta parametern $\theta$ $\operatorname{var} p$, och $X \sim \operatorname{Bin}(1000, p)$. Stickprovet hade storlek $n=1, d v s$. vi hade en variabel $X_{1}$ och beräknade stickprovsvariabeln $p^{\star}=X_{1} / 1000$, vilket gav utfallet $p_{\text {obs }}^{\star}=0.45$ eftersom $x_{1}=450$.

Alternativt skulle vi kunnat modellera problemet som $n=1000$ stycken bernoullifördelade stokastiska variabler $X_{1}, X_{2}, \ldots, X_{1000}$ med sannolikhet $p$ att ge ett (svar: ja) och sannolikhet $1-p$ att ge noll (svar: nej). Vi skulle då fått $p^{\star}=\sum_{i=1}^{n} X_{i} / 1000$, men svaret förblir detsamma som ovan.

Exempel 2. Låt $X$ vara antalet telefonsamtal till kundservice hos ett visst företag mellan kl. 13:00 och kl. 14:00. Antag att $X$ har fördelningen Po $(\mu)$. Under en vecka mäter vi antalet samtal 13:00-14:00 måndag-fredag, vilket ger vissa värden $x_{1}, x_{2}, x_{3}, x_{4}, x_{5}$. En vettig punktskattning kan vara medelvärdet $\mu_{\mathrm{obs}}^{\star}=\left(x_{1}+x_{2}+\right.$ $\left.x_{3}+x_{4}+x_{5}\right) / 5$

Stickprovet är då $X_{1}, X_{2}, X_{3}, X_{4}, X_{5}$ oberoende stokastiska variabler fördelade enligt Po $(\mu)$. Stickprovsvariabeln motsvarande skattningen är då $\mu^{\star}=\left(X_{1}+X_{2}+X_{3}+X_{4}+\right.$ $\left.X_{5}\right) / 5$

Exempel 3. Låt oss anta att vi gjort fyra mätningar $x_{1}, x_{2}, x_{3}, x_{4}$ av smältpunkten hos en viss legering. Eftersom det mätningarna är behäftade med ett visst fel så överensstämmer de inte helt. Vi kan då anta att mätningarna är utfall av oberoende likafördelade variabler $X_{1}, X_{2}, X_{3}, X_{4}$. Vi söker då parametrarna $\mu$ och $\sigma^{2}$ motsvarande väntevärdet och variansen för denna fördelning. Notera att vi kan anta att fördelningen har en viss form (t.ex. $N(\mu, \sigma)$ ) men detta är strikt sett inte nödvändigt (även om det kan komma visa sig vara användbart).

\section{Skattning av väntevärde och varians}

I det sista exemplet ovan noterade vi att det inte är nödvändigt att specificera en viss fördelning: den sökta parametern kan helt enkelt vara väntevärdet eller variansen hos en viss stokastisk variabel. I dessa fall kan vi definiera några standardskattningar. De kommer inte alltid att vara optimala (även om de ofta är det), men kan utgöra en användbar utgångspunkt för mer sofistikerade skattningar.

Till och börja med har vi det aritmetiska medelvärdet, som vi sett innan. Givet en samling utfall $x_{1}, x_{2}, \ldots, x_{n}$ har vi

$$
\mu_{\mathrm{obs}}^{\star}=\bar{x}=\frac{1}{n} \sum_{i=1}^{n} x_{i},
$$

vilket ses som ett utfall av stickprovsvariabeln

$$
\mu^{\star}=\bar{X}=\frac{1}{n} \sum_{i=1}^{n} x_{i},
$$

där vi betraktar stickprovet av oberoende likafördelade $X_{1}, X_{2}, \ldots, X_{n}$. Vi kommer se i nästa del att denna skattning har en rad trevliga egenskaper, oavsett vilken fördelning stickprovet härstammar från.

Den andra viktiga punktskattningen är stickprovsvariansen

$$
\left(\sigma^{2}\right)_{\mathrm{obs}}^{\star}=s^{2}=\frac{1}{n-1} \sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)^{2} .
$$

Notera att denna beror på det aritmetiska medelvärdet $\bar{x}$ eftersom väntevärdet måste skattas också. (Om väntevärdet redan är känt kan man använda en variant av stickprovsvariansen ovan, men detta fall är ganska sällsynt.) Den motsvarande stickprovsvariabeln är

$$
\left(\sigma^{2}\right)^{\star}=S^{2}=\frac{1}{n-1} \sum_{i=1}^{n}\left(X_{i}-\bar{X}\right)^{2} .
$$

Notera att vi ofta använder beteckningarna $s^{2}$ och $S^{2}$ istället för de klumpigare $\left(\sigma^{2}\right)_{\text {obs }}^{\star}$ och $\left(\sigma^{2}\right)^{\star}$.

\section{Egenskaper hos punktskattningar}

En viktig egenskap hos en punktskattning är att dess stickprovsvariabel har ett väntevärde som överensstämmer med den sanna parametern. Med andra ord, om vi repeterar skattningen ett stort antal gånger kommer medelvärdet att närma sig det korrekta värdet. Givet en punktskattning $\theta_{\text {obs }}^{\star}$ av en parameter $\theta$ : säger vi att den är väntevärdesriktig om

$$
\mathrm{E}\left[\theta^{\star}\right]=\theta
$$

där $\theta^{\star}$ är den motsvarande stickprovsvariabeln. (Vi kan också kräva att väntevärdet $\mathrm{E}\left[\theta^{\star}\right]$ närmar sig $\theta$ då antalet element i stickprovet går mot oändligheten, vilket betyder att skattningen är asymptotiskt väntevärdesriktig.) Skillnaden $\mathrm{E}\left[\theta^{\star}\right]-\theta$ kallas det systematiska felet hos skattningen.

![](https://cdn.mathpix.com/cropped/2022_11_17_2aa4f50f6cb13f62d6d8g-10.jpg?height=784&width=1065&top_left_y=638&top_left_x=560)

Det aritmetiska väntevärdet är väntevärdesriktigt eftersom

$$
\mathrm{E}\left[\mu^{\star}\right]=\mathrm{E}[\bar{X}]=\mathrm{E}\left[\frac{1}{n} \sum_{i=1}^{n} X_{i}\right]=\frac{1}{n} \sum_{i=1}^{n} \mathrm{E}\left[X_{i}\right]=\frac{1}{n} \times n \times \mathrm{E}[X]=\mathrm{E}[X]=\mu .
$$

Stickprovsvariansen likaså då

$$
\begin{aligned}
\sum_{i=1}^{n}\left(X_{i}-\bar{X}\right)^{2} &=\sum_{i=1}^{n}\left(\left(X_{i}-\mu\right)-(\bar{X}-\mu)\right)^{2} \\
&=\sum_{i=1}^{n}\left(X_{i}-\mu\right)^{2}-2(\bar{X}-\mu) \sum_{i=1}^{n}\left(X_{i}-\mu\right)+n(\bar{X}-\mu)^{2} \\
&=\sum_{i=1}^{n}\left(X_{i}-\mu\right)^{2}-2 n(\bar{X}-\mu)^{2}+n(\bar{X}-\mu)^{2} \\
&=\sum_{i=1}^{n}\left(X_{i}-\mu\right)^{2}-n(\bar{X}-\mu)^{2},
\end{aligned}
$$

vilket ger, eftersom $\mathrm{V}[\bar{X}]=\sigma^{2} / n$ som vi såg tidigare,

$$
\begin{aligned}
\mathrm{E}\left[\sum_{i=1}^{n}\left(X_{i}-\bar{X}\right)^{2}\right] &=\mathrm{E}\left[\sum_{i=1}^{n}\left(X_{i}-\mu\right)^{2}\right]-n \mathrm{E}\left[(\bar{X}-\mu)^{2}\right] \\
&=n \mathrm{E}\left[(X-\mu)^{2}\right]-n \mathrm{~V}[\bar{X}]=n \sigma^{2}-n \frac{\sigma^{2}}{n}=(n-1) \sigma^{2}
\end{aligned}
$$

så $\mathrm{E}\left[S^{2}\right]=\frac{1}{n-1}(n-1) \sigma^{2}=\sigma^{2}$. Detta förklarar varför vi behöver $n-1$ istället för $n$ i nämnaren: annars skulle skattningen inte vara väntevärdesriktig.

Notera att även om stickprovsvariansen $s^{2}$ är väntevärdesriktig så är detta inte fallet för stickprovsstandardavvikelsen $s$ eftersom vi inte kan "flytta in" kvadratroten innanför väntevärdet (dvs. $\mathrm{E}[S]=\mathrm{E}\left[\sqrt{S^{2}}\right] \neq \sqrt{\mathrm{E}\left[S^{2}\right]}=\sqrt{\sigma^{2}}=\sigma$ ). Ofta har vi däremot att det systematiska felet $E[S]-\sigma$ är så litet att det inte spelar så stor roll.

En annan viktig egenskap beskriver hur skattningen beter sig med avseende på stickprovsstorleken. Antag att vi har ett oändligt stort stickprov $X_{1}, x_{2}, \ldots$ samt en följd av punktskattningar $\theta_{1, \text { obs }}^{\star} \theta_{2, \text { obs' }}^{\star}$... där $\theta_{n, \text { obs }}^{\star}$ bara beror på de $n$ första värdena $x_{1}, x_{2}, \ldots, x_{n}$. Med andra ord har $\theta_{n, o b s}^{\star}$ stickprovsstorleken $n$. Låt $\theta_{n}^{\star}$ vara stickprovsvariabeln motsvarande $\theta_{n, o b s}^{\star}$. Om

$$
\lim _{n \rightarrow \infty} P\left(\left|\theta_{n}^{\star}-\theta\right|>\epsilon\right)=0,
$$

för varje $\epsilon>0$ sägs denna följd av punktskattningar vara konsistent.

![](https://cdn.mathpix.com/cropped/2022_11_17_2aa4f50f6cb13f62d6d8g-11.jpg?height=591&width=1049&top_left_y=1537&top_left_x=554)

Detta är en naturlig och användbar egenskap hos skattningar - när antalet datapunkter går mot oändligheten förväntar vi oss att skattningen blir mer och mer exakt. Vi ser att det aritmetiska medelvärdet $\bar{x}$ bildar en konsistent följd av punktskattningar på grund av stora talens lag. För att erhålla ett liknande resultat för stickprovsvariansen krävs att $\mathrm{V}\left[\left(X_{i}-\bar{X}\right)^{2}\right]$ är ändlig, dvs. att $E\left[|X|^{4}\right]$ är ändlig, vilket inte alltid är fallet för alla fördelningar. När detta gäller, som till exempel för normalfördelningen, är stickprovsvariansen en konsistent skattning. Att felet går till noll när $n$ går mot oändligheten är bra att veta, men vi är också intresserade av felet $\mathrm{i}$ skattningen $\theta_{\text {obs }}^{\star}$ av $\theta$. Detta definieras oftast som medelkvadratfelet (MSE från engelskans "mean square error")

$$
\mathrm{MSE}=\mathrm{E}\left[\left(\theta^{\star}-\theta\right)^{2}\right]
$$

där $\theta^{\star}$ är den motsvarande stickprovsvariabeln I regel vill vi ha ett lågt MSE, då detta betyder att den slumpmässiga inverkan på skattningen $\theta_{\text {obs }}^{\star}$ är liten. Notera att MSE beror på den sökta parameterns $\theta$ värde. I vissa tillämpningar är det relevant att ta maximum över möjliga $\theta$-värden och vi får då ett specifikt maxfel för en viss skattning. Alternativt kan vi ha en fördelning över troliga $\theta$-värden och beräkna väntevärdet av medelkvadratfelet med avseende på denna fördelning. Detta kallas punktskattningens Bayesrisk och kommer att introduceras senare i kursen.

Om vi utvecklar lite ser vi att medelkvadratfelet kan uttryckas som summan av två felkomponenter:

$$
\begin{aligned}
\mathrm{MSE} &=\mathrm{E}\left[\left(\theta^{\star}-\theta\right)^{2}\right] \\
&=\mathrm{E}\left[\left(\theta^{\star}-\mathrm{E}\left(\theta^{\star}\right)+\mathrm{E}\left[\theta^{\star}\right]-\theta\right)^{2}\right] \\
&=\mathrm{E}\left[\left(\theta^{\star}-\mathrm{E}\left[\theta^{\star}\right]\right)^{2}\right]+2 \mathrm{E}\left[\theta^{\star}-\mathrm{E}\left[\theta^{\star}\right]\right]\left(\mathrm{E}\left[\theta^{\star}\right]-\theta\right)+\left(\mathrm{E}\left[\theta^{\star}\right]-\theta\right)^{2} \\
&=\mathrm{E}\left[\left(\theta^{\star}-\mathrm{E}\left[\theta^{\star}\right]\right)^{2}\right]+0+\left(\mathrm{E}\left[\theta^{\star}\right]-\theta\right)^{2} \\
&=\mathrm{V}\left[\theta^{\star}\right]+\left(\mathrm{E}\left[\theta^{\star}\right]-\theta\right)^{2}
\end{aligned}
$$

Med andra ord så beror felet dels på skattningens varians $\mathrm{V}\left[\theta^{\star}\right]$ samt kvadraten av det systematiska felet $E\left[\theta^{\star}\right]-\theta$. Minimeringen av MSE sker då genom att minimera både variansen och det systematiska felet. Tyvärr är detta inte alltid möjligt, utan en mindre varians kan ge ett större systematiskt fel och vice versa. Den optimala avvägningen mellan systematiskt fel och varians beror ofta på tillämpningen. Man kan, till exempel, ofta tillåta ett litet systematiskt fel om variansen minskas.

Som vi sett ovan har vi dock ofta att det systematiska felet är noll, dvs. att skattningen är väntevärdesriktig. I så fall har vi att MSE $=\mathrm{V}\left[\theta^{*}\right]$. Om det systematiska felet är litet utan att vara noll kan det fortfarande vara bra att istället fokusera på variansen. Detta förenklar bland annat beräkningar och låter oss jämföra olika skattningar. Låt $\theta_{\text {obs }}^{\star}$ och $\hat{\theta}_{\text {obs }}$ vara två olika punktskattningar. Vi säger att $\theta_{\text {obs }}^{\star}$ är effektivare än $\hat{\theta}_{\text {obs }}$ om

$$
\mathrm{V}\left[\theta^{\star}\right] \leq \mathrm{V}[\hat{\theta}]
$$

för alla $\theta \in \Sigma_{\theta}$ samt att det finns ett $\theta_{0} \in \Sigma_{\theta}$ så att

$$
\mathrm{V}\left[\theta^{\star}\right]<\mathrm{V}[\hat{\theta}] \text {. }
$$

För vissa punktskattningar kan vi visa att de är effektivare än alla andra möjliga skattningar.