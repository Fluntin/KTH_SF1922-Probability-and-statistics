\title{
Föreläsning sju
}

\author{
Joakim Andén
}

18 november 2022

\section{Beroendemått}

Vi har tidigare sett att två stokastiska variabler $X$ och $Y$ kan vara oberoende av varandra, dvs. att $f_{X, Y}(x, y)=f_{X}(x) f_{Y}(y)$ i det kontinuerliga fallet. Men om variablerna inte är oberoende, kan vi kvantifiera graden av beroende? Inte bara det, men är beroendet "positivt", dvs. att större $X$ medför större $Y$, eller "negativt", dvs. att större $X$ medför mindre $Y$ ?

![](https://cdn.mathpix.com/cropped/2022_11_15_e8598ab2b415fb02099bg-01.jpg?height=425&width=412&top_left_y=1197&top_left_x=539)

Starkt beroende

(positive)

![](https://cdn.mathpix.com/cropped/2022_11_15_e8598ab2b415fb02099bg-01.jpg?height=360&width=377&top_left_y=1758&top_left_x=554)

![](https://cdn.mathpix.com/cropped/2022_11_15_e8598ab2b415fb02099bg-01.jpg?height=417&width=423&top_left_y=1198&top_left_x=1095)

Starke beroench

(negative)

![](https://cdn.mathpix.com/cropped/2022_11_15_e8598ab2b415fb02099bg-01.jpg?height=363&width=377&top_left_y=1759&top_left_x=1077)

Ett sätt att mäta beroendet hos $X$ och $Y$ är att betrakta produkten $\left(X-\mu_{X}\right)\left(Y-\mu_{Y}\right)$. Om produkten oftast tar positiva värden betyder det att när $X$ är stort (större än $\mu_{X}$ ) är $Y$ också stort (större än $\mu_{Y}$ ) och när $X$ är litet (mindre än $\mu_{X}$ ) är $Y$ också litet (mindre än $\mu_{Y}$ ). Med andra ord kan vi då säga att $X$ och $Y$ är starkt positivt beroende. Om istället produkten oftast tar negativa värden betyder det att $X$ är stort när $Y$ är litet och vice versa, dvs. att vi har ett starkt negativt beroende. Om produkten tar både positiva och negativa värden, dvs. dess fördelning är centrerad runt noll, så är $X$ och $Y$ svagt beroende.

Vi definierar därför kovariansen mellan $X$ och $Y$ som

$$
\mathrm{C}[X, Y]=\mathrm{E}\left[\left(X-\mu_{X}\right)\left(Y-\mu_{Y}\right)\right]
$$

Detta värde mäter alltså hur $X$ och $Y$ varierar tillsammans ("kovarierar"?). Notera att $\mathrm{C}[X, X]=\mathrm{V}[X]$

Som innan har vi en användbar identitet för att beräkna kovariansen

$$
\begin{aligned}
\mathrm{C}[X, Y] &=\mathrm{E}\left[\left(X-\mu_{X}\right)\left(Y-\mu_{Y}\right)\right]=\mathrm{E}\left[X Y-\mu_{X} Y-\mu_{Y} X+\mu_{X} \mu_{Y}\right] \\
&=\mathrm{E}[X Y]-\mu_{X} \mu_{Y}-\mu_{Y} \mu_{X}+\mu_{X} \mu_{Y}=\mathrm{E}[X Y]-\mu_{X} \mu_{Y} \\
&=\mathrm{E}[X Y]-\mathrm{E}[X] \mathrm{E}[Y] .
\end{aligned}
$$

Som konsekvens av detta ser vi att om $X$ och $Y$ är oberoende så har vi $E[X Y]=$ $\mathrm{E}[X] \mathrm{E}[Y]$, vilket då ger att $\mathrm{C}[X, Y]=0$.

Om vi delar med standardavvikelserna $D[X]$ och $D[Y]$ får vi korrelationskoefficienten

$$
\rho[X, Y]=\frac{\mathrm{C}[X, Y]}{\mathrm{D}[X] D[Y]} .
$$

Man kan visa (genom tillämpning av Cauchy-Schwarz olikhet) att $|C[X, Y]| \leq \mathrm{D}[X] \mathrm{D}[Y]$, vilket ger att $-1 \leq \rho[X, Y] \leq 1$. Om $\rho[X, Y]=1$ är variablerna maximalt positivt korrelerade medan om $\rho[X, Y]=-1$ är variablerna maximalt negativt korrelerade. Korrelationskoefficienten är ett sätt att beskriva beroendet mellan $X$ och $Y$ utan att ta hänsyn till skala. Om vi multiplicerar $X$ eller $Y$ med en konstant så multipliceras kovariansen $C[X, Y]$ med samma konstant - korrelationskoefficienten $\rho[X, Y]$ är däremot oförändrad. Man säger att korrelationskoefficienten är skalinvariant. Exempel 1. Antag att $X$ och $Y$ är diskreta stokastiska variabler så att sannolikhetsfunktionen har värdena

$$
\begin{array}{lll}
p_{X, Y}(0,0)=1 / 3 & p_{X, Y}(0,1)=1 / 6 & p_{X, Y}(0,2)=0 \\
p_{X, Y}(1,0)=0 & p_{X, Y}(1,1)=1 / 6 & p_{X, Y}(1,2)=1 / 3
\end{array}
$$

och som är noll för andra värden på $(x, y)$. Då kan vi beräkna marginalfördelningarnas sannolikhetsfunktioner

$$
p_{x}(x)= \begin{cases}1 / 2, & x=0 \\ 1 / 2, & x=1\end{cases}
$$

och

$$
p_{Y}(y)= \begin{cases}1 / 3, & y=0 \\ 1 / 3, & y=1 \\ 1 / 3, & y=2\end{cases}
$$

som allstå är likformiga. Om vi betingar med avseende på $X=0$ däremot får vi sannolikhetsfunktionen

$$
p_{Y \mid X=0}(y)= \begin{cases}2 / 3, & y=0, \\ 1 / 3, & y=1 \\ 0, & y=2\end{cases}
$$

vilket skiljer sig (markant) från marginalfördelningen pr(y). Alltså är $X$ och $Y$ inte oberoende (om så var fallet skulle marginalfördelningen och den betingade fördelningen sammanfalla).

Låt oss nu beräkna kovariansen. Först har vi väntevärdena

$$
\mathrm{E}[X]=0 \cdot p_{x}(0)+1 \cdot p_{x}(1)=0 \cdot \frac{1}{2}+1 \cdot \frac{1}{2}=\frac{1}{2}
$$

och

$$
E[Y]=0 \cdot p_{Y}(0)+1 \cdot p_{Y}(1)+2 \cdot p_{Y}(2)=0 \cdot \frac{1}{3}+1 \cdot \frac{1}{3}+2 \cdot \frac{1}{3}=1 \text {. }
$$

För att beräkna $\mathrm{E}[X Y]$ kan vi tänka på två sätt. Antingen tar vi varje värde på $(x, y)$, beräknar $x y p_{X, Y}(x, y)$ och summerar. Eller så identifierar vi de par $(x, y)$ som ger samma produkt xy, lägger ihop deras sannolikheter, och summerar. Paren $(0,0)$, $(0,1),(0,2)$ och $(1,0)$ ger produkten $0,(1,1)$ ger produkten 1 och $(1,2)$ ger produkten 2, därför får vi

$$
\mathrm{E}[X Y]=0 \cdot\left(\frac{1}{3}+\frac{1}{6}+0+0\right)+1 \cdot \frac{1}{6}+2 \cdot \frac{1}{3}=\frac{5}{6} .
$$

Vi har alltså

$$
\mathrm{C}[X, Y]=\frac{5}{6}-\frac{1}{2} \cdot 1=\frac{1}{3} .
$$

Vi kan också beräkna korrelationskoefficienten. Först har vi $\mathrm{V}[X]=1 / 4$ och $\mathrm{V}[Y]=$ 1 , vilket $\operatorname{ger} \mathrm{D}[X]=1 / 2$ och $\mathrm{D}[Y]=1$, så

$$
\rho[X, Y]=\frac{1 / 3}{1 / 2 \cdot 1}=\frac{2}{3} \text {. }
$$

Variablerna är alltså relativt starkt korrelerade.

Vi säger att $X$ och $Y$ är okorrelerade om $\rho[X, Y]=0$, dvs. om $C[X, Y]=0$. Ickekorrelation är en svagare egenskap är oberoende - två stokastiska variabler är okorrelerade om de är oberoende, men två okorrelerade variabler är inte nödvändigtvis oberoende.

Exempel 2. Låt $X$ och $Y$ vara oberoende tvåpunktsfördelade med sannolikhetsfunktioner

$$
p_{X}(x)=\left\{\begin{array}{ll}
1 / 2, & x=0,1 \\
0, & \text { annars },
\end{array} \text { och } p_{Y}(y)= \begin{cases}1 / 2, & y=-1,1 \\
0, & \text { annars }\end{cases}\right.
$$

Produkten $U=X Y$ har då sannolikhetsfunktionen

$$
p_{\cup}(u)= \begin{cases}1 / 4, & u=-1,1 \\ 1 / 2, & u=0 \\ 0, & \text { annars. }\end{cases}
$$

Vi har då att $\mathrm{E}[X]=1 / 2, \mathrm{E}[Y]=0$ och $\mathrm{E}[U]=0$ samt

$$
\mathrm{E}[U X]=\mathrm{E}\left[X^{2} Y\right]=\mathrm{E}\left[X^{2}\right] \mathrm{E}[Y]=\mathrm{E}\left[X^{2}\right] \cdot 0=0 \text {, }
$$

vilket ger $\mathrm{C}[U, X]=\mathrm{E}[U X]-\mathrm{E}[X] \mathrm{E}[U]=0-0=0$.

Men U och $X$ är inte oberoende. Vi har, till exempel

$$
P(U=1 \mid X=0)=P(X Y=1 \mid X=0)=0 \neq 1 / 4=P(U=1) .
$$

Med kovariansbegreppet i hand låt oss nu återkomma till variansen av $X+Y$. Vi kan skriva om denna som

$$
\begin{aligned}
\mathrm{V}[X+Y] &=\mathrm{E}\left[\left(X+Y-\left(\mu_{X}+\mu_{Y}\right)\right)^{2}\right] \\
&=\mathrm{E}\left[\left(\left(X-\mu_{X}\right)+\left(Y-\mu_{Y}\right)\right)^{2}\right] \\
&=\mathrm{E}\left[\left(X-\mu_{X}\right)^{2}+2\left(X-\mu_{X}\right)\left(Y-\mu_{Y}\right)+\left(Y-\mu_{Y}\right)^{2}\right] \\
&=\mathrm{E}\left[\left(X-\mu_{X}\right)^{2}\right]+2 \mathrm{E}\left[\left(X-\mu_{X}\right)\left(Y-\mu_{Y}\right)\right]+\mathrm{E}\left[\left(Y-\mu_{Y}\right)^{2}\right] \\
&=\mathrm{V}[X]+\mathrm{V}[Y]+2 \mathrm{C}[X, Y] .
\end{aligned}
$$

Kovariansen bestämmer alltså om summan av $X$ och $Y$ kommer att öka eller minska spridningen jämfört med den individuella spridningen hos $X$ och $Y$. Vårt exempel innan med $Y=-X$ ger då $C[X, Y]=C[X,-X]=-V[X]$, så med identiteten ovan får vi $\mathrm{V}[0]=\mathrm{V}[X-X]=\mathrm{V}[X]+\mathrm{V}[-X]+2 \mathrm{C}[X,-X]=2 \mathrm{~V}[X]-2 \mathrm{~V}[X]=0$

Vi kan nu generalisera ovanstående resultat till två identiteter gällande linjärkombinationer av $n$ stokastiska variabler $X_{1}, X_{2}, \ldots, X_{n}$. Först har vi

$$
\mathrm{E}\left[\sum_{i=1}^{n} a_{i} X_{i}+b\right]=\sum_{i=1}^{n} a_{i} \mathrm{E}\left[X_{i}\right]+b \text {, }
$$

dvs. väntevärdet av linjärkombinationen är linjärkombinationen av väntevärdena. För variansen har vi

$$
\mathrm{V}\left[\sum_{i=1}^{n} a_{i} X_{i}+b\right]=\sum_{i=1}^{n} a_{i}^{2} \mathrm{~V}\left[X_{i}\right]+2 \sum_{1 \leq j<k \leq n} a_{j} a_{k} \mathrm{C}\left[X_{j}, X_{k}\right]
$$

dvs. vi får summan av varianserna plus en korrektion som beror på de parvisa kovarianserna mellan termerna i summan. Notera att korrektionstermen försvinner när $X_{1}, X_{2}, \ldots, X_{n}$ är okorrelerade. För okorrelerade stokastiska variabler $X_{1}, X_{2}, \ldots, X_{n}$ har vi

$$
\mathrm{V}\left[\sum_{i=1}^{n} a_{i} X_{i}+b\right]=\sum_{i=1}^{n} a_{i}^{2} \mathrm{~V}\left[X_{i}\right]
$$

Som följd av detta har vi att om $X_{1}, X_{2}, \ldots, X_{n}$ har samma väntevärde $\mu$ (om de representerar repeterade mätningar av samma storhet, till exempel) får vi

$$
\mathrm{E}\left[\sum_{i=1}^{n} X_{i}\right]=n \mu .
$$

Vi ser därför att det aritmetiska medelvärdet $\bar{X}=\frac{1}{n} \sum_{i=1}^{n} X_{i}$ har väntevärde

$$
\mathrm{E}[\bar{X}]=\mu \text {. }
$$

Om $X_{1}, X_{2}, \ldots, X_{n}$ är okorrelerade och har samma varians $\sigma^{2}$ har vi varianserna

$$
\mathrm{V}\left[\sum_{i=1}^{n} X_{i}\right]=n \sigma^{2} \quad \text { och } \mathrm{V}[\bar{X}]=\frac{1}{n^{2}} \mathrm{~V}\left[\sum_{i=1}^{n} x_{i}\right]=\frac{\sigma^{2}}{n} \text {. }
$$

vilket ger standardavvikelser

$$
\mathrm{D}\left[\sum_{i=1}^{n} x_{i}\right]=\sigma \sqrt{n} \text { och } \mathrm{D}[\bar{X}]=\frac{\sigma}{\sqrt{n}} .
$$

Vi ser alltså att det aritmetiska medelvärdet $\bar{X}$ närmar sig väntevärdet $\mu$ när $n$ går mot oändligheten. Detta sker som $1 / \sqrt{n}$, vilket betyder att vi måste multiplicera antalet försök $n$ med fyra för att halvera standardavvikelsen. Senare i denna föreläsning kommer vi stärka detta resultat genom att visa hur denna konvergens sker med avseende på fördelningen hos $\bar{X}$.

Identitet ovan för variansen av summan av okorrelerade och likafördelade stokastiska variabler ger oss ett enklare sätt att härleda variansen hos en $\operatorname{Bin}(n, p)$-fördelad stokastisk variabel. Kom ihåg att denna kan skrivas som summan av $n$ oberoende $\operatorname{Ber}(p)$-fördelade stokastiska variabler. Eftersom dessa har väntevärde $p$ blir variansen $\sigma^{2}=(1-p)^{2} \cdot p+(0-p)^{2} \cdot(1-p)=p(1-p)$. Enligt formeln ovan måste då variansen för summan av dessa $n$ stokastiska variabler vara $n \sigma^{2}=n p(1-p)$, vilket stämmer med variansen för $\operatorname{Bin}(n, p)$ som vi beräknade innan.

\section{Betingade väntevärden}

Som vi diskuterade tidigare har betingade fördelningar i stort sett samma egenskaper som vanliga fördelningar. Bland annat kan vi definiera det betingade väntevärdet

$$
\begin{array}{ll}
\mathrm{E}[X \mid Y=y]=\sum_{x=0}^{+\infty} x p_{X \mid Y=y}(x) & \text { (diskret) } \\
\mathrm{E}[X \mid Y=y]=\int_{X=-\infty}^{+\infty} x f_{X \mid Y=y}(X) d x & \text { (kontinuerlig) }
\end{array}
$$

som också betecknas $\mu_{X \mid Y=y}$.

För varje värde $y \in \mathbb{R}$ har vi ett betingat väntevärde $\mathrm{E}[X \mid Y=y]$. Vi kan därför definiera funktionen $g(y)=\mathrm{E}[X \mid Y=y]$ och betrakta den stokastiska variabeln $Z=g(Y)$ vilken vi betecknar $\mathrm{E}[X \mid Y]$. Detta kan förstås som att vi tar väntevärdet av $X$ med avseende på allt som inte beror på $Y$ och låter $Y$ fortfarande variera slumpmässigt. Den enda variationen som är kvar är då variationen i $Y$. Som ett exempel, antag att $X$ är en bowlingbolls vikt och $Y$ är en bowlingbolls volym. Eftersom densiteten hos bowlingbollen inte kan vara vilket värde som helst har vi ett beroende mellan $X$ och $Y$. Vi kan betrakta väntevärdet $E[X]$ (medelvikten) och väntevärdet $E[Y]$ (medelvolymen). För en viss volym y kan vi också betrakta medelvikten $\mathrm{E}[X \mid Y=y]$ för bowlingbollarna med volymen $y$. Men vi kan också betrakta medelvikten som en stokastisk variabel $E[X \mid Y]$ om vi låter volymen $Y$ variera slumpmässigt enligt sin marginalfördelning. Detta betyder att om vi tar en godtycklig volym $Y$ på måfå så har vi också medelvikten $\mathrm{E}[X \mid Y]$ för den medelvolymen.

Med detta synsätt kan vi visa lagen om total förväntan:

$$
\mathrm{E}[X]=\mathrm{E}[\mathrm{E}[X \mid Y]],
$$

dvs. väntevärdet av $X$ kan beräknas genom att först beräkna det betingade väntevärdet av $X$ givet $Y$ och sedan det obetingade väntevärdet av denna - vi integrerar först bort variationen hos $X$ som inte beror på $Y$, sedan variationen som beror på $Y$. I det kontinuerliga fallet har vi

$$
\begin{aligned}
\mathrm{E}[\mathrm{E}[X \mid Y]] &=\int_{y=-\infty}^{+\infty} \mathrm{E}[X \mid Y=y] f_{Y}(y) d y \\
&=\int_{y=-\infty}^{+\infty} \int_{x=-\infty}^{+\infty} x f_{X \mid Y=y}(x) d x f_{Y}(y) d y \\
&=\int_{y=-\infty}^{+\infty} \int_{x=-\infty}^{+\infty} x f_{X \mid Y=y}(x) f_{Y}(y) d x d y \\
&=\int_{y=-\infty}^{+\infty} \int_{x=-\infty}^{+\infty} x f_{X, Y}(x, y) d x d y=\mathrm{E}[X]
\end{aligned}
$$

(Detta är egentligen en tillämpning av lagen om total sannolikhet.)

Givet att vi håller betingningen med avseende på $Y$ fixt har vi i övrigt samma egenskaper hos betingade väntevärden som för vanliga (obetingade) väntevärden. För kontinuerliga stokastiska variabler gäller till exempel att vi kan beräkna det betingade väntevärdet av en funktion $g(X)$ av $X$ :

$$
\mathrm{E}[g(X) \mid Y=y]=\int_{X=-\infty}^{+\infty} g(x) f_{X \mid Y=y}(x) d x .
$$

Vi har också samma linjäritetsrelationer:

$$
\mathrm{E}\left[a_{1} X_{1}+a_{2} X_{2}+b \mid Y=y\right]=a_{1} \mathrm{E}\left[X_{1} \mid Y=y\right]+a_{2} \mathrm{E}\left[X_{2} \mid Y=y\right]+b .
$$

På samma sätt som i det obetingade fallet kan vi definiera den betingade variansen

$$
\mathrm{V}[X \mid Y=y]=\mathrm{E}\left[\left(X-\mu_{X \mid Y=y}\right)^{2} \mid Y=y\right] .
$$

Precis som $E[X \mid Y]$ kan vi definiera den stokastiska variabeln $V[X \mid Y]$ dvs. variansen av $X$ givet $Y$ men där vi låter $Y$ fortfarande variera slumpmässigt. Vi har då en nära släkting till lagen om total förväntan, lagen om total varians:

$$
\mathrm{V}[X]=\mathrm{E}[\mathrm{V}[X \mid Y]]+\mathrm{V}[\mathrm{E}[X \mid Y]]
$$

Variansen för $X$ har alltså två komponenter: väntevärdet hos den betingade variansen $V[X \mid Y]$ (medelvariansen av $X$ givet $Y$ ) samt variansen hos det betingade väntevärdet $E[X \mid Y]$ (variansen av medelvärdet av $X$ givet $Y$ ). Detta kan visas genom att tillämpa lagen om total förväntan på $\mathrm{E}\left[X^{2}\right]$ och $\mathrm{E}[X]$, vilket ger

$$
\begin{aligned}
\mathrm{V}[X] &=\mathrm{E}\left[X^{2}\right]-\mathrm{E}[X]^{2}=\mathrm{E}\left[\mathrm{E}\left[X^{2} \mid Y\right]\right]-\mathrm{E}[\mathrm{E}[X \mid Y]]^{2} \\
&=\mathrm{E}\left[\mathrm{E}\left[X^{2} \mid Y\right]\right]-\mathrm{E}\left[\mathrm{E}[X \mid Y]^{2}\right]+\mathrm{E}\left[\mathrm{E}[X \mid Y]^{2}\right]-\mathrm{E}[\mathrm{E}[X \mid Y]]^{2} \\
&=\mathrm{E}\left[\mathrm{E}\left[X^{2} \mid Y-\mathrm{E}[X \mid Y]^{2}\right]+\mathrm{E}\left[\mathrm{E}[X \mid Y]^{2}\right]-\mathrm{E}[\mathrm{E}[X \mid Y]]^{2}\right.\\
&=\mathrm{E}[\mathrm{V}[X \mid Y]]+\mathrm{V}[\mathrm{E}[X \mid Y]] .
\end{aligned}
$$

Exempel 3. Betingade fördelningar är kraftfulla verktyg för att bygga avancerade stokastiska modeller. Låt till exempel antalet bilar $X$ som passerar en korsning under en timme vara Poissonfördelat med parameter $\mu=560, d v s . X \sim \operatorname{Po}(560)$. Korsningen är relativt olycksdrabbad, så risken att en bil hamnar i en singelolycka där är $p=0.01$. Vi är nu intresserade av $Y$, antalet olyckor i korsningen.

Ett sätt att bestämma fördelningen för $Y$ är att konstatera att om $x$ bilar passerar korsningen så är antalet olyckor fördelat enligt $\operatorname{Bin}(x, 0.01)$. Med andra ord har vi att den betingade fördelningen av $Y$ givet $X=x$ är $\operatorname{Bin}(x, 0.01)$. Vi kan då använda lagen om total sannolikhet $p_{Y}(y)=\sum_{x=0}^{+\infty} p_{Y \mid X=x}(y) p_{X}(x)$ där $p_{Y \mid X=x}(y)$ och $p_{X}(x)$ ges av sannolikhetsfunktionerna för binomialfördelningen respektive Poissonfördelningen. Om vi bara intresserar oss för väntevärdet och variansen kan vi använda identiteterna ovan (lagarna om total förväntan och varians). Den första ger

$$
\mathrm{E}[Y]=\mathrm{E}[\mathrm{E}[Y \mid X]]=\mathrm{E}[X \cdot 0.01]=0.01 \mathrm{E}[X]=0.01 \cdot 560=5.6 \text {, }
$$

där vi har använt formeln för väntevärdet av binomialfördelningen i första likheten och väntevärdet för Poissonfördelningen i sista likheten. På samma sätt har vi

$$
\begin{aligned}
\mathrm{V}[Y] &=\mathrm{E}[\mathrm{V}[Y \mid X]]+\mathrm{V}[\mathrm{E}[Y \mid X]]=\mathrm{E}[X \cdot 0.01 \cdot(1-0.01)]+\mathrm{V}[0.01 X] \\
&=0.0099 \cdot 560+0.0001 \cdot 560=0.01 \cdot 560=5.6
\end{aligned}
$$

vilket ger en standardavvikelse på $\mathrm{D}[Y]=\sqrt{V[Y]} \approx 2.37$.

Exempel 4. Låt $N$ vara en diskret stokastisk variabel med värden 0, 1, 2, . . och låt $x_{1}, x_{2}, \ldots$ vara en följd oberoende likafördelade stokastiska variabler med samma väntevärde $\mu$ och varians $\sigma^{2}$. Vi antar också att $N$ och $X_{1}, X_{2}, \ldots$ är oberoende och definierar

$$
S_{N}=\sum_{i=1}^{N} x_{i} .
$$

Notera att antalet termer i summan är slumpmässigt. Fördelningen för $S_{N}$ är komplicerad, men vi kan komma åt dess väntevärde och varians genom att betinga med avseende på $N$ och använda resultaten ovan. Mer konkret har vi det betingade väntevärdet

$$
\mathrm{E}\left[S_{N} \mid N=n\right]=\mathrm{E}\left[\sum_{i=1}^{N} X_{i} \mid N=n\right]=\mathrm{E}\left[\sum_{i=1}^{n} X_{i}\right]=n \mu
$$

dvs. $\mathrm{E}\left[S_{N} \mid N\right]=N \mu$. Lagen om total förväntan ger $d a ̊ \mathrm{E}\left[S_{N}\right]=\mathrm{E}\left[\mathrm{E}\left[S_{N} \mid N\right]\right]=\mathrm{E}[N \mu]=$ $\mathrm{E}[N] \mu$

För variansen har vi

$$
\mathrm{V}\left[S_{N} \mid N=n\right]=\mathrm{V}\left[\sum_{i=1}^{n} X_{i}\right]=n \sigma^{2}
$$

$d v s . \vee\left[S_{N} \mid N\right]=N \sigma^{2}$. Den totala variansen är alltså

$$
\begin{aligned}
\mathrm{V}\left[S_{N}\right] &=\mathrm{E}\left[\mathrm{V}\left[S_{N} \mid N\right]\right]+\mathrm{V}\left[\mathrm{E}\left[S_{N} \mid N\right]\right] \\
&=\mathrm{E}\left[N \sigma^{2}\right]+\mathrm{V}[N \mu]=\mathrm{E}[N] \sigma^{2}+\mathrm{V}[N] \mu^{2} .
\end{aligned}
$$

Det är alltså inte bara medelvariationen hos $X_{1}, X_{2}, \ldots$ (varav vi har i genomsnitt $\mathrm{E}[N]$ stycken termer) som ger variansen hos $S_{N}$. Vi har också variationen hos $N$, givet av V $[N]$, som ger en extra dos variation givet att $\mu^{2} \neq 0$.

\section{Standardiserade normalfördelningen}

Vi såg tidigare att en normalfördelad variabel $X \sim \mathrm{N}(\mu, \sigma)$ har täthetsfunktion

$$
f_{X}(x)=\frac{1}{\sqrt{2 \pi \sigma^{2}}} e^{-(x-\mu)^{2} / 2 \sigma^{2}}
$$

och fördelningsfunktion

$$
F_{X}(x)=\frac{1}{\sqrt{2 \pi \sigma^{2}}} \int_{u=-\infty}^{x} e^{-(u-\mu)^{2} / 2 \sigma^{2}} d u .
$$

Tyvärr finns det ingen sluten form på fördelningsfunktionen utan dess värden måste beräknas numeriskt. Som vi ser har normalfördelning två parametrar: $\mu$ och $\sigma$. Vi kommer se senare att $\mu=\mathrm{E}[X]$ och $\sigma=\mathrm{D}[X]$.

Ett speciellt parameterval är $\mu=0$ och $\sigma=1$. I detta fall har vi $Z \sim N(0,1)$ och betecknar täthetsfunktionen $\phi(z)=f_{z}(z)$ och fördelningsfunktionen $\Phi(z)=F_{z}(z)$. Vi har då

$$
\phi(z)=\frac{1}{\sqrt{2 \pi}} e^{-z^{2} / 2} \text { och } \Phi(z)=\frac{1}{\sqrt{2 \pi}} \int_{u=-\infty}^{z} e^{-u^{2} / 2} d u .
$$
![](https://cdn.mathpix.com/cropped/2022_11_15_e8598ab2b415fb02099bg-08.jpg?height=314&width=1290&top_left_y=2178&top_left_x=386)Denna fördelning har ett par mycket användbara egenskaper:

(i) Täthetsfunktionen $\phi(z)$ är symmetrisk: $\phi(-z)=\phi(z)$.

(ii) Eftersom $\phi(z)$ är symmetrisk har vi att $\Phi(-z)=1-\Phi(z)$ eftersom

$$
\Phi(-z)=\int_{u=-\infty}^{-z} \phi(u) d u=\int_{u=z}^{+\infty} \phi(-u) d u=\int_{u=z}^{+\infty} \phi(u) d u=1-\Phi(z) .
$$

(iii) Sannolikheten att $Z \in[a, b]$ ges av

$$
P(a<Z<b)=\Phi(b)-\Phi(a) .
$$

Notera att inklusion av ändpunkterna $a$ och $b$ inte har någon effekt eftersom $Z$ är en kontinuerlig stokastisk variabel.

(iv) $\alpha$-kvantilerna för $N(0,1)$ ges specialbeteckningen $\lambda_{\alpha}$. Vi har alltså

$$
\mathrm{P}\left(Z>\lambda_{\alpha}\right)=\alpha \Leftrightarrow \mathrm{P}\left(Z \leq \lambda_{\alpha}\right)=1-\alpha \Leftrightarrow \Phi\left(\lambda_{\alpha}\right)=1-\alpha \Leftrightarrow \lambda_{\alpha}=\Phi^{-1}(1-\alpha) .
$$

(v) Om vi tillämpar $\Phi(-z)=1-\Phi(z)$ på definitionen av $\lambda_{\alpha}$ har vi att $\lambda_{1-\alpha}=-\lambda_{\alpha}$ eftersom

$$
\Phi\left(\lambda_{\alpha}\right)=1-\alpha \Leftrightarrow \Phi\left(-\lambda_{\alpha}\right)=1-\Phi\left(\lambda_{\alpha}\right)=1-(1-\alpha) .
$$

(vi) Det symmetriska intervallet $\left[-\lambda_{\alpha / 2}, \lambda_{\alpha / 2}\right]$ innehåller $Z$ med sannolikheten $1-\alpha$ eftersom

$$
P\left(-\lambda_{\alpha / 2}<Z<\lambda_{\alpha / 2}\right)=\Phi\left(\lambda_{\alpha / 2}\right)-\Phi\left(-\lambda_{\alpha / 2}\right)=(1-\alpha / 2)-\alpha / 2=1-\alpha .
$$
![](https://cdn.mathpix.com/cropped/2022_11_15_e8598ab2b415fb02099bg-09.jpg?height=386&width=1308&top_left_y=1438&top_left_x=446)

(vii) Väntevärdet är $\mathrm{E}[Z]=0$ eftersom $\phi(z)$ är symmetrisk, vilket ger att $z \phi(z)$ är en ojämn funktion vars integral således är noll.

(viii) Standardavvikelsen är $D[Z]=1$, eftersom $E\left[Z^{2}\right]=1$, vilket fås genom partiell integration

$$
\begin{aligned}
\mathrm{E}\left[Z^{2}\right] &=\frac{1}{\sqrt{2 \pi}} \int_{z=-\infty}^{+\infty} z^{2} e^{-z^{2} / 2} d z=\frac{1}{\sqrt{2 \pi}} \int_{z=-\infty}^{+\infty} z \cdot z e^{-z^{2} / 2} d z \\
&=\frac{1}{\sqrt{2 \pi}}\left[z \cdot-e^{-z^{2} / 2}\right]_{z=-\infty}^{+\infty}-\frac{1}{\sqrt{2 \pi}} \int_{z=-\infty}^{+\infty}-e^{-z^{2} / 2} d z=0+1=1 .
\end{aligned}
$$

En stokastisk variabel sägs vara standardiserad om dess väntevärde är noll och dess varians ett. Därför kallas detta specialfall av normalfördelningen för den standardiserade normalfördelningen. 

\section{Allmänna normalfördelningen}

Vi ska nu se hur egenskaperna ovan kan överföras till den allmänna normalfördelningen $\mathrm{N}(\mu, \sigma)$. För detta krävs följande sats:

Sats 5. För $\mu \in \mathbb{R}, \sigma \in \mathbb{R}>0$ har $v i$

$$
X \sim N(\mu, \sigma) \Leftrightarrow Z=\frac{X-\mu}{\sigma} \sim N(0,1) .
$$

Bevis. Vi antar först att $X \sim \mathrm{N}(\mu, \sigma)$. Detta ger fördelningsfunktionen

$$
\begin{aligned}
F_{z}(z) &=\mathrm{P}(Z \leq z)=P\left(\frac{X-\mu}{\sigma} \leq z\right)=\mathrm{P}(X \leq \mu+\sigma z) \\
&=\frac{1}{\sqrt{2 \pi \sigma^{2}}} \int_{u=-\infty}^{\mu+\sigma z} e^{-(u-\mu)^{2} / 2 \sigma^{2}} d u
\end{aligned}
$$

Med variabelbytet $v=\frac{u-\mu}{\sigma}$ får vi

$$
\begin{aligned}
&\frac{1}{\sqrt{2 \pi \sigma^{2}}} \int_{u=-\infty}^{\mu+\sigma z} e^{-(u-\mu)^{2} / 2 \sigma^{2}} d u \\
&=\frac{1}{\sqrt{2 \pi \sigma^{2}}} \int_{v=-\infty}^{z} e^{-v^{2} / 2}|\sigma| d v \\
&=\frac{1}{\sqrt{2 \pi}} \int_{v=-\infty}^{z} e^{-v^{2} / 2} d v=\Phi(z) .
\end{aligned}
$$

Så $Z$ har fördelningsfunktion $\Phi(z)$ och måste då ha fördelningen $N(0,1)$.

Andra riktningen visas på samma sätt.

Som direkt konsekvens av denna ekvivalens har vi för $X \sim \mathrm{N}(\mu, \sigma)$ att

$$
f_{X}(x)=\frac{1}{\sigma} \phi\left(\frac{x-\mu}{\sigma}\right) \quad \text { och } \quad F_{X}(x)=\Phi\left(\frac{x-\mu}{\sigma}\right)
$$

samt att

$$
\mathrm{E}[X]=\mathrm{E}[\mu+\sigma Z]=\mu+\sigma \mathrm{E}[Z]=\mu+0=\mu
$$

och

$$
\mathrm{V}[X]=\mathrm{V}[\mu+\sigma Z]=\sigma^{2} \mathrm{~V}[Z]=\sigma^{2} \cdot 1=\sigma^{2} \Rightarrow \mathrm{D}[X]=\sigma,
$$

där $Z=(X-\mu) / \sigma \sim N(0,1)$. Parametrarna $\mu$ och $\sigma$ för normalfördelningen $\mathrm{N}(\mu, \sigma)$ svarar alltså mot fördelningens väntevärde och standardavvikelse. Vi kan också översätta sannolikhetsberäkningar rörande $N(\mu, \sigma)$ med beräkningar på $N(0,1)$, dvs. med avseende på $\Phi(z)$ :

$$
\mathrm{P}(a<X<b)=P\left(\frac{a-\mu}{\sigma}<\frac{X-\mu}{\sigma}<\frac{b-\mu}{\sigma}\right)=\Phi\left(\frac{b-\mu}{\sigma}\right)-\Phi\left(\frac{a-\mu}{\sigma}\right) .
$$

Eftersom normalfördelningens fördelningsfunktion inte går att skriva på sluten form används relationen ovan för att beräkna sannolikheter genom att slå upp sökta värden på $\Phi(z)$ i tabellverk.

Kvantilerna för $N(\mu, \sigma)$ kan också beräknas utifrån kvantilerna $\lambda_{\alpha}$ för $N(0,1)$. Med andra ord har vi, eftersom $\mathrm{P}\left(Z>\lambda_{\alpha}\right)=\alpha$ för $Z \sim N(0,1)$, att

$$
P\left(\frac{X-\mu}{\sigma}>\lambda_{\alpha}\right)=\alpha \Leftrightarrow P\left(X>\mu+\lambda_{\alpha} \sigma\right)=\alpha,
$$

dvs. $\alpha$-kvantilen för $\mathrm{N}(\mu, \sigma)$ ges av $\mu+\lambda_{\alpha} \sigma$. På samma sätt har vi det symmetriska intervallet $\left[\mu-\lambda_{\alpha / 2} \sigma, \mu+\lambda_{\alpha / 2} \sigma\right]$ runt $\mu$ som uppfyller

$$
\mathrm{P}\left(\mu-\lambda_{\alpha / 2} \sigma<X<\mu+\lambda_{\alpha / 2} \sigma\right)=1-\alpha .
$$

\section{Linjärtransformationer av normalfördelade variabler}

En viktig egenskap hos normalfördelningen är att vi kan applicera godtyckliga linjärtransformationer på normalfördelade stokastiska variabler och återfå en normalfördelad stokastisk variabel. Vi betraktat först transformationen $X \mapsto a X+b$.

Sats 6. Låt $X \sim N(\mu, \sigma)$ och $b \in \mathbb{R}, a \in \mathbb{R}_{>0}$. Då har vi $Y=a X+b \sim N(a \mu+b,|a| \sigma)$.

Bevis. Enligt Sats 5 har vi

$$
Z=\frac{X-\mu}{\sigma} \sim N(0,1) \text {. }
$$

Om $Y=a X+b$ måste $X=(Y-b) / a$, vilket ger

$$
Z=\frac{(Y-b) / a-\mu}{\sigma}=\frac{Y-(b+a \mu)}{a \sigma} \sim N(0,1) .
$$

Antag nu att $a>0$, vi har då $\mu^{\prime}=b+a \mu$ och $\sigma^{\prime}=a \sigma>0$ så att

$$
\frac{Y-\mu^{\prime}}{\sigma^{\prime}} \sim N(0,1),
$$

och enligt Sats 5 ger detta att $Y \sim \mathrm{N}\left(\mu^{\prime}, \sigma^{\prime}\right)=\mathrm{N}(a \mu+b, a \sigma)=\mathrm{N}(a \mu+b,|a| \sigma)$ (eftersom $a>0$ så $a=|a|)$.

Om $a<0$ så kan vi inte definiera standardavvikelsen som $a \sigma$ eftersom denna är negativ. Istället noterar vi att om $Z \sim N(0,1)$ så är $-Z \sim N(0,1)$ eftersom fördelningen är symmetrisk. Detta ger då

$$
-Z=\frac{Y-(a \mu+b)}{-a \sigma} \sim N(0,1),
$$

så med $\mu^{\prime}=a \mu+b$ och $\sigma^{\prime}=-a \sigma>0$ har vi att

$$
\frac{Y-\mu^{\prime}}{\sigma^{\prime}} \sim \mathrm{N}(0,1) \text {, }
$$

vilket återigen ger att $Y \sim \mathrm{N}\left(\mu^{\prime}, \sigma^{\prime}\right)=\mathrm{N}(a \mu+b,-a \sigma)=\mathrm{N}(a \mu+b,|a| \sigma)$ (eftersom $a<0$ så $-a=|a|)$. Ett liknande förhållande gäller om vi adderar två normalfördelade stokastiska variabler.

Sats 7. $\operatorname{Om}_{1} \sim \mathrm{N}\left(\mu_{1}, \sigma_{1}\right)$ och $X_{2} \sim \mathrm{N}\left(\mu_{2}, \sigma_{2}\right)$ är oberoende har vi att

$$
X_{1}+X_{2} \sim \mathrm{N}\left(\mu_{1}+\mu_{2}, \sqrt{\sigma_{1}^{2}+\sigma_{2}^{2}}\right) .
$$

Med andra ord är summan av två normalfördelade variabler också normalfördelad.

Bevis. Enligt Sats 5 finns oberoende $Z_{1} \sim N(0,1)$ och $Z_{2} \sim N(0,1)$ så att

$$
X_{1}=\mu_{1}+\sigma_{1} Z_{1} \text { och } X_{2}=\mu_{2}+\sigma_{2} Z_{2},
$$

vilket ger

$$
X_{1}+X_{2}=\mu_{1}+\mu_{2}+\sigma_{1} Z_{1}+\sigma_{2} Z_{2}=\left(\mu_{1}+\mu_{2}\right)+\sigma_{1}\left(Z_{1}+\sigma_{1}^{-1} \sigma_{2} Z_{2}\right) .
$$

Det räcker alltså att visa att $Z_{1}+\alpha Z_{2} \sim N\left(0, \sqrt{1+\alpha^{2}}\right)$ för $\alpha>0$ och sedan tillämpa Sats 6.

Om $Y=Z_{1}+\alpha Z_{2}$ använder vi den kontinuerliga faltningsformeln och får

$$
\begin{aligned}
f_{Y}(y) &=\int_{z=-\infty}^{+\infty} f_{Z_{1}}(y-z) f_{\alpha z_{2}}(z) d z \\
&=\int_{z=-\infty}^{+\infty} \frac{1}{\sqrt{2 \pi}} e^{-(y-z)^{2} / 2} \cdot \frac{1}{\sqrt{2 \pi \alpha^{2}}} e^{-z^{2} / 2 \alpha^{2}} d z \\
&=\frac{1}{2 \pi \alpha} \int_{z=-\infty}^{+\infty} e^{-\frac{(y-z)^{2}}{2}-\frac{z^{2}}{2 \alpha^{2}}} d z \\
&=\frac{1}{2 \pi \alpha} \int_{z=-\infty}^{+\infty} e^{-\frac{\alpha^{2}(y-z)^{2}+z^{2}}{2 \alpha^{2}}} d z .
\end{aligned}
$$

Kvoten i exponenten kan skrivas om med hjälp av kvadratkomplettering till

$$
\begin{aligned}
\frac{\alpha^{2}(y-z)^{2}+z^{2}}{2 \alpha^{2}} &=\frac{\alpha^{2} y^{2}-2 \alpha^{2} y z+\alpha^{2} z^{2}+z^{2}}{2 \alpha^{2}} \\
&=\frac{\alpha^{2} y^{2}+\left(1+\alpha^{2}\right) z^{2}-2 \alpha^{2} y z+\alpha^{4}\left(1+\alpha^{2}\right)^{-1} y^{2}-\alpha^{4}\left(1+\alpha^{2}\right)^{-1} y^{2}}{2 \alpha^{2}} \\
&=\frac{\alpha^{2} y^{2}+\left(\left(1+\alpha^{2}\right)^{1 / 2} z-\alpha^{2}\left(1+\alpha^{2}\right)^{-1 / 2} y\right)^{2}-\alpha^{4}\left(1+\alpha^{2}\right)^{-1} y^{2}}{2 \alpha^{2}} \\
&=\frac{\alpha^{2}\left(1+\alpha^{2}\right)^{-1} y^{2}+\left(\left(1+\alpha^{2}\right)^{1 / 2} z-\alpha^{2}\left(1+\alpha^{2}\right)^{-1 / 2} y\right)^{2}}{2 \alpha^{2}} \\
&=\frac{y^{2}}{2\left(1+\alpha^{2}\right)}+\frac{\left(z-\alpha^{2}\left(1+\alpha^{2}\right)^{-1} y\right)^{2}}{2 \alpha^{2}\left(1+\alpha^{2}\right)^{-1}}
\end{aligned}
$$

Stoppar vi denna tillbaka in i exponenten får vi

$$
\begin{aligned}
f_{Y}(Y) &=\frac{1}{2 \pi \alpha} \int_{z=-\infty}^{+\infty} e^{-\frac{\alpha^{2}(y-z)^{2}+z^{2}}{2 \alpha^{2}}} d z=\frac{1}{2 \pi \alpha} e^{-\frac{y^{2}}{2\left(1+\alpha^{2}\right)}} \int_{z=-\infty}^{+\infty} e^{-\frac{\left(z-\alpha^{2}\left(1+\alpha^{2}\right)^{-1} y\right)^{2}}{2 \alpha^{2}\left(1+\alpha^{2}\right)^{-1}}} d z \\
&=\frac{1}{2 \pi \alpha} e^{-\frac{y^{2}}{2\left(1+\alpha^{2}\right)}} \sqrt{2 \pi \alpha^{2}\left(1+\alpha^{2}\right)^{-1}} \int_{z=-\infty}^{+\infty} \frac{1}{\sqrt{2 \pi \alpha^{2}\left(1+\alpha^{2}\right)^{-1}}} e^{-\frac{\left(z-\alpha^{2}\left(1+\alpha^{2}\right)^{-1} y\right)^{2}}{2 \alpha^{2}\left(1+\alpha^{2}\right)^{-1}}} d z \\
&=\frac{1}{\sqrt{2 \pi\left(1+\alpha^{2}\right)}} e^{-\frac{y^{2}}{2\left(1+\alpha^{2}\right)}} \int_{z=-\infty}^{+\infty} \frac{1}{\sqrt{2 \pi \alpha^{2}\left(1+\alpha^{2}\right)^{-1}}} e^{-\frac{\left(z-\alpha^{2}\left(1+\alpha^{2}\right)^{-1} y\right)^{2}}{2 \alpha^{2}\left(1+\alpha^{2}\right)^{-1}}} d z
\end{aligned}
$$

Integralen är lika med integralen av täthetsfunktionen för $N\left(\alpha^{2}\left(1+\alpha^{2}\right)^{-1} y, \alpha(1+\right.$ $\left.\alpha^{2}\right)^{-1 / 2}$ ) över $\mathbb{R}$ och är således ett, vilket ger

$$
f_{Y}(y)=\frac{1}{\sqrt{2 \pi\left(1+\alpha^{2}\right)}} e^{-\frac{y^{2}}{2\left(1+\alpha^{2}\right)}},
$$

dvs. $Y \sim N\left(0, \sqrt{1+\alpha^{2}}\right)$, vilket skulle visas.

Satsen ovan kan generaliseras till fler stokastiska variabler. Om vi har oberoende stokastiska variabler $X_{1} \sim \mathrm{N}\left(\mu_{1}, \sigma_{1}\right), X_{2} \sim \mathrm{N}\left(\mu_{2}, \sigma_{2}\right), \ldots, X_{n} \sim \mathrm{N}\left(\mu_{n}, \sigma_{n}\right)$ får vi

$$
\sum_{i=1}^{n} a_{i} X_{i}+b \sim \mathrm{N}\left(\sum_{i=1}^{n} a_{i} \mu_{i}+b, \sqrt{\sum_{i=1}^{n} a_{i}^{2} \sigma_{i}^{2}}\right) .
$$

Ett intressant specialfall inträffar då alla $X_{1}, X_{2}, \ldots, X_{n}$ är oberoende och likafördelade, (samma $\mu$ och $\sigma$ ) och vi beräknar det aritmetiska medelvärdet $\bar{X}$. Då har vi

$$
\bar{x}=\frac{1}{n} \sum_{i=1}^{n} x_{i} \sim \mathrm{N}\left(\mu, \frac{\sigma}{\sqrt{n}}\right) .
$$

Med andra ord så "krymper" normalfördelningen när vi tar medelvärdet $\bar{x}$ av flera normalfördelade stokastiska variabler med samma väntevärde och varians.

\section{Stora talens lag}

Resultatet ovan gällande $\bar{X}$ för normalfördelade stokastiska variabler stämmer väl med resultatet tidigare i föreläsningen angående standardavvikelsen hos $\bar{X}$ för likafördelade oberoende stokastiska variabler med samma väntevärde $\mu$ och standardavvikelse $\sigma$ (men med godtycklig fördelning annars). Vi såg då att $D[\bar{X}]=\frac{\sigma}{\sqrt{n}}$.

Vi kan visa några starkare resultat för detta konvergensbeteende. Det första kallas stora talens lag och ligger till grund för mycket av den empiriska vetenskapen. Den säger att det inte bara är standardavvikelsen som går mot noll, men hela sannolikhetsmåttet koncentrerar sig runt väntevärdet $\mu$ då $n \rightarrow \infty$. Sats 8. (Stora talens lag) Låt $X_{1}, X_{2}, \ldots$ vara oberoende likafördelade stokastiska variabler med samma väntevärde $\mu$ och standardavvikelse $\sigma$. Sätt

$$
\bar{x}_{n}=\frac{1}{n} \sum_{i=1}^{n} x_{i} .
$$

Då har vi för varje $\epsilon>0$ att

$$
P\left(\mu-\epsilon<\bar{X}_{n}<\mu+\epsilon\right) \rightarrow 1 \text { då } n \rightarrow+\infty .
$$

För att bevisa satsen behöver vi ett par enklare resultat.

Sats 9. (Markovs olikhet) Låt $Y$ vara en icke-negativ stokastisk variabel (dvs. $Y$ tar endast värden större än eller lika med noll) och $a>0$. Då har vi

$$
P(Y \geq a) \leq \frac{\mathrm{E}[Y]}{a} .
$$

Bevis. Enligt definitionen av $\mathrm{E}[Y]$ har vi i det kontinuerliga fallet

$$
\begin{aligned}
\mathrm{E}[Y] &=\int_{y=0}^{+\infty} y f_{Y}(y) d y=\int_{y=0}^{a} y f_{Y}(y) d y+\int_{y=a}^{+\infty} y f_{Y}(y) d y \\
& \geq \int_{y=a}^{+\infty} y f_{Y}(y) d y \geq a \int_{y=a}^{+\infty} f_{Y}(y) d y=a \mathrm{P}(Y \geq y) .
\end{aligned}
$$

Om vi stuvar om olikheten får vi $\mathrm{P}(Y \geq a) \leq \mathrm{E}[Y] / a$. Det diskreta fallet visas på samma sätt men integralerna ersätts med summor.

Sats 10. (Tjebysjovs olikhet) Låt $X$ vara en stokastisk variabel med väntevärde $\mu$ och standardavvikelse $\sigma>0$. För varje $k>0$ har vi då

$$
P(|X-\mu| \geq k \sigma) \leq \frac{1}{k^{2}} .
$$

Bevis. Vi har alltså

$$
\mathrm{P}(|X-\mu| \geq k \sigma)=P\left(\frac{|X-\mu|^{2}}{\sigma^{2}} \geq k^{2}\right) .
$$

Om vi sätter $Y=|X-\mu|^{2} / \sigma^{2}$ och tillämpar Markovs olikhet får vi

$$
\mathrm{P}(|X-\mu| \geq k \sigma)=P\left(\frac{|X-\mu|^{2}}{\sigma^{2}} \geq k^{2}\right)=\mathrm{P}\left(Y \geq k^{2}\right) \leq \frac{\mathrm{E}[Y]}{k^{2}}=\frac{1}{k^{2}}
$$

vilket visar den sökta olikheten.

Vi återgår nu till beviset för stora talens lag. Bevis. (Bevis för Sats 8) Vi vet att

$$
\mathrm{P}\left(\mu-\epsilon<\bar{X}_{n}<\mu+\epsilon\right)=\mathrm{P}\left(\left|\bar{X}_{n}-\mu\right|<\epsilon\right)=1-\mathrm{P}\left(\left|\bar{X}_{n}-\mu\right| \geq \epsilon\right) .
$$

Om vi sätter $k=\epsilon \sqrt{n} / \sigma$ ger Tjebysjovs olikhet att

$$
\mathrm{P}\left(\left|\bar{X}_{n}-\mu\right| \geq \epsilon\right)=\mathrm{P}\left(\left|\bar{X}_{n}-\mu\right| \geq k \sigma / \sqrt{n}\right) \leq \frac{1}{k^{2}}=\frac{\sigma^{2}}{\epsilon^{2} n} .
$$

Eftersom $n \rightarrow+\infty$ går högerledet mot noll, vilket i sin tur ger att

$$
\mathrm{P}\left(\mu-\epsilon<\bar{X}_{n}<\mu+\epsilon\right) \rightarrow 1 \text { då } n \rightarrow+\infty \text {. }
$$

\section{Centrala gränsvärdessatsen}

Stora talens lag visar att sannolikhetsfördelningen för $\bar{X}$ koncentreras runt $\mu$ när $n \rightarrow$ $+\infty$, men i övrigt vet vi inte riktigt hur den fördelningen ser ut. Sådan information kan vara viktig för att bestämma sannolikheten att $\bar{X}$ ligger tillräckligt nära $\mu$ eller för att utesluta ett alltför stort fel.

Det visar sig att vi kan beskriva denna fördelning approximativt om $n$ är tillräckligt stort. Mer konkret så konvergerar fördelningsfunktionen för summan av oberoende stokastiska variabler till fördelningsfunktionen för en normalfördelning. Detta resultat kallas centrala gränsvärdessatsen och spelar en nyckelroll inom statistiken.

Sats 11. (Centrala gränsvärdessatsen) Låt $X_{1}, X_{2}, \ldots$ vara oberoende likafördelade stokastiska variabler med väntevärde $\mu$ och standardavvikelse $\sigma$. Om vi definierar

$$
Z_{n}=\frac{\bar{X}_{n}-\mu}{\sigma / \sqrt{n}}=\frac{\sum_{i=1}^{n} X_{i}-n \mu}{\sigma \sqrt{n}}
$$

har vi att

$$
\lim _{n \rightarrow+\infty} F_{Z_{n}}(z)=\Phi(z) .
$$

(Detta kallas att $Z_{n}$ konvergerar till $\mathrm{N}(0,1)$ i distribution.) Med andra ord har vi

$$
P\left(a \leq Z_{n} \leq b\right)=P\left(a \leq \frac{\bar{X}_{n}-\mu}{\sigma / \sqrt{n}} \leq b\right)=P\left(a \leq \frac{\sum_{i=1}^{n} X_{i}-n \mu}{\sigma \sqrt{n}} \leq b\right) \rightarrow \Phi(b)-\Phi(a)
$$

då $n \rightarrow+\infty$.

Det viktiga att notera här är att $x_{1}, x_{2}, \ldots$ kan ha vilken fördelning som helst (diskret eller kontinuerlig) - deras summa konvergerar oavsett till en normalfördelad stokastisk variabel. Detta motiverar normalfördelningens centrala roll inom statistiken: den uppstår varje gång vi summerar ett stort antal slumpmässiga värden.

Intuitivt bygger beviset på upprepad tillämpning av faltningsformeln. Varje faltning innebär en viss utjämning eller utslätning av tätheten. Resultatet av denna utslätning är då normalfördelningen - denna motsvarar på något sätt "den slätaste" fördelningen med avseende på faltningsoperationen. Ett sätt att tolka central gränsvärdessatsen är att för ett tillräckligt stort $n$ så har vi att $Z_{n}$ har approximativt fördelningen $N(0,1)$. Eftersom $Z_{n}=\left(\bar{X}_{n}-\mu\right) /(\sigma / \sqrt{n})=$ $\left(\sum_{i=1}^{n} X_{i}-n \mu\right) /(\sigma \sqrt{n})$ ger detta att $\bar{X}_{n}$ approximativt har fördelningen $N(\mu, \sigma / \sqrt{n})$ medan $\sum_{i=1}^{n} X_{i}$ approximativt har fördelningen $\mathrm{N}(n \mu, \sigma \sqrt{n})$.

Ett problem med den centrala gränsvärdessatsen är att den inte säger hur stort $n$ måste vara för att få en bra approximation. Ofta är det svårt att säga hur nära vi kommer för ett givet $n$ utan att veta mer om fördelningen för $x_{1}, x_{2}, \ldots$ l de problem vi studerar i kursen kommer det framgå när satsen kan tillämpas.

Vi kan illustrera satsen genom att ta $X_{1}, X_{2}, \ldots$ med likformig fördelning över $[-1,1]$. I detta fall har vi $\mu=0$ och $\sigma=1 / \sqrt{3}$. Enligt centrala gränsvärdessatsen kommer då

$$
\frac{\sqrt{3}}{\sqrt{n}} \sum_{i=1}^{n} x_{n}
$$

att vara approximativt $N(0,1)$-fördelad när $n \rightarrow \infty$.
![](https://cdn.mathpix.com/cropped/2022_11_15_e8598ab2b415fb02099bg-16.jpg?height=782&width=1136&top_left_y=1138&top_left_x=493)

Notera att även om den likformiga fördelningen är långt ifrån normalfördelningen så krävs det inte många termer förrän vi börjar närma oss normalfördelningen.