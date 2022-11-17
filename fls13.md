\title{
Föreläsning tretton
}

\author{
Joakim Andén
}

7 december 2022

\section{Apriorifördelning}

Hittills har vi antagit att den sökta parametern har ett fixt värde och försöker skatta denna (eller dessa) utifrån ett slumpmässigt stickprov. Detta kan till exempel göras med en ML- eller MK-skattning. Tanken är att om vi repeterar denna skattning på olika stickprov så får vi en viss fördelning på skattningens stickprovsvariabel. Utifrån denna kan vi sedan beräkna väntevärde, standardavvikelse, konfidensintervall, testa hypoteser, och så vidare.

Alla dessa förfaranden utgår ifrån en (åtminstone teoretisk) repetition av experimentet, men en sådan är inte alltid möjlig. Till exempel kan vi vilja prata om sannolikheten att det regnar imorgon givet dagens väderförhållanden. Vi kan inte repetera detta experiment utan har bara ett stickprov. Grundproblemet är frekvenstolkningen av sannolikhetsbegreppet. Om vi istället tolkar sannolikheter subjektivt, dvs. som ett mått på hur mycket vi tror på ett visst påstående (som att det regnar imorgon), öppnas möjligheter att modellera andra fenomen.

En naturlig konsekvens av en subjektiv sannolikhetstolkning är att vi inte längre behöver betrakta parametern som ett fixt värde. I stället kan vi betrakta den som en stokastisk variabel med en viss fördelning. Denna fördelning motsvarar då vad för värden som vi tror att parametern antar. Med andra ord kvantifierar parameterns fördelning vår osäkerhet gällande dess värde.

Vi återgår nu till huvudproblemet inom statistisk inferens: skattning av parametrar från data. Med perspektivet ovan blir då uppgiften att bestämma parameterns fördelning utifrån mätdata. Detta görs enklast genom att betrakta mätdatan som utfall av en betingad fördelning där betingningen sker med avseende på den sökta parametern. Målet är sedan att vända på betingningen, dvs. att bestämma den betingade fördelningen av parametern med avseende på mätdatan. För att åstadkomma detta använder vi Bayes sats.

Låt oss anta att vår sökta parameter är ett utfall $\theta$ av den stokastiska variabeln $\Theta$. Innan vi kan tillämpa Bayes sats behöver vi veta fördelningen på $\Theta$ innan vi ser datan. Detta kallas parameterns apriorifördelning (a priori betyder på förhand på latin) och betecknas med $f_{\Theta}(\theta)$ (detta är alltså täthetsfunktionen för $\Theta$ om det är en kontinuerlig stokastisk variabel och en sannolikhetsfunktion om den är diskret). Apriorifördelningen $f_{\Theta}(\theta)$ motsvarar våra antaganden om $\Theta$ : utan att vi har sett några data, vilka värden tror vi att $\Theta$ antar? Vi kan på detta sätt baka in olika antaganden (hur stor eller liten borde parametern vara) eller information från tidigare experiment (vår modell kanske baseras på en annan modell där vi vet vad för värde $\Theta$ antar). Notera att detta inte är möjligt inom den klassiska inferensteorin: i till exempel ML-skattning så kan parametern $\theta$ anta vilket värde som helst (eller eventuellt begränsas till en delmängd, men inte mer än så).

Den andra ingrediensen beskriver hur parametern $\Theta$ påverkar fördelningen av våra mätdata. Detta är den betingade fördelningen av mätdata $X$ givet $\Theta=\theta$ och skrivs $f_{X \mid \theta}(x \mid \theta)$. Vi kallar detta för datafördelningen eller samplingfördelningen. (Ȧterigen använder vi samma beteckning för täthetsfunktion - om $X$ är kontinuerlig - och sannolikhetsfunktion - om $X$ är diskret.) Datafördelningen är redan bekant från tidigare föreläsningar, då kallade vi den för likelihoodfunktionen. Som vi kommer att se så skiljer de sig emellertid åt i hur de tillämpas och hur de tolkas.

Om vi multiplicerar datafördelningen med apriorifördelningen och integrerar över $\theta$ får vi marginalfördelningen

$$
f_{X}(x)=\int_{\Sigma_{\theta}} f_{X \mid \Theta}(x \mid \theta) f_{\Theta}(\theta) d \theta
$$

enligt lagen om total sannolikhet där $\Sigma_{\theta}$ är mängden av möjliga parametrar. (Om $\Theta$ är diskret ersätter vi integralen med en summa $\sum_{\theta \in \Sigma_{\theta}} f_{X \mid \Theta}(\chi \mid \theta) f_{\Theta}(\theta)$.) Detta är alltså den obetingade fördelningen för mätdatan: fördelningen för $X$ som vi förväntar oss om parametern $\Theta$ tillåts variera enligt apriorifördelningen $f_{\Theta}(\theta)$.

Ett sätt att förstå apriorifördelningar, datafördelningar och marginalfördelningar är att se det slumpmässiga försöket som en tvåstegsprocess: först dras en parameter $\theta_{1}$ enligt $f_{\Theta}(\theta)$ och sedan dras $\chi_{1}$ enligt $f_{X \mid \Theta}\left(x \mid \theta_{1}\right)$ - denna fördelning är alltså betingad med avseende på händelsen $\Theta=\theta_{1}$. Om detta försök repeteras (och vi får alltså en ny parameter $\theta_{1}$ och datapunkt $x_{1}$ varje gång) så kommer de dragna värdena $x_{1}$ att följa fördelningen marginalfördelningen $f_{X}(x)$. Vi illustrerar detta med ett konkret exempel.

Exempel 1. Anta att vi har en påse med tre stycken kronor. En har sannolikheten $0.2$ att hamna på klave när vi singlar, två har sannolikheten $0.5$ att hamna på klave och en har sannolikheten $0.8$ att hamna på klave. Om vi låter $\theta$ beteckna sannolikheten att det dragna myntet hamnar på klave när vi singlar har denna sannolikhetsfunktionen

$$
f_{\Theta}(\theta)= \begin{cases}1 / 4, & \theta=0.2 \\ 1 / 2, & \theta=0.5 \\ 1 / 4, & \theta=0.8 \\ 0, & \text { annars }\end{cases}
$$



![](https://cdn.mathpix.com/cropped/2022_11_17_b2b9ad02dc0ed3316331g-03.jpg?height=531&width=729&top_left_y=239&top_left_x=687)

Vi singlar nu det valda myntet $n$ gånger. Antalet gånger den hamnar med på klave $X$ har då fördelningen $\operatorname{Bin}(n, \theta)$, vilket ger

$$
f_{X \mid \Theta}(x \mid \theta)=\left(\begin{array}{l}
n \\
x
\end{array}\right) \theta^{x}(1-\theta)^{n-x} .
$$

Vi har alltså en fördelning för $X$ betingad med avseende på parametern $\Theta$.

Den marginella fördelningen är då

$$
\begin{aligned}
f_{x}(x) &=\sum_{\theta \in\{0.2,0.5,0.8\}} f_{X \mid \Theta}(x \mid \theta) f_{\Theta}(\theta) \\
&=\sum_{\theta \in\{0.2,0.5,0.8\}}\left(\begin{array}{l}
n \\
x
\end{array}\right) \theta^{x}(1-\theta)^{n-x} f_{\Theta}(\theta) \\
&=\left(\begin{array}{l}
n \\
x
\end{array}\right)\left(0.2^{x} 0.8^{n-x} \cdot \frac{1}{4}+0.8^{x} 0.2^{n-x} \cdot \frac{1}{4}+0.5^{n} \cdot \frac{1}{2}\right) \\
&=\left(\begin{array}{l}
n \\
x
\end{array}\right)\left(\frac{0.2^{x} 0.8^{n-x}+0.8^{x} 0.2^{n-x}}{4}+\frac{0.5^{n}}{2}\right) .
\end{aligned}
$$

Detta är alltså fördelningen som vi får om vi drar ett mynt, singlar det $n$ gånger och räknar antalet klavar.

![](https://cdn.mathpix.com/cropped/2022_11_17_b2b9ad02dc0ed3316331g-03.jpg?height=564&width=1293&top_left_y=1965&top_left_x=427)



\section{Aposteriorifördelning}

Datafördelningen beskriver hur vår mätdata genereras utifrån parametrar dragna från apriorifördelningen - detta bildar en stokastisk modell för datan. För att lösa inferensproblemet vill vi gå åt andra hållet: från mätdata och datafördelningen vill vi bestämma en fördelning för parametern. Verktyget som låter oss göra detta är Bayes sats. Om vi låter $f_{\Theta \mid x}(\theta \mid x)$ beteckna den betingade fördelningen för $\Theta$ givet observationen $X=x$ får vi

$$
f_{\Theta \mid X}(\theta \mid x)=\frac{f_{X \mid \Theta}(x \mid \theta) f_{\Theta}(\theta)}{f_{X}(x)} .
$$

Fördelningen $f_{\Theta \mid x}(\theta \mid x)$ kallas aposteriorifördelningen (a posteriori betyder $i$ efterhand på latin) och motsvarar alltså vår uppfattning av parametern $\theta$ givet att vi observerat datan $x$. Detta kan ses som en "uppdatering" av apriorifördelningen $f_{\Theta}(\theta)$. Innan vi observerat något överhuvudtaget antar vi att $\theta$ har fördelningen $f_{\Theta}(\theta)$. Vi korrigerar sedan denna efter att ha observerat $x$ genom Bayes sats, vilket get aposteriorifördelningen $f_{\Theta \mid x}(\theta \mid x)$. Denna fördelning kan nu användas för att dra olika slutsatser om parametern eller som apriorifördelning för ett annat experiment. Exempel 2. I slantsinglingsexemplet ovan har vi

$$
\begin{aligned}
f_{\Theta \mid x}(\theta \mid x) &=\frac{\left(\begin{array}{l}
n \\
x
\end{array}\right) \theta^{x}(1-\theta)^{n-x} f_{\Theta}(\theta)}{\left(\begin{array}{l}
n \\
x
\end{array}\right)\left(\left(0.2^{x} 0.8^{n-x}+0.8^{x} 0.2^{n-x}\right) / 4+0.5^{n} / 2\right)} \\
&=\frac{\theta^{x}(1-\theta)^{n-x} f_{\Theta}(\theta)}{\left(0.2^{x} 0.8^{n-x}+0.8^{x} 0.2^{n-x}\right) / 4+0.5^{n} / 2^{\prime}}
\end{aligned}
$$

för $\theta=0.2,0.5,0.8$. Detta motsvarar alltså vår uppdaterade uppfattning om vilket mynt som valts ut givet att vi singlat myntet $n$ gånger och fått $x$ klavar.

Om $n=20$ och $x=14$ får vi

$$
f_{\Theta \mid x}(\theta \mid 14) \approx \begin{cases}9.1 \cdot 10^{-6}, & \theta=0.2, \\ 0.40, & \theta=0.5 \\ 0.60, & \theta=0.8, \\ 0, & \text { annars. }\end{cases}
$$

Sannolikheten att vi drog myntet med $\theta=0.2$ är alltså betydligt mindre än innan vi utförde experimentet. Samtidigt har inte sannolikheten att vi drog $\theta=0.5$ ändrats mycket, medan det har blivit mycket mer sannolikt att $\theta=0.8$.

Om vi istället hade fått $x=16$ utav $n=20$ singlingar får vi aposteriorifördelningen

$$
f_{\Theta \mid x}(\theta \mid 16) \approx \begin{cases}5.7 \cdot 10^{-8}, & \theta=0.2, \\ 0.041, & \theta=0.5, \\ 0.96, & \theta=0.8 \\ 0, & \text { annars. }\end{cases}
$$

Sannolikheten att vi drog $\theta=0.8$ är nu mycket större än de andra möjligheterna. Aposteriorifördelningen beror också på hur många singlingar $n$ vi utför. Om $n=40$ och $x=32$ får vi

$$
f_{\Theta \mid x}(\theta \mid 32) \approx \begin{cases}3.5 \cdot 10^{-15}, & \theta=0.2, \\ 9 \cdot 10^{-4}, & \theta=0.5, \\ 0.999, & \theta=0.8, \\ 0, & \text { annars. }\end{cases}
$$

Notera att kvoten $x / n$ är fortfarande densamma som ovan (0.8) men nu har vi en mycket större sannolikhet att $\theta=0.8$. Datan har alltså en större uppdateringseffekt på aposteriorifördelningen eftersom vi har ett större stickprov ( $n=40$ istället för $n=20$ ).

![](https://cdn.mathpix.com/cropped/2022_11_17_b2b9ad02dc0ed3316331g-05.jpg?height=431&width=1366&top_left_y=855&top_left_x=366)

Parametern $\Theta$ behöver inte ha en diskret fördelning utan denna kan också vara kontinuerlig, som vi ser i följande exempel.

Exempel 3. Antag att $\Theta \sim \mathrm{U}([0,1])$, dvs. $\Theta$ är likformigt fördelad över intervallet $[0,1]$. Detta motsvarar en så kallad icke-informativ apriorifördelning - den säger egentligen ingenting om parametern och vi gör alltså inga antaganden. Vi har då

$$
f_{\Theta}(\theta)= \begin{cases}1, & 0 \leq \theta \leq 1, \\ 0, & \text { annars } .\end{cases}
$$

Som innan antar vi att datafördelningen för $X \mid \theta$ är $\operatorname{Bin}(n, \theta)$. Marginalfördelningen för $X$ blir då

$$
f_{x}(x)=\int_{0}^{1}\left(\begin{array}{l}
n \\
x
\end{array}\right) \theta^{x}(1-\theta)^{n-x} d \theta=\left(\begin{array}{l}
n \\
x
\end{array}\right) \int_{0}^{1} \theta^{x}(1-\theta)^{n-x} d \theta
$$

Integralen kan skrivas med hjälp av betafunktionen $B(\alpha, \beta)$ som ges av

$$
B(\alpha, \beta)=\int_{0}^{1} t^{\alpha-1}(1-t)^{\beta-1} d t=\frac{\Gamma(\alpha) \Gamma(\beta)}{\Gamma(\alpha+\beta)},
$$

där $\Gamma(\alpha)$ är gammafunktionen $\Gamma(\alpha)=\int_{0}^{+\infty} e^{-u} u^{\alpha-1} d u$. För heltal $k$, $\ell$ har $v i \Gamma(k)=$ $(k-1) !$ och $\Gamma(\ell)=(\ell-1) !$, vilket ger

$$
B(k, \ell)=\frac{(k-1) !(\ell-1) !}{(k+\ell-1) !} .
$$

Stoppar vi in detta i vår uttryck för $m(x)$ får vi

$$
f_{x}(x)=\left(\begin{array}{l}
n \\
x
\end{array}\right) B(x+1, n-x+1)=\frac{n !}{(n-x) ! x !} \cdot \frac{x !(n-x) !}{(n+1) !}=\frac{1}{n+1} .
$$

Med andra ord är $X$ likformigt fördelad över $x=0,1, \ldots, n$.

Aposteriorifördelningen är nu

$$
\begin{aligned}
f_{\Theta \mid x}(\theta \mid x) &=\frac{f_{x \mid \Theta}(x \mid \theta) f_{\Theta}(\theta)}{m(x)}=\frac{\left(\begin{array}{l}
n \\
x
\end{array}\right) \theta^{x}(1-\theta)^{n-x}}{1 /(n+1)} \\
&=\frac{(n+1) n !}{(n-x) ! x !} \theta^{x}(1-\theta)^{n-x} \\
&=\frac{(n+1) !}{(n-x) ! x !} \theta^{x}(1-\theta)^{n-x} \\
&=\frac{1}{B(x+1, n-x+1)} \theta^{x}(1-\theta)^{n-x}
\end{aligned}
$$

![](https://cdn.mathpix.com/cropped/2022_11_17_b2b9ad02dc0ed3316331g-06.jpg?height=509&width=721&top_left_y=1174&top_left_x=686)

Låt oss anta att $n=20$ och $x=16$. Vi får då en fördelning som lutar starkt mot $\theta=1$, vilket är rimligt givet det stora antalet klavar som erhölls.

Aposteriorifördelningen som beräknades ovan kallas för en betafördelning. Dessa har parametrarna $\alpha, \beta$, betecknas $\operatorname{Beta}(\alpha, \beta)$ och har täthetsfunktionen

$$
f_{\Theta}(\theta)= \begin{cases}\frac{1}{B(\alpha, \beta)} \theta^{\alpha-1}(1-\theta)^{\beta-1}, & 0 \leq \theta \leq 1 \\ 0, & \text { annars. }\end{cases}
$$

Ovan har vi alltså att för $\Theta \sim U([0,1])$ och $X \mid \Theta=\theta \sim \operatorname{Bin}(n, \theta)$ har vi aposteriorifördelningen $\Theta \mid X=x \sim \operatorname{Beta}(1+x, 1+n-x)$. Ett specialfall av betafördelningen är då $\alpha=\beta=1$, vilket ger $U([0,1])$. $\operatorname{Om~} \Theta \sim \operatorname{Beta}(\alpha, \beta)$ har vi

$$
\begin{aligned}
\mathrm{E}[\Theta] &=\frac{1}{B(\alpha, \beta)} \int_{0}^{1} \theta \cdot \theta^{\alpha-1}(1-\theta)^{\beta-1} d \theta \\
&=\frac{1}{B(\alpha, \beta)} \int_{0}^{1} \theta^{(\alpha+1)-1}(1-\theta)^{\beta-1} d \theta \\
&=\frac{1}{B(\alpha, \beta)} \cdot B(\alpha+1, \beta)=\frac{\Gamma(\alpha+\beta)}{\Gamma(\alpha) \Gamma(\beta)} \cdot \frac{\Gamma(\alpha+1) \Gamma(\beta)}{\Gamma(\alpha+\beta+1)} \\
&=\frac{\Gamma(\alpha+\beta)}{\Gamma(\alpha)} \cdot \frac{\alpha \Gamma(\alpha)}{(\alpha+\beta) \Gamma(\alpha+\beta)}=\frac{\alpha}{\alpha+\beta},
\end{aligned}
$$

där vi har utnyttjat definitionen av betafunktionen $B(\alpha, \beta)$ och att $\Gamma(x+1)=x \Gamma(x)$. På samma sätt får vi

$$
\mathrm{E}\left[\Theta^{2}\right]=\frac{\alpha(\alpha+1)}{(\alpha+\beta)(\alpha+\beta+1)},
$$

vilket ger

$$
\mathrm{V}[\Theta]=\mathrm{E}\left[\Theta^{2}\right]-\mathrm{E}[\Theta]^{2}=\frac{\alpha \beta}{(\alpha+\beta)^{2}(\alpha+\beta+1)}
$$

Parametrarna $\alpha$ och $\beta$ bestämmer alltså hur sannolikheten är fördelad mellan noll och ett. Om $\alpha=\beta$ är den symmetrisk runt $1 / 2$, men om $\alpha \gg \beta$ lutar den mot ett och om $\beta \gg \alpha$ lutar den mot noll. Summan $\alpha+\beta$ kontrollerar osäkerheten: om summan är stor är fördelningen mer koncentrerad runt väntevärdet, annars är den diffus.

Det visar sig att betafördelningen inte bara uppstår som en aposteriorifördelning när vi har apriorifördelningen $U([0,1])$ och datafördelningen $X \mid \Theta=\theta \sim \operatorname{Bin}(n, \theta)$. Den är också en naturlig apriorifördelning i detta sammanhang.

Låt $\Theta \sim \operatorname{Beta}(\alpha, \beta)$. Om $X \mid \Theta=\theta \sim \operatorname{Bin}(n, \theta)$ har vi

$$
\begin{aligned}
f_{X \mid \Theta}(x \mid \theta) f_{\Theta}(\theta) &=\left(\begin{array}{l}
n \\
x
\end{array}\right) \theta^{\chi}(1-\theta)^{n-x} \frac{1}{B(\alpha, \beta)} \theta^{\alpha-1}(1-\theta)^{\beta-1} \\
&=\frac{\left(\begin{array}{l}
n \\
x
\end{array}\right)}{B(\alpha, \beta)} \theta^{\alpha+x-1}(1-\theta)^{\beta+n-x-1} .
\end{aligned}
$$

Om vi integrerar detta med avseende på $\theta$ över $[0,1]$ får vi

$$
\begin{aligned}
f_{x}(x) &=\frac{\left(\begin{array}{l}
n \\
x
\end{array}\right)}{B(\alpha, \beta)} \int_{0}^{1} \theta^{\alpha+x-1}(1-\theta)^{\beta+n-x-1} d \theta \\
&=\frac{\left(\begin{array}{l}
n \\
x
\end{array}\right)}{B(\alpha, \beta)} \cdot B(\alpha+x, \beta+n-x),
\end{aligned}
$$

där vi återigen utnyttjat definitionen av betafunktionen $B(\alpha, \beta)$. Aposteriorifördelningen blir då

$$
\begin{aligned}
f_{\Theta \mid X}(\theta \mid x) &=\frac{f_{X \mid \Theta}(x \mid \theta) f_{\Theta}(\theta)}{f_{X}(x)} \\
&=\frac{\theta^{\alpha+x-1}(1-\theta)^{\beta+n-x-1}}{B(\alpha+x, \beta+n-x)} .
\end{aligned}
$$

Med andra ord har vi $\Theta \mid X=x \sim \operatorname{Beta}(\alpha+x, \beta+n-x)$. Uppdateringen av apriorifördelningen $\operatorname{Beta}(\alpha, \beta)$ med utfallet $x$ av $X \mid \Theta=\theta \sim \operatorname{Bin}(n, \theta)$ är alltså aposteriorifördelningen $\operatorname{Beta}(\alpha+x, \beta+n-x)$. Med andra ord räcker det att uppdatera parametrarna enligt

$$
(\alpha, \beta) \mapsto(\alpha+x, \beta+n-x) .
$$

Dessa typer av relationer håller för många fördelningar. Man säger att betafördelningarna bildar en konjugatfamilj för binomialfördelningen $\operatorname{Bin}(n, \theta)$ med avseende på parametern $\theta$.

För normalfördelningen med känd standardavvikelse $\sigma$ har vi att konjugatfamiljen är normalfördelningarna själva. Om $\Theta \sim N\left(\mu_{0}, \tau_{0}\right)$ och $X \mid \Theta=\theta \sim N(\theta, \sigma)$ har vi att $\Theta \mid X=x \sim \mathrm{N}\left(\mu_{1}, \tau_{1}\right)$ där

$$
\mu_{1}=\tau_{1}^{2}\left(\frac{\mu_{0}}{\tau_{0}^{2}}+\frac{x}{\sigma^{2}}\right) \quad \text { och } \tau_{1}=1 / \sqrt{\frac{1}{\tau_{0}^{2}}+\frac{1}{\sigma^{2}}} .
$$

Den nya datapunkten bakas alltså in i fördelningen för $\Theta$ genom att viktas med avseende på datafördelningens standardavvikelse $\sigma$ och apriorifördelningens standardavvikelse. Vi skriver detta som följande uppdatering av parametrarna:

$$
\left(\mu_{0}, \tau_{0}\right) \mapsto\left(\left(\frac{\mu_{0}}{\tau_{0}^{2}}+\frac{x}{\sigma^{2}}\right) /\left(\frac{1}{\tau_{0}^{2}}+\frac{1}{\sigma^{2}}\right), 1 / \sqrt{\frac{1}{\tau_{0}^{2}}+\frac{1}{\sigma^{2}}}\right) .
$$

För Poissonfördelningen $\operatorname{Po}(\theta)$ som datafördelning består konjugatfamiljen av gammafördelningarna $\operatorname{Gamma}(c, \lambda)$. Om $\Theta \sim \operatorname{Gamma}(c, \lambda)$ och $X \mid \Theta=\theta \sim \operatorname{Po}(\theta)$ har vi att utfallet $x$ ger $\Theta \mid X=x \sim \operatorname{Gamma}(c+x, \lambda+1)$. Vi skriver detta som uppdateringen

$$
(c, \lambda) \mapsto(c+x, \lambda+1) \text {. }
$$

Till sist har vi exponentialfördelningen $\operatorname{Exp}(\theta)$ som också har gammafördelningarna som konjugatfamilj. Om $\Theta \sim \operatorname{Gamma}(c, \lambda)$ och $X \mid \Theta=\theta \sim \operatorname{Exp}(\theta)$ har vi att utfallet $x$ ger $\Theta \mid X=x \sim \operatorname{Gamma}(c+1, \lambda+x)$. Vi skriver detta som

$$
(c, \lambda) \mapsto(c+1, \lambda+x) \text {. }
$$

Konjugatfamiljer är naturliga på det sättet att de förenklar uppdateringsprocessen, men de behöver inte alltid vara passande apriorifördelningar för alla problem. Nuförtiden finns det effektiva beräkningsmetoder som kan approximera aposteriorifördelningarna numeriskt i de fall då icke-konjugata apriorifördelningar används. 

\section{Aposteriorifördelning med flera värden}

Uppdateringsformlerna som vi gav ovan går att generalisera till flera mätvärden. Vi börjar med binomialfördelningen. Antag att $\Theta \sim \operatorname{Beta}(\alpha, \beta)$ och $X_{1} \mid \Theta=\theta \sim$ $\operatorname{Bin}\left(n_{1}, \theta\right), x_{2} \mid \Theta=\theta \sim \operatorname{Bin}\left(n_{2}, \theta\right)$ för $X_{1}$ och $x_{2}$ oberoende givet $\Theta$. Om $x_{1}$ och $x_{2}$ är utfall av $X_{1}$ respektive $X_{2}$ så har vi först uppdateringen med avseende på $X_{1}=x_{1}$ :

$$
(\alpha, \beta) \mapsto\left(\alpha+x_{1}, \beta+n_{1}-x_{1}\right)
$$

Med andra ord har vi aposteriorifördelningen $\Theta \mid X_{1}=x_{1} \sim \operatorname{Beta}\left(\alpha+x_{1}, \beta+n_{1}-x_{1}\right)$. Vi tar nu detta som vår apriorifördelning och uppdaterar den med utfallet $x_{2}=x_{2}$, vilket ger

$$
\left(\alpha+x_{1}, \beta+n_{1}-x_{1}\right) \mapsto\left(\alpha+x_{1}+x_{2}, \beta+n_{1}+n_{2}-x_{1}-x_{2}\right)
$$

Vi har då att $\Theta \mid X_{1}=x_{1}, x_{2}=x_{2}$ har fördelningen $\operatorname{Beta}\left(\alpha+x_{1}+x_{2}, \beta+n_{1}+n_{2}-x_{1}-x_{2}\right)$. Notera att vi kan också erhålla detta resultat genom att bilda $Y=X_{1}+X_{2}$. Sedan innan vet vi då att $Y \mid \Theta=\theta \sim \operatorname{Bin}\left(n_{1}+n_{2}, \theta\right)$ eftersom sannolikheten att ett försök lyckas $(\theta)$ är densamma för både $X_{1}$ och $X_{2}$. Om vi tillämpar den uppdateringsregeln för ett utfall med utfallet $Y=x_{1}+x_{2}$ får vi

$$
(\alpha, \beta) \mapsto\left(\alpha+x_{1}+x_{2}, \beta+n_{1}+n_{2}-x_{1}-x_{2}\right)
$$

dvs. samma aposteriorifördelning som innan. Det spelar alltså ingen roll om vi gör två separata uppdateringar eller om vi uppdaterar med avseende på båda mätvärdena samtidigt.

Vi kan skriva detta som ett förhållande mellan aposteriorifördelningarna $f_{\Theta \mid x_{1}, x_{2}}\left(\theta \mid x_{1}, x_{2}\right)$ (fördelningen för $\Theta$ givet både $x_{1}=x_{1}$ och $x_{2}=x_{2}$ ) och $f_{\Theta \mid x_{1}}\left(\theta \mid x_{1}\right)$ (fördelningen för $\Theta$ givet bara $\left.X_{1}=x_{1}\right)$. För $\Theta \sim \operatorname{Beta}(\alpha, \beta)$ och oberoende $X_{1} \mid \Theta=\theta \sim \operatorname{Bin}\left(n_{1}, \theta\right)$, $x_{2} \mid \Theta=\theta \sim \operatorname{Bin}\left(n_{2}, \theta\right)$ har vi då visat

$$
f_{\Theta \mid x_{1}, x_{2}}\left(\theta \mid x_{1}, x_{2}\right)=\frac{f_{X_{2} \mid \Theta}\left(x_{2} \mid \theta\right) f_{\Theta \mid X_{1}}\left(\theta \mid x_{1}\right)}{\int_{\Omega_{\theta}} f_{X_{2} \mid \Theta}\left(x_{2} \mid \theta\right) f_{\Theta \mid X_{1}}\left(\theta \mid x_{1}\right) d \theta} .
$$

Det visar sig att formeln ovan gäller mer allmänt så länge $X_{1}$ och $X_{2}$ är oberoende givet $\Theta$.

Sats 4. Antag att $X_{1}$ och $X_{2}$ är oberoende givet $\Theta$. Då gäller att

$$
f_{\Theta \mid x_{1}, x_{2}}\left(\theta \mid x_{1}, x_{2}\right)=\frac{f_{X_{2} \mid \Theta}\left(x_{2} \mid \theta\right) f_{\Theta \mid X_{1}}\left(\theta \mid x_{1}\right)}{\int_{\Omega_{\theta}} f_{X_{2} \mid \Theta}\left(x_{2} \mid \theta\right) f_{\Theta \mid X_{1}}\left(\theta \mid x_{1}\right) d \theta} .
$$

Bevis. Vi skriver först om $f_{X_{1}, x_{2} \mid \Theta}\left(x_{1}, x_{2} \mid \theta\right)$ som $f_{X_{2} \mid x_{1}, \Theta}\left(x_{2} \mid x_{1}, \theta\right) f_{X_{1} \mid \Theta}\left(x_{1} \mid \theta\right)$, vilket fås ur definitionen för betingad sannolikhet. Eftersom $X_{1}$ och $X_{2}$ är oberoende givet $\theta$ har vi vidare att $f_{X_{2} \mid x_{1}, \Theta}\left(x_{2} \mid x_{1}, \theta\right)=f_{X_{2} \mid \Theta}\left(x_{2} \mid \theta\right)$. Vi stoppar nu in detta i Bayes sats, vilket ger

$$
\begin{aligned}
& f_{\Theta \mid x_{1}, x_{2}}\left(\theta \mid x_{1}, x_{2}\right) \\
=& \frac{f_{X_{1}, x_{2} \mid \Theta}\left(x_{1}, x_{2} \mid \theta\right) f_{\Theta}(\theta)}{\int_{\Omega_{\theta}} f_{X_{1}, x_{2} \mid \Theta}\left(x_{1}, x_{2} \mid \theta\right) f_{\Theta}(\theta) d \theta} \\
=& \frac{f_{X_{2} \mid \Theta}\left(x_{2} \mid \theta\right) f_{X_{1} \mid \Theta}\left(x_{1} \mid \theta\right) f_{\Theta}(\theta)}{\int_{\Omega_{\theta}} f_{X_{2} \mid \Theta}\left(x_{2} \mid \theta\right) f_{X_{1} \mid \Theta}\left(x_{1} \mid \theta\right) f_{\Theta}(\theta) d \theta} \\
=& f_{X_{2} \mid \Theta}\left(x_{2} \mid \theta\right) \cdot \frac{f_{X_{1} \mid \Theta}\left(x_{1} \mid \theta\right) f_{\Theta}(\theta)}{\int_{\Omega_{\theta}} f_{X_{1} \mid \Theta}\left(x_{1} \mid \theta\right) f_{\Theta}(\theta) d \theta} \cdot \frac{\int_{\Omega_{\theta}} f_{X_{1} \mid \Theta}\left(x_{1} \mid \theta\right) f_{\Theta}(\theta) d \theta}{\int_{\Omega_{\theta}} f_{X_{2} \mid \Theta}\left(x_{2} \mid \theta\right) f_{X_{1} \mid \Theta}\left(x_{1} \mid \theta\right) f_{\Theta}(\theta) d \theta}
\end{aligned}
$$

Eftersom

$$
f_{\Theta \mid X_{1}}\left(\theta \mid x_{1}\right)=\frac{f_{X_{1} \mid \Theta}\left(x_{1} \mid \theta\right) f_{\Theta}(\theta)}{\int_{\Omega_{\theta}} f_{X_{1} \mid \Theta}\left(x_{1} \mid \theta\right) f_{\Theta}(\theta) d \theta}
$$

har vi då

$$
f_{\Theta \mid x_{1}, x_{2}}\left(\theta \mid x_{1}, x_{2}\right)=f_{X_{2} \mid \Theta}\left(x_{2} \mid \theta\right) \cdot f_{\Theta \mid x_{1}}\left(\theta \mid x_{1}\right) \cdot \frac{1}{\int_{\Omega_{\theta}} f_{X_{2} \mid \Theta}\left(x_{2} \mid \theta\right) f_{\Theta \mid x_{1}}\left(\theta \mid x_{1}\right) d \theta},
$$

vilket skulle visas.

Vi kan tillämpa satsen ovan flera gånger för att få aposteriorifördelningen för $\Theta \sim$ $\operatorname{Beta}(\alpha, \beta)$ givet flera utfall $x_{1}, x_{2}, \ldots, x_{k}$ från de oberoende stokastiska variablerna $X_{1}\left|\Theta=\theta \sim \operatorname{Bin}\left(n_{1}, \theta\right), X_{2}\right| \Theta=\theta \sim \operatorname{Bin}\left(n_{2}, \theta\right), \ldots, X_{k} \mid \Theta=\theta \sim \operatorname{Bin}\left(n_{k}, \theta\right)$. Detta ger

$$
(\alpha, \beta) \mapsto \operatorname{Beta}\left(\alpha+\sum_{i=1}^{k} x_{i}, \beta+\sum_{i=1}^{k} n_{i}-x_{i}\right) \text {. }
$$

Vi kan också tillämpa satsen på de andra uppdateringsreglerna vi undersökte tidigare. För $\Theta \sim N\left(\mu_{0}, \tau_{0}\right)$ och oberoende $X_{1}\left|\Theta=\theta \sim N(\theta, \sigma), X_{2}\right| \Theta=\theta \sim N(\theta, \sigma), \ldots, X_{k} \mid \Theta=$ $\theta \sim \mathrm{N}(\theta, \sigma)$ med utfallen $x_{1}, x_{2}, \ldots, x_{k}$ har vi

$$
\left(\mu_{0}, \tau_{0}\right) \mapsto\left(\left(\frac{\mu_{0}}{\tau_{0}^{2}}+\frac{\sum_{i=1}^{k} x_{i}}{\sigma^{2}}\right) /\left(\frac{1}{\tau_{0}^{2}}+\frac{k}{\sigma^{2}}\right), \frac{1}{\sqrt{\frac{1}{\tau_{0}^{2}}+\frac{k}{\sigma^{2}}}}\right) \text {. }
$$

För $\Theta \sim \operatorname{Gamma}(c, \lambda)$ och oberoende $X_{1}\left|\Theta=\theta \sim \operatorname{Po}(\theta), X_{2}\right| \Theta=\theta \sim \operatorname{Po}(\theta), \ldots, X_{k} \mid \Theta=$ $\theta \sim \operatorname{Po}(\theta)$ med utfall $x_{1}, x_{2}, \ldots, x_{k}$ har vi

$$
(c, \lambda) \mapsto\left(c+\sum_{i=1}^{k} x_{i}, \lambda+k\right) \text {. }
$$

Slutligen för $\Theta \sim \operatorname{Gamma}(c, \lambda)$ och oberoende $X_{1}\left|\Theta=\theta \sim \operatorname{Exp}(\theta), X_{2}\right| \Theta=\theta \sim$ $\operatorname{Exp}(\theta), \ldots, x_{k} \mid \Theta=\theta \sim \operatorname{Po}(\theta)$ med utfall $x_{1}, x_{2}, \ldots, x_{k}$ har vi

$$
(c, \lambda) \mapsto\left(c+k, \lambda+\sum_{i=1}^{k} x_{i}\right) \text {. }
$$



\section{Punktskattningar}

Aposteriorifördelningen är intressant i sig i och med att den specificerar vad vi tror att en parameter antar för ett värde. Man kan, till exempel, betrakta de olika kvantilerna för att bilda ett intervall där parametern ligger med stor sannolikhet.

Ofta kan det dock vara intressant att sammanfatta aposteriorifördelningen på något sätt och bilda en punktskattning. Ett vanligt sätt att åstadkomma detta är genom att bilda det betingade väntevärdet $\mathrm{E}[\Theta \mid X=x]$. Detta motsvarar alltså det värde som parametern antar i genomsnitt under den skattade aposteriorifördelningen.

För fallet med $\Theta \sim \operatorname{Beta}(\alpha, \beta)$ och $X \mid \Theta=\theta \sim \operatorname{Bin}(n, \theta)$ hade vi att utfallet $x$ gav uppdateringen

$$
(\alpha, \beta) \mapsto(\alpha+x, \beta+n-x) .
$$

Om vi jämför väntevärdet för apriorifördelningen med väntevärdet för aposteriorifördelningen får vi

$$
\mathrm{E}[\Theta]=\frac{\alpha}{\alpha+\beta} \text { och } \mathrm{E}[\Theta \mid X=x]=\frac{\alpha+x}{\alpha+\beta+n} .
$$

Det senare värdet kan skrivas om som

$$
\mathrm{E}[\Theta \mid X=x]=\frac{n}{\alpha+\beta+n} \cdot \frac{x}{n}+\frac{\alpha+\beta}{\alpha+\beta+n} \cdot \frac{\alpha}{\alpha+\beta} .
$$

Det betingade väntevärdet är alltså en slags kompromiss mellan aprioriväntevärdet och ML-skattningen $x / n$. När $n$ är litet dominerar aprioriväntevärdet (vi har då inte tillräckligt många datapunkter $n$ för att dominera apriorifördelningen), men när $n$ är stort närmar vi oss $x / n$. Vi såg samma sak för normalfördelningen ovan - ju starkare vår datapunkt (större $x$, mindre $\sigma$ ), desto mer dominerar datan över apriorifördelningen.

Exempel 5. Låt oss ta $\Theta \sim \operatorname{Beta}(2,2)$. Denna fördelning är koncentrerad runt $\mathrm{E}[\Theta]=1 / 2$ men avtar när vi närmar oss noll eller ett. $O m X \mid \Theta=\theta \sim \operatorname{Bin}(n, \theta)$ och $n=20$ med utfallet $x=18$ har vi

$$
\Theta \mid X=x \sim \operatorname{Beta}(2+18,2+2)=\operatorname{Beta}(20,4) .
$$

Det betingade väntevärdet är då

$$
\mathrm{E}[\Theta \mid X=x]=\frac{20}{20+4}=\frac{5}{6} \approx 0.83,
$$

vilket fortfarande ligger nära 1/2 men närmar sig ett. 

![](https://cdn.mathpix.com/cropped/2022_11_17_b2b9ad02dc0ed3316331g-12.jpg?height=507&width=724&top_left_y=229&top_left_x=684)

Vi kan också jämföra standardavvikelserna hos fördelningarna. Enligt formeln för variansen av betafördelningen ovan får vi

$$
\mathrm{V}[\Theta]=\frac{1}{20} \quad \text { och } \quad \mathrm{V}[\Theta \mid X=\chi]=\frac{1}{180}
$$

Vi har alltså $\mathrm{D}[\Theta]=1 / 2 \sqrt{5}$ och $\mathrm{D}[\Theta \mid X=\chi]=1 / 6 \sqrt{5}$. Standardavvikelsen har reducerats med en faktor tre.

Fenomenet ovan är typiskt för aposteriorifördelningar - när vi uppdaterar apriorifördelningen så minskar standardavvikelsen i genomsnitt. Vi kan visa detta genom att använda formeln för den betingade variansen som vi tog fram tidigare i kursen:

$$
\mathrm{V}[\Theta]=\mathrm{E}[\mathrm{V}[\Theta \mid X]]+\mathrm{V}[\mathrm{E}[\Theta \mid X]]
$$

Eftersom $V[E[\Theta \mid X]] \geq 0$ per definition får vi

$$
\mathrm{E}[\mathrm{V}[\Theta \mid X]] \leq \mathrm{V}[\Theta]
$$

Med andra ord så är den genomsnittliga betingade variansen (där vi har medelvärdesbildat över alla möjliga mätdata $X$ ) mindre än apriorivariansen. Hur stor den här reduktionen är beror på variansen hos det betingade väntevärdet $\mathrm{E}[\Theta \mid X]$. Om denna är stor, dvs. aposteriorifördelningen anpassar sig väl efter datan, så kommer vi ha en mindre betingad varians $\vee[\Theta \mid X]$, i genomsnitt.

En annan sammanfattning av aposteriorifördelningen fås om vi betraktar dess maximum, dvs. det $\theta$ som maximerar $f_{\Theta \mid x}(\theta \mid x)$. Denna punkt kallas maximum a posterioriskattning (MAP-skattning). För betafördelningen $\operatorname{Beta}(\alpha, \beta)$ har vi, till exempel att

$$
\theta=\frac{\alpha-1}{\alpha+\beta-2}
$$

maximerar $f_{\Theta}(\theta)$. Med uppdateringen från binomialfördelningen får vi då

$$
\theta=\frac{\alpha+x-1}{\alpha+\beta+n-2}
$$

Återigen konvergerar denna mot $x / n$ då $n \rightarrow+\infty$.