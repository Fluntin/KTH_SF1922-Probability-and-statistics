\title{
Föreläsning nio
}

\author{
Joakim Andén
}

25 november 2022

\section{Maximum-likelihood-skattning}

I föregående föreläsning diskuterade vi två konkreta punktskattningar: det aritmetiska medelvärdet och stickprovsvariansen. Dessa visade sig ha ett antal användbara egenskaper som väntevärdesriktighet och konsistens (för stickprovsvariansen gäller detta inte allmänt men för många fördelningar, som till exempel normalfördelningen). Frågan kvarstår dock om hur man går till väga för att konstruera punktskattningar mer allmänt för olika parametrar.

Ett sätt går ut på att betrakta hur sannolikheten för erhållna mätvärden varierar med valet av parameter. Låt oss först introducera notation som klargör detta beroende. Vi antar att $\theta$ är en parameter med värde i ett parameterrum $\Sigma_{\theta}$. I vår modell skriver vi då $P(A ; \theta)$ för sannolikheten att $A$ inträffar när parametern är $\theta$. På samma sätt skriver vi sannolikhetsfunktionen för diskreta stokastiska variabler som $p_{x}(\chi ; \theta)$ och täthetsfunktionen för kontinuerliga stokastiska variabler som $f_{X}(\chi ; \theta)$. Om $\theta_{0}$ är den sanna parametern som genererat våra mätvärden följer dessa då sannolikhetsmåttet $\mathrm{P}\left(A ; \theta_{0}\right)$ och har sannolikhetsfunktionerna $p_{x}\left(\chi ; \theta_{0}\right)$ (i det diskreta fallet) eller täthetsfunktionerna $f_{X}\left(x ; \theta_{0}\right)$ (i det kontinuerliga fallet).

Antag nu att vi har $n$ oberoende diskreta stokastiska variabler $x_{1}, x_{2}, \ldots, x_{n}$, inte nödvändigtvis likafördelade, genererade enligt parametern $\theta=\theta_{0}$. Sannolikheten att dessa har utfallen $x_{1}, x_{2}, \ldots, x_{n}$ för parametern $\theta$ (dvs. ett annat värde på $\theta$ jämfört med $\theta_{0}$ ) är då

$$
\mathrm{P}\left(X_{1}=x_{1}, X_{2}=x_{2}, \ldots, X_{n}=x_{n} ; \theta\right)=\prod_{i=1}^{n} p_{X_{i}}\left(x_{i} ; \theta\right) .
$$

Antag att vi erhållit just dessa mätvärden $x_{1}, x_{2}, \ldots, x_{n}$. Vi kan då vända på beroendet och bilda funktionen

$$
L\left(\theta ; x_{1}, x_{2}, \ldots, x_{n}\right)=\prod_{i=1}^{n} p_{x_{i}}\left(x_{i} ; \theta\right)
$$

som kallas likelihoodfunktionen och motsvarar en sorts "rimlighet" för parametern $\theta$ - dvs. sannolikheten att just dessa värden erhållits om parametern är lika med $\theta$. Antag till exempel att vi har två parametervärden $\theta_{1}$ och $\theta_{2}$ samt dess sannolikhetsfunktioner $p_{x}\left(x ; \theta_{1}\right)$ och $p_{x}\left(x ; \theta_{2}\right)$. Om vi plottar dessa funktioner tillsammans med histogrammet av mätdata nedan så ser vi att en av parametervärdena verkar passa datan bättre än den andra.

![](https://cdn.mathpix.com/cropped/2022_11_17_b74524338d87b0a48427g-02.jpg?height=585&width=940&top_left_y=526&top_left_x=598)

För att skatta den sanna parametern $\theta_{0}$ antar vi att det $\theta$ som maximerar likelihoodfunktionen (dvs. det $\theta$ som är "rimligast") ligger nära $\theta_{0}$. Detta kallas likelihoodprincipen och vi kallar detta maximerande värde på $\theta$ för maximum-likelihoodskattningen, eller ML-skattningen, av $\theta$ och betecknar den som vanligt med $\theta_{\text {obs }}^{\star}$. Vi har då att ML-skattningen $\theta_{\text {obs }}^{\star}$ uppfyller

$$
L\left(\theta_{\text {obs }}^{\star} ; x_{1}, x_{2}, \ldots, x_{n}\right) \geq L\left(\theta ; x_{1}, x_{2}, \ldots, x_{n}\right)
$$

för alla $\theta \in \Omega_{\theta}$. Detta kan verka lite kontraintuitivt, men är en mycket naturlig skattning. Vi säger helt enkelt att för andra värden på $\theta$ så är sannolikheten mindre att vi fick de observerade mätvärdena. Om vi inte har väldigt otur och får väldigt osannolika utfall så borde detta hålla. Det visar sig att för större stickprovsstorlekar $n$ har vi mindre sannolikt otur och ML-skattningen blir mer exakt.

Exempel 1. Om vi återgår till opinionsundersökningen innan har vi utfallet $k=450$ av den diskreta stokastiska variabeln $X \sim \operatorname{Bin}(1000, p)$ och söker värdet på p. Vi har då likelihoodfunktionen

$$
L(p ; k)=p_{x}(x ; p)=\left(\begin{array}{c}
1000 \\
x
\end{array}\right) p^{x}(1-p)^{1000-x} .
$$

I vårt fall ger $x=450$ funktionen

$$
L(p ; 450)=\left(\begin{array}{c}
1000 \\
450
\end{array}\right) p^{450}(1-p)^{550},
$$

och vi söker värdet på p som maximerar denna funktion. 

![](https://cdn.mathpix.com/cropped/2022_11_17_b74524338d87b0a48427g-03.jpg?height=553&width=871&top_left_y=195&top_left_x=627)

Som den ser ut är likelihoodfunktionen lite komplicerad att maximera rätt av, så vi använder oss av ett användbart trick: logaritmering. Eftersom logaritmen är en strikt växande funktion så har detta ingen effekt på det p som maximerar funktionen. Logaritmen av likelihoodfunktionen är då

$$
\log L(p ; 450)=\log \left(\begin{array}{c}
1000 \\
450
\end{array}\right)+450 \log p+550 \log (1-p)
$$

Om vi deriverar med avseende på p fås

$$
\frac{d}{d p} \log L(p ; 450)=\frac{450}{p}-\frac{550}{1-p},
$$

vilket är noll då $p=450 /(550+450)=0.45$. För att verifiera att detta utgör ett maximum beräknar vi andraderivatan

$$
\frac{d^{2}}{d p^{2}} \log L(p ; 450)=-\frac{450}{p^{2}}-\frac{550}{(1-p)^{2}} .
$$

Eftersom denna är negativ är alla kritiska punkter (inklusive $p=0.45$ ) lokala maximum. Randvärdena $L(0 ; 450)=0$ och $L(1 ; 450)=0$ är mindre än $L(0.45 ; 450)>0$ så $p=0.45$ är ett globalt maximum för $L(p ; 450)$ över $[0,1]$. Med andra ord har vi $M L-s k a t t n i n g e n ~ p_{\text {obs }}^{\star}=0.45$, vilket överensstämmer med den intuitiva skattningen vi definierade i föregående föreläsning.

Logaritmtricket som tillämpades ovan är så vanligt att man brukar ge funktionen $\log L\left(\theta ; x_{1}, x_{2}, \ldots, x_{n}\right)$ ett speciellt namn: log-likelihoodfunktionen.

Fallet ovan med $n=1$ är inte så typiskt för parameterskattningar. Låt oss betrakta ett mer naturligt exempel.

Exempel 2. Låt återigen $X$ vara antalet telefonsamtal till kundservice hos ett visst mellan kl. 13:00 och $k$ l. 14:00. Om $X$ har fördelningen Po $(\mu)$ och vi observerar fem oberoende mätvärden $k_{1}, k_{2}, \ldots, k_{5}$ (ett värde för varje vardag under en vecka) får vi likelihoodfunktionen

$$
L\left(\mu ; k_{1}, k_{2}, \ldots, k_{5}\right)=\prod_{i=1}^{5} p_{x}\left(k_{i} ; \mu\right)=\prod_{i=1}^{5} \frac{\mu^{k_{i}} e^{-\mu}}{k_{i} !}=\mu^{\sum_{i=1}^{n} k_{i}} e^{-5 \mu} \prod_{i=1}^{5} \frac{1}{k_{i} !} .
$$



$$
\log L\left(\mu ; k_{1}, k_{2}, \ldots, k_{5}\right)=(\log \mu) \sum_{i=1}^{5} k_{i}-5 \mu+C
$$

där C är en konstant som inte beror på $\mu$. Derivatan är då

$$
\frac{d}{d \mu} \log L\left(\mu ; k_{1}, k_{2}, \ldots, k_{5}\right)=\frac{1}{\mu} \sum_{i=1}^{5} k_{i}-5
$$

vilket ger en kritisk punkt i $\mu=\frac{1}{5} \sum_{i=1}^{5} k_{i}$. Derivatan är strikt avtagande, så andraderivatan är negativ, vilket ger att den kritiska punkten är ett lokalt maximum. Randvärdet $\mu=0$ har $L\left(0 ; k_{1}, k_{2}, \ldots, k_{5}\right)=0$ så det lokala maximat $i \mu=\frac{1}{5} \sum_{i=1}^{5} k_{i}$ är ett globalt maximum. ML-skattningen av $\mu$ är då $\mu_{\mathrm{obs}}^{\star}=\frac{1}{5} \sum_{i=1}^{n} k_{i}$.

Antag att vi observerade värdena $11,13,10,14,12$, vi får då $\mu_{\text {obs }}^{\star}=60 / 5=12$.

För kontinuerliga stokastiska variabler återkommer problemet att sannolikheten att $X_{1}=x_{1}, X_{2}=x_{2}, \ldots, x_{n}=x_{n}$ är noll, oavsett vilket värde på $\theta$ vi använder. Som innan så antar vi istället att utfallen ligger i ett litet intervall av storlek $\Delta x$ och får då, eftersom variablerna är oberoende,

$$
\begin{aligned}
&\mathrm{P}\left(X_{1} \in\left[x_{1}, x_{1}+\Delta x\right], x_{2} \in\left[x_{2}, x_{2}+\Delta x\right], \ldots, x_{n} \in\left[x_{n}, x_{n}+\Delta x\right] ; \theta\right) \\
&\quad=\int_{u_{1}=x_{1}}^{x_{1}+\Delta x} \int_{u_{2}=x_{2}}^{x_{2}+\Delta x} \cdots \int_{u_{n}=x_{n}}^{x_{n}+\Delta x} \prod_{i=1}^{n} f_{x_{i}}\left(u_{i} ; \theta\right) d u_{n} \cdots d u_{2} d u_{1} \\
&=\Delta x^{n} \prod_{i=1}^{n} f_{x_{i}}\left(x_{i}+\alpha_{i} \Delta x ; \theta\right),
\end{aligned}
$$

för $\left(\alpha_{1}, \alpha_{2}, \ldots, \alpha_{n}\right) \in[0,1]^{n}$. Om vi nu tar kvoten av sannolikheterna för två parametrar $\theta_{1}$ och $\theta_{2}$ har vi

$$
\begin{aligned}
&\frac{\mathrm{P}\left(x_{1} \in\left[x_{1}, x_{1}+\Delta x\right], x_{2} \in\left[x_{2}, x_{2}+\Delta x\right], \ldots, x_{n} \in\left[x_{n}, x_{n}+\Delta x\right] ; \theta_{1}\right)}{\mathrm{P}\left(X_{1} \in\left[x_{1}, x_{1}+\Delta x\right], x_{2} \in\left[x_{2}, x_{2}+\Delta x\right], \ldots, x_{n} \in\left[x_{n}, x_{n}+\Delta x\right] ; \theta_{2}\right)} \\
&\quad=\frac{\prod_{i=1}^{n} f_{x_{i}}\left(x_{i}+\alpha_{i} \Delta x ; \theta_{1}\right)}{\prod_{i=1}^{n} f_{x_{i}}\left(x_{i}+\alpha_{i} \Delta x ; \theta_{2}\right)} .
\end{aligned}
$$

Låter vi $\Delta x \rightarrow 0$ ger detta kvoten

$$
\frac{\prod_{i=1}^{n} f_{X_{i}}\left(x_{i} ; \theta_{1}\right)}{\prod_{i=1}^{n} f_{X_{i}}\left(x_{i} ; \theta_{2}\right)} .
$$

Denna kvot kan alltså ses som hur sannolika mätvärdena är för parametern $\theta_{1}$ jämfört med parametern $\theta_{2}$. Om kvoten är större än ett antar vi att $\theta_{1}$ är ett "rimligare" parametervärde än $\theta_{2}$. Med bakgrund av detta definierar vi likelihoodfunktionen för oberoende kontinuerliga stokastiska variabler som

$$
L\left(\theta ; x_{1}, x_{2}, \ldots, x_{n}\right)=\prod_{i=1}^{n} f_{x_{i}}\left(x_{i} ; \theta\right),
$$

och ML-skattningen $\theta_{\text {obs }}^{\star}$ fås återigen som det $\theta$ som maximerar $L\left(\theta ; x_{1}, x_{2}, \ldots, x_{n}\right)$. Exempel 3. Låt $x_{1}, x_{2}, \ldots, X_{n}$ vara oberoende stokastiska variabler med fördelning $\operatorname{Exp}(\lambda), d v s$. med täthetsfunktioner

$$
f x_{i}\left(x_{i}\right)= \begin{cases}\lambda e^{-\lambda x_{i}}, & x \geq 0, \\ 0, & \text { annars }\end{cases}
$$

Detta ger likelihoodfunktionen

$$
L\left(\lambda ; x_{1}, x_{2}, \ldots, x_{n}\right)=\prod_{i=1}^{n} \lambda e^{-\lambda x_{i}}=\lambda^{n} e^{-\lambda \sum_{i=1}^{n} x_{i}},
$$

och vi får då log-likelihoodfunktionen

$$
\log L\left(\lambda ; x_{1}, x_{2}, \ldots, x_{n}\right)=n \log \lambda-\lambda \sum_{i=1}^{n} x_{i}
$$

Derivatan är

$$
\frac{d}{d \lambda} \log L\left(\lambda ; x_{1}, x_{2}, \ldots, x_{n}\right)=\frac{n}{\lambda}-\sum_{i=1}^{n} x_{i}
$$

som har nollstället $\lambda=\left(\frac{1}{n} \sum_{i=1}^{n} x_{i}\right)^{-1}=1 / \bar{\chi}$. Derivatan är strikt avtagande $i \lambda$ så detta är ett lokalt maximum. Likelihoodfunktionen är noll för $\lambda=0$, så det lokala maximat är globalt. Med andra ord har vi ML-skattningen $\lambda_{\text {obs }}^{\star}=1 \sqrt{\chi}$.

Om vi observerar värdena $2.1,0.3$ och $1.6$ blir ML-skattningen här $\lambda_{\text {obs }}^{\star}=3 /(2.1+$ $0.3+1.6)=3 / 3.6=5 / 6 \approx 0.833$.

Som vi ser följer metoden för att bestämma ML-skattningen ett par distinkta steg:

(i) Bilda likelihoodfunktionen: $L\left(\theta ; x_{1}, x_{2}, \ldots, x_{n}\right)$.

(ii) Logaritmera: $\log L\left(\theta ; x_{1}, x_{2}, \ldots, x_{n}\right)$.

(iii) Maximera.

Notera att vi inte alltid behöver logaritmera: ibland räcker det att arbeta med likelihoodfunktionen. Det sista steget kan göras genom att derivera log-likelihoodfunktionen, hitta nollställen, och bestämma ett globalt maximum genom att betrakta andraderivatan samt randvärderna. Detta är inte alltid möjligt (om likelihoodfunktionen är diskontinuerlig) eller önskvärt (om beräkning av derivatan eller andraderivatan är mycket arbetskrävande). Exempel 4. Som exempel på en annorlunda ML-skattning betraktar vi den likformiga fördelningen $\mathrm{U}[0, \theta]$. Givet oberoende stokastiska variabler $X_{1}, X_{2}, \ldots, X_{n}$ med denna fördelning har vi täthetsfunktionerna

$$
f_{X_{i}}\left(x_{i} ; \theta\right)= \begin{cases}\frac{1}{\theta}, & x_{i} \in[0, \theta], \\ 0, & \text { annars. }\end{cases}
$$

Detta ger likelihoodfunktionen

$$
L\left(\theta ; x_{1}, x_{2}, \ldots, x_{n}\right)=\prod_{i=1}^{n} f_{X_{i}}\left(x_{i}\right)= \begin{cases}\frac{1}{\theta^{n}}, & \theta \geq \max \left(x_{1}, x_{2}, \ldots, x_{n}\right), \\ 0, & \text { annars, }\end{cases}
$$

eftersom om någon $x_{i}>\theta$ så blir dess täthetsfunktion $f_{x_{i}}\left(x_{i} ; \theta\right)$ noll. Att någon av alla $x_{i}$ är större än $\theta$ är detsamma som att $\max \left(x_{1}, x_{2}, \ldots, x_{n}\right)>\theta$. Vi har då att en av täthetsfunktionerna är noll, så hela likelihoodfunktionen är noll i detta fall. Om $\max \left(x_{1}, x_{2}, \ldots, x_{n}\right) \leq \theta$ så är alla täthetsfunktioner lika med $1 / \theta$, så likelihoodfunktionen är då lika med $1 / \theta^{n}$.

För $\theta$ större än $\max \left(x_{1}, x_{2}, \ldots, x_{n}\right)$ så avtar alltså likelihoodfunktionen och för $\theta<$ $\max \left(x_{1}, x_{2}, \ldots, x_{n}\right)$ är den noll, vilket ger att maximum uppnås $i$

$$
\theta_{\text {obs }}^{\star}=\max \left(x_{1}, x_{2}, \ldots, x_{n}\right) \text {. }
$$

![](https://cdn.mathpix.com/cropped/2022_11_17_b74524338d87b0a48427g-06.jpg?height=551&width=942&top_left_y=1280&top_left_x=605)

Vad har denna punktskattning för egenskaper? Vi vet sedan tidigare att fördelningsfunktionen för maximum $\theta^{\star}=\max \left(X_{1}, X_{2}, \ldots, X_{n}\right)$ ges av

$$
F_{\theta^{\star}}(\theta)=\left(F_{X}(\theta)\right)^{n} .
$$

Om $\theta_{0}$ är den sanna parametern för fördelningen har vi

$$
F_{x}(x)= \begin{cases}\frac{x}{\theta_{0}}, & x \in\left[0, \theta_{0}\right], \\ 0, & \text { annars, }\end{cases}
$$

vilket ger

$$
F_{\theta^{*}}(\theta)= \begin{cases}\frac{\theta^{n}}{\theta_{0}^{n},} & \theta \in\left[0, \theta_{0}\right], \\ 0, & \text { annars. }\end{cases}
$$

Täthetsfunktionen är då

$$
f_{\theta^{\star}}(\theta)= \begin{cases}\frac{n \theta^{n-1}}{\theta_{0}^{n}}, & \theta \in\left[0, \theta_{0}\right], \\ 0, & \text { annars, }\end{cases}
$$

och väntevärdet blir

$$
\mathrm{E}\left[\theta^{\star}\right]=\int_{-\infty}^{+\infty} f_{\theta^{\star}}(\theta) d \theta=\int_{0}^{\theta_{0}} \theta \cdot \frac{n \theta^{n-1}}{\theta_{0}^{n}} d \theta=\frac{n}{n+1} \theta_{0} .
$$

ML-skattningen är alltså inte väntevärdesriktig.

Som tur är ger formeln ovan tillräckligt med information för att korrigera skattningen. Om vi tar

$$
\hat{\theta}_{\mathrm{obs}}=\frac{n+1}{n} \max \left(x_{1}, x_{2}, \ldots, x_{n}\right)
$$

är denna skattning väntevärdesriktig. Vi ser också att $\mathrm{E}\left[\max \left(X_{1}, X_{2}, \ldots, X_{n}\right)^{2}\right]=$ $\frac{n}{n+2} \theta_{0}^{2}$, vilket ger att $\mathrm{E}\left[\hat{\theta}^{2}\right]=\frac{(n+1)^{2}}{n(n+2)} \theta_{0}^{2}$ och $\mathrm{V}[\hat{\theta}]=\frac{\theta_{0}^{2}}{n(n+2)}$.

Som vi såg i exemplet är ML-skattningen inte alltid väntevärdesriktig, men kan ofta omvandlas till en väntevärdesriktig skattning genom att multiplicera med en konstant. Denna skattning kallas ofta för den korrigerade ML-skattningen.

ML-skattningar kan också definieras för fler än en parameter. Om vi har parametrarna $\theta_{1}, \theta_{2}, \ldots, \theta_{k}$ är likelihoodfunktionen för $X_{1}, X_{2}, \ldots, X_{n}$ oberoende stokastiska variabler

$$
\begin{aligned}
&L\left(\theta_{1}, \theta_{2}, \ldots, \theta_{k} ; x_{1}, x_{2}, \ldots, x_{n}\right)=\prod_{i=1}^{n} p_{x_{i}}\left(x_{i} ; \theta_{1}, \theta_{2}, \ldots, \theta_{k}\right), \quad \text { (diskreta fallet) } \\
&L\left(\theta_{1}, \theta_{2}, \ldots, \theta_{k} ; x_{1}, x_{2}, \ldots, x_{n}\right)=\prod_{i=1}^{n} f_{x_{i}}\left(x_{i} ; \theta_{1}, \theta_{2}, \ldots, \theta_{k}\right) . \quad \text { (kontinuerliga fallet) }
\end{aligned}
$$

ML-skattningen fås då för de värden på $\theta_{1}, \theta_{2}, \ldots, \theta_{k}$ som samtidigt maximerar likelihoodfunktionen.

Exempel 5. Antag att $X_{1}, X_{2}, \ldots, X_{n}$ är oberoende med fördelning $\mathrm{N}(\mu, \sigma)$. Låt oss skatta $\mu$ och $\sigma^{2}$. Likelihoodfunktionen är

$$
L\left(\mu, \sigma^{2} ; x_{1}, x_{2}, \ldots, x_{n}\right)=\prod_{i=1}^{n} \frac{1}{\sqrt{2 \pi \sigma^{2}}} e^{-\left(x_{i}-\mu\right)^{2} / 2 \sigma^{2}}=\frac{1}{\left(2 \pi \sigma^{2}\right)^{n / 2}} e^{-\frac{1}{2 \sigma^{2}} \sum_{i=1}^{n}\left(x_{i}-\mu\right)^{2}},
$$

vilket ger log-likelihoodfunktionen

$$
\log L\left(\mu, \sigma^{2} ; x_{1}, x_{2}, \ldots x_{n}\right)=-\frac{n}{2} \log \left(\sigma^{2}\right)-\frac{1}{2 \sigma^{2}} \sum_{i=1}^{n}\left(x_{i}-\mu\right)^{2}+C,
$$

där C är en konstant som inte beror på $\mu$ eller $\sigma^{2}$. För att maximera en tvådimensionell funktion söker vi först dess kritiska punkter där partialderivatorna är noll. Ett globalt maximum är en kritisk punkt, men det kan finnas flera sådana, så för varje kritisk punkt måste vi verifiera om den är ett globalt maximum eller inte.

Partialderivatorna hos log-likelihoodfunktionen är

$$
\begin{aligned}
\frac{\partial}{\partial \mu} \log L\left(\mu, \sigma^{2} ; x_{1}, x_{2}, \ldots, x_{n}\right) &=\frac{1}{\sigma^{2}} \sum_{i=1}^{n}\left(x_{i}-\mu\right), \\
\frac{\partial}{\partial \sigma^{2}} \log L\left(\mu, \sigma^{2} ; x_{1}, x_{2}, \ldots, x_{n}\right) &=-\frac{n}{2 \sigma^{2}}+\frac{1}{2 \sigma^{4}} \sum_{i=1}^{n}\left(x_{i}-\mu\right)^{2} .
\end{aligned}
$$

Derivatan med avseende på $\mu$ är noll när $\mu=\frac{1}{n} \sum_{i=1}^{n} x_{i}=\bar{\chi}$ medan $\sigma^{2}$ är noll då $\sigma^{2}=\frac{1}{n} \sum_{i=1}^{n}\left(x_{i}-\mu\right)^{2}$. Punkten

$$
\left(\mu, \sigma^{2}\right)=\left(\bar{x}, \frac{1}{n} \sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)^{2}\right)
$$

är alltså det enda simultana nollstället för båda partialderivatorna.

För att bekräfta att denna punkt är ett globalt maximum har vi ett par alternativ. Vi kan beräkna andraderivatorna för log-likelihoodfunktionen och visa att matrisen som bildas bara har negativa egenvärden, men detta kräver mycket arbete (även om det är fullt möjligt att utföra). Vi kan också visa att likelihoodfunktionen går mot noll då $\mu$ och $\sigma^{2}$ går mot oändligheten, men detta är komplicerat eftersom variablerna interagerar på ett icke-trivialt sätt.

Istället visar vi först att $\mu=\bar{x}$ maximerar log-likelihoodfunktionen med avseende på $\mu$ och fixerar sedan $\mu=\bar{x}$ och visar att detta maximeras av $\sigma^{2}=Q / n$ där vi låtit $Q=\sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)^{2}$. Först noterar vi att $\sum_{i=1}^{n}\left(x_{i}-\mu\right)^{2}$ alltid minimeras $i \mu=\bar{x}$ eftersom

$$
\begin{aligned}
\sum_{i=1}^{n}\left(x_{i}-\mu\right)^{2} &=\sum_{i=1}^{n}\left(\left(x_{i}-\bar{x}\right)+(\bar{x}-\mu)\right)^{2} \\
&=\sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)^{2}+\sum_{i=1}^{n} 2\left(x_{i}-\bar{x}\right)(\bar{x}-\mu)+n(\bar{x}-\mu)^{2} \\
&=\sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)^{2}+0+n(\bar{x}-\mu)^{2} \geq \sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)^{2}
\end{aligned}
$$

där vi får likhet då $\mu=\bar{x}$. På grund av detta har vi

$$
-\frac{n}{2} \log \left(\sigma^{2}\right)-\frac{1}{2 \sigma^{2}} \sum_{i=1}^{n}\left(x_{i}-\mu\right)^{2} \leq-\frac{n}{2} \log \left(\sigma^{2}\right)-\frac{1}{2 \sigma^{2}} \sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)^{2},
$$

$d v s$.

$$
\log L\left(\mu, \sigma^{2} ; x_{1}, x_{2}, \ldots, x_{n}\right) \leq \log L\left(\bar{x}, \sigma^{2} ; x_{1}, x_{2}, \ldots, x_{n}\right)
$$

för alla $\mu \in \mathbb{R}$ och $\sigma^{2} \in \mathbb{R}_{>0}$. Med andra ord så för varje $\sigma^{2} \in \mathbb{R}_{>0}$ har vi att $\mu=\bar{x}$ maximerar funktionen $\mu \mapsto \log L\left(\mu, \sigma^{2} ; x_{1}, x_{2}, \ldots, x_{n}\right)$. Det räcker då att visa att $\sigma^{2}=$ $Q / n$ maximerar funktionen $\sigma^{2} \mapsto \log L\left(\bar{x}, \sigma^{2} ; x_{1}, x_{2}, \ldots, x_{n}\right)$.

Vi vet redan att

$$
\frac{d}{d \sigma^{2}} \log L\left(\bar{x}, \sigma^{2} ; x_{1}, x_{2}, \ldots, x_{n}\right)=-\frac{n}{2 \sigma^{2}}+\frac{1}{2 \sigma^{4}} \sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)^{2},
$$

och att denna är noll för $\sigma^{2}=Q / n$ så vi behöver bara bekräfta att andraderivatan är negativ i den punkten. Andraderivatan med avseende på $\sigma^{2}$ är

$$
\begin{aligned}
\frac{d^{2}}{\left(d \sigma^{2}\right)^{2}} \log L\left(\bar{x}, \sigma^{2} ; x_{1}, x_{2}, \ldots, x_{n}\right) &=\frac{n}{\sigma^{4}}-\frac{2}{2 \sigma^{6}} \sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)^{2}=\frac{n}{2 \sigma^{4}}-\frac{1}{\sigma^{6}} Q \\
&=\frac{n}{2 \sigma^{4}}-\frac{1}{\sigma^{6}} n \sigma^{2}=-\frac{n}{2 \sigma^{4}}<0 .
\end{aligned}
$$

Med andra ord är $\sigma^{2}$ ett globalt maximum för $\log L\left(\bar{x}, \sigma^{2} ; x_{1}, x_{2}, \ldots, x_{n}\right)$ och det följer då att $M L-s k a t t n i n g e n ~ a v ~\left(\mu, \sigma^{2}\right)$ är

$$
\left(\mu_{\mathrm{obs}}^{\star}\left(\sigma^{2}\right)_{\mathrm{obs}}^{\star}\right)=\left(\bar{x}, \frac{1}{n} \sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)^{2}\right) .
$$

Notera att ML-skattningen av $\mu$ är väntevärdesriktig men så är inte fallet för $\sigma^{2}$. För att denna ska vara väntevärdesriktig måste vi korrigera den och får då stickprovsvariansen

$$
s^{2}=\frac{1}{n-1} \sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)^{2} .
$$

Hittills har vi antagit att alla stokastisk variabler i stickprovet har samma fördelning, men det behöver inte vara fallet. Det viktiga är att deras fördelningar beror på samma parametrar - parametrarna vi vill skatta.

Exempel 6. Antag att vi har två stickprov, det ena fördelat $\operatorname{som} \mathrm{N}\left(\mu_{1}, \sigma\right)$ och det andra fördelat som $\mathrm{N}\left(\mu_{2}, \sigma\right)$. Med andra ord har vi olika väntevärden, men samma varians. Detta uppstår, till exempel, om vi använder samma mätinstrument (med samma felfördelning, dvs. samma varians) och mäter olika storheter.

Mer konkret har vi $X_{1}, X_{2}, \ldots, X_{n_{1}} \sim \mathrm{N}\left(\mu_{1}, \sigma\right)$ och $Y_{1}, Y_{2}, \ldots, Y_{n_{2}} \sim \mathrm{N}\left(\mu_{2}, \sigma\right)$. Alla stokastiska variabler är oberoende. Likelihodfunktionen är nu

$$
\begin{aligned}
&L\left(\mu_{1}, \mu_{2}, \sigma^{2} ; x_{1}, x_{2}, \ldots, x_{n_{1}}, y_{1}, y_{2}, \ldots, y_{n_{2}}\right) \\
&\quad=\prod_{i=1}^{n_{1}} \frac{1}{\sqrt{2 \pi \sigma^{2}}} e^{-\left(x_{i}-\mu_{1}\right)^{2} / 2 \sigma^{2}} \prod_{j=1}^{n_{2}} \frac{1}{\sqrt{2 \pi \sigma^{2}}} e^{-\left(y_{j}-\mu_{2}\right)^{2} / 2 \sigma^{2}} \\
&\quad=\frac{1}{\left(2 \pi \sigma^{2}\right)^{\frac{n_{1}+n_{2}}{2}}} e^{-\frac{1}{2 \sigma^{2}}\left(\sum_{i=1}^{n_{1}}\left(x_{i}-\mu_{1}\right)^{2}+\sum_{j=1}^{n_{2}}\left(y_{i}-\mu_{2}\right)^{2}\right)} .
\end{aligned}
$$

Log-likelihoodfunktionen är då

$$
\begin{aligned}
&\log L\left(\mu_{1}, \mu_{2}, \sigma^{2} ; x_{1}, x_{2}, \ldots, x_{n_{1}}, y_{1}, y_{2}, \ldots, y_{n_{2}}\right) \\
&\quad=-\frac{n_{1}+n_{2}}{2} \log \sigma^{2}-\frac{1}{2 \sigma^{2}}\left(\sum_{i=1}^{n_{1}}\left(x_{i}-\mu_{1}\right)^{2}+\sum_{j=1}^{n_{2}}\left(y_{i}-\mu_{2}\right)^{2}\right)+C
\end{aligned}
$$

där $C$ är en konstant som inte beror på $\mu_{1}, \mu_{2}$ eller $\sigma^{2}$.

Som innan kan vi beräkna partialderivatorna med avseende på $\mu_{1}, \mu_{2}$ och $\sigma^{2}$. Dessa är alla noll i den kritiska punkten

$$
\left(\mu_{1}, \mu_{2}, \sigma^{2}\right)=\left(\bar{x}, \bar{y}, \frac{Q_{1}+Q_{2}}{n_{1}+n_{2}}\right),
$$

där $Q_{1}=\sum_{i=1}^{n_{1}}\left(x_{i}-\bar{x}\right)^{2}$ och $Q_{2}=\sum_{j=1}^{n_{2}}\left(y_{j}-\bar{y}\right)^{2}$. På samma sätt som föregående exempel kan vi också visa att $\mu_{1}=\bar{x}$ och $\mu_{2}=\bar{y}$ maximerar log-likelihoodfunktionen med avseende på $\mu_{1}$ och $\mu_{2}$ :

$$
\begin{aligned}
&\log L\left(\bar{x}, \bar{y}, \sigma^{2} ; x_{1}, x_{2}, \ldots, x_{n_{1}}, y_{1}, y_{2}, \ldots, y_{n_{2}}\right) \\
&\quad \geq \log L\left(\mu_{1}, \mu_{2}, \sigma^{2} ; x_{1}, x_{2}, \ldots, x_{n_{1}}, y_{1}, y_{2}, \ldots, y_{n_{2}}\right)
\end{aligned}
$$

för alla $\mu_{1}, \mu_{2} \in \mathbb{R}$ och $\sigma^{2} \in \mathbb{R}_{>0}$. Om vi deriverar vänsterledet med avseende på $\sigma^{2}$ två gånger ser vi återigen att andraderivatan är negativ, så vår kritiska punkt är ett globalt maximum. Vi har alltså ML-skattningen

$$
\left(\left(\mu_{1}\right)_{\mathrm{obs}^{\prime}}^{\star}\left(\mu_{2}\right)_{\mathrm{obs}}^{\star}\left(\sigma^{2}\right)_{\mathrm{obs}}^{\star}\right)=\left(\bar{x}, \bar{y}, \frac{Q_{1}+Q_{2}}{n_{1}+n_{2}}\right) .
$$

Som i fallet med ett stickprov är variansskattningen inte väntevärdesriktig utan måste korrigeras. Den korrigerade $M L-s k a t t n i n g e n$ för variansen är

$$
\frac{Q_{1}+Q_{2}}{\left(n_{1}-1\right)+\left(n_{2}-1\right)}=\frac{\sum_{i=1}^{n_{1}}\left(x_{i}-\bar{x}\right)^{2}+\sum_{j=1}^{n_{2}}\left(y_{i}-\bar{y}\right)^{2}}{\left(n_{1}-1\right)+\left(n_{2}-1\right)}
$$

och brukar betecknas $s^{2}$.

ML-skattningar har ett antal viktiga egenskaper. Det första är att om vi har två parametrar $\theta$ och $\eta$ så att $\eta$ kan skrivas som en strikt monoton funktion $g(\theta)$ av $\theta$ så gäller att $\eta_{\mathrm{obs}}^{\star}=g\left(\theta_{\mathrm{obs}}^{\star}\right)$. Med andra ord så kan vi beräkna ML-skattningen av $\eta$ från ML-skattningen av $\theta$ - den är invariant med avseende på parametriseringen. Som konsekvens av detta kan vi se att ML-skattningen för $\sigma$ i normalfördelningen ovan är helt enkelt

$$
\sigma_{\mathrm{obs}}^{\star}=\sqrt{\left(\sigma^{2}\right)_{\mathrm{obs}}^{\star}}=\sqrt{\frac{1}{n} \sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)^{2}} .
$$

En annan egenskap är konsistens. Man kan visa att under vissa (relativt milda) krav på fördelningen, så är ML-skattningen konsistent, dvs. den konvergerar mot det sanna värdet då $n \rightarrow+\infty$. Till slut så kan man visa (återigen under relativt milda krav) att ML-skattningen är effektivast (dvs. den har minst varians) bland alla punktskattningar då $n \rightarrow+\infty$.

Med alla dessa trevliga egenskaper kan man fråga sig om det ens är värt att betraka andra skattningar. Den stora nackdelen med ML-skattningar är tyvärr att de kan vara svåra att beräkna för alla fördelningar. I fördelningarna som vi har betraktat ovan har vi haft tur att ML-skattningen kan skrivas på sluten form. Detta är inte så vanligt för mer komplicerade fördelningar (som, till exempel, blandningsmodeller). Om en sluten form saknas måste ML-skattningen beräknas numeriskt genom optimeringsalgoritmer. En vanlig komplikation är då att algoritmerna kan ta lång tid att konvergera, eller det inte ens kan garanteras att de konvergerar. Under dessa förhållanden kan andra skattningar spela en viktig roll, även om de inte har lika fördelaktiga egenskaper som ML-skattningen.

\section{Minsta-kvadrat-skattning}

En viktig förutsättning för ML-skattningen är att vi har tillgång till fördelningen hos de stokastiska variabler vars utfall utgör vår mätdata. Så är inte alltid fallet. Vi kanske vet att vår mätdata är behäftade med vissa fel, men inte hur dessa fel är fördelade. Antag att vi har $X_{1}, X_{2}, \ldots, X_{n}$ oberoende stokastiska variabler vars fördelningar beror på en parameter $\theta$. Om vi betecknar väntevärdet av $X_{i}$ där fördelningen har parametern $\theta$ med $\mathrm{E}\left[X_{i} ; \theta\right]$ så har vi funktionerna

$$
\mu_{i}(\theta)=\mathrm{E}\left[X_{i} ; \theta\right]
$$

som beskriver väntevärdet som funktion av parametern. Ekvivalent kan vi skriva $X_{i}$ som

$$
X_{i}=\mu_{i}(\theta)+E_{i}
$$

där $E_{1}, E_{2}, \ldots, E_{n}$ är oberoende stokastiska variabler med $\mathrm{E}\left[E_{i}\right]=0$ för alla $i=$ $1,2, \ldots, n$.

Om vi vidare antar att felen har samma varians, dvs. att $V\left[E_{i}\right]=\sigma^{2}$ för alla $i=$ $1,2, \ldots, n$ är det naturligt att minimera följande kvadratsumma:

$$
Q(\theta)=\sum_{i=1}^{n} e_{i}^{2}=\sum_{i=1}^{n}\left(x_{i}-\mu_{i}(\theta)\right)^{2},
$$

där $e_{1}, e_{2}, \ldots, e_{n}$ är utfall av $E_{1}, E_{2}, \ldots, E_{n}$. Det $\theta_{\text {obs }}^{\star}$ som minimerar $Q(\theta)$ kallas minsta-kvadrat-skattningen (MK-skattningen) av $\theta$. Notera att denna endast är användbar då $\mu_{i}(\theta)$ inte är konstant, dvs. att $\theta$ har en effekt på väntevärdet. Den kan, till exempel, inte användas för att skatta variansen hos felet $E_{i}$.

Exempel 7. Antag att vi släpper $n$ objekt från en höjd och mäter hur långt de faller $x_{i}$ inom en viss tid $t_{i}$. Vi antar vidare att objekten befinner sig i fritt fall och därför har konstant acceleration $\theta$, vilket ger relationen

$$
x_{i}=\theta t_{i}^{2} / 2+e_{i},
$$

för $n=1,2, \ldots, n$ där $e_{i}$ är mätfelet för det i:te objektet. För att skatta $\theta$ definierar vi de oberoende stokastiska variablerna

$$
X_{i}=\theta t_{i}^{2} / 2+E_{i}
$$

för $n=1,2, \ldots, n$. Felet $E_{i}$ har väntevärde $\mathrm{E}\left[E_{i}\right]=0$, så vi kan tillämpa MK-metoden med $\mu_{i}(\theta)=\theta t_{i}^{2} / 2$. Kvadratsumman är då

$$
Q(\theta)=\sum_{i=1}^{n}\left(x_{i}-\mu_{i}(\theta)\right)^{2}=\sum_{i=1}^{n}\left(x_{i}-\theta t_{i}^{2} / 2\right)^{2} .
$$

Om vi deriverar och sätter derivatan till noll fås

$$
-\sum_{i=1}^{n} t_{i}^{2} x_{i}+\theta \sum_{i=1}^{n} t_{i}^{4} / 2=0 \quad \Longrightarrow \quad \theta=\frac{2 \sum_{i=1}^{n} t_{i}^{2} x_{i}}{\sum_{i=1}^{n} t_{i}^{4}} .
$$

Andraderivatan är alltid positiv, så detta är ett globalt minimum och ger alltså MKskattningen $\theta_{\text {obs' }}^{\star}$

Notera att om $E_{i}$ är normalfördelade så överensstämmer MK-skattningen med MLskattningen eftersom likelihoodfunktionen då är

$$
L\left(\theta ; x_{1}, x_{2}, \ldots, x_{n}\right)=\frac{1}{\left(2 \pi \sigma^{2}\right)^{n / 2}} e^{-\frac{1}{2 \sigma^{2}} \sum_{i=1}^{n}\left(x_{i}-\mu_{i}(\theta)\right)^{2}}=\frac{1}{\left(2 \pi \sigma^{2}\right)^{n / 2}} e^{-\frac{1}{2 \sigma^{2}} Q(\theta)}
$$

och maximering av $L\left(\theta ; x_{1}, x_{2}, \ldots, x_{n}\right)$ är således detsamma som minimering av $Q(\theta)$. I andra fall kan ML- och MK-skattningarna skilja sig avsevärt.

Exempel 8. Vi antar återigen att vi har $X_{1}, X_{2}, \ldots, X_{n}$ oberoende likafördelade stokastiska variabler med fördelning $\mathrm{U}[0, \theta]$. Detta ger $\mu_{i}(\theta)=\mathrm{E}_{\theta}\left[X_{i}\right]=\theta / 2$ så vi får

$$
Q(\theta)=\sum_{i=1}^{n}\left(x_{i}-\theta / 2\right)^{2},
$$

vilket ger MK-skattningen $\theta_{\mathrm{obs}}^{\star}=2 \bar{x}$. Denna skattning kan verka rimlig - den är väntevärdesriktig och det aritmetiska medelvärdet $\bar{x}$ borde ligga runt $\theta / 2$ - men vi ska se att den korrigerade ML-skattningen är att föredra.

Den korrigerade $M L-s k a t t n i n g e n$ är

$$
\hat{\theta}_{\mathrm{obs}}=\frac{n+1}{n} \max \left(x_{1}, x_{2}, \ldots, x_{n}\right)
$$

och var varians $\mathrm{V}[\hat{\theta}]=\frac{\theta_{0}^{2}}{n(n+2)}$ där $\theta_{0}$ är den parameter som användas för att generera mätvärdena. För MK-skattningen har vi däremot

$$
\mathrm{V}\left[\theta^{\star}\right]=\mathrm{V}[2 \bar{X}]=4 \mathrm{~V}[\bar{X}]=\frac{4}{n} \mathrm{~V}[X]=\frac{4}{n} \cdot \frac{\theta_{0}^{2}}{12}=\frac{\theta_{0}^{2}}{3 n} .
$$

Alltså är ML-skattningen $(n+2) / 3$ gånger effektivare $(d v s$. den har $(n+2) / 3$ gånger lägre varians) jämfört med MK-skattningen. Anledningen är att ML-skattningen bara beror på ett värde - det största mätvärdet bland $x_{1}, x_{2}, \ldots, x_{n}$ - medan MKskattningen beror på alla mätvärdena. MK-skattningen kommer alltså att "störas" av dessa mindre mätvärden som inte tillför någon viktig information om $\theta$. 

\section{Medelfel}

Som vi såg i början av föregående föreläsning är en viktig del av den statistiska modelleringen att skatta felet i vår punktskattning. Vi kommer att diskutera detta mer i detalj under nästa föreläsning då vi behandlar intervallskattning, men kan redan introducera ett närliggande begrepp inom punktskattningsramverket.

I regel har vi en standardavvikelse $D\left[\theta^{\star}\right]$ för en punktskattning $\theta_{\mathrm{obs}}^{\star}$. Problemet är oftast att uttrycket för $D\left[\theta^{\star}\right]$ beror på den sökta parametern $\theta_{0}$ själv och kan därför inte bestämmas exakt. Vi måste därför skatta $D\left[\theta^{\star}\right]$. En sådan skattning kallas medelfelet och betecknas ofta $d\left(\theta^{\star}\right)$.

Ett rimligt medelfel fås ofta om vi istället för det sanna värdet $\theta_{0}$ använder skattningen $\theta_{\text {obs }}^{\star}$ som värde på $\theta$ när vi beräknar $D\left[\theta^{\star}\right]$. Motiveringen här är att om $\theta_{\text {obs }}^{\star}$ är en tillräckligt bra skattning av $\theta_{0}$ (vi kanske har en konsistent punktskattning och arbetar med stor stickprovsstorlek $n)$ så kommer $d\left(\theta^{\star}\right)=\left.D\left[\theta^{\star}\right]\right|_{\theta=\theta_{\text {obs }}^{\star}}$ vara en bra skattning av $\left.\mathrm{D}\left[\theta^{\star}\right]\right|_{\theta=\theta_{0}}$.

Om vi återvänder till opinionsundersökningen så skattade vi $p$ med punktskattningen $p_{\text {obs }}^{\star}=x / n$. Denna har standardavvikelsen

$$
\mathrm{D}\left[p^{\star}\right]=\sqrt{\frac{p(1-p)}{n}},
$$

så ett rimligt medelfel ges av

$$
d\left(p^{\star}\right)=\sqrt{\frac{p_{\text {obs }}^{\star}\left(1-p_{\text {obs }}^{\star}\right)}{n}} .
$$

På samma sätt har vi kanske skattat $\mu$ och $\sigma$ för normalfördelade variabler med $\mu_{\text {obs }}^{\star}=\bar{x}$ och $\sigma_{\text {obs }}^{\star}=s$. Standardavvikelsen för $\bar{X}$ är

$$
\mathrm{D}\left[\mu^{\star}\right]=\mathrm{D}[\bar{X}]=\frac{\sigma}{\sqrt{n}},
$$

så vi får medelfelet

$$
d\left(\mu^{\star}\right)=\frac{s}{\sqrt{n}} .
$$

Ett annat tillvägagångssätt är att "simulera" olika utfall av punktskattningen. Detta görs genom att dra $n$ mätvärden ut stickprov $x_{1}, x_{2}, \ldots, x_{n}$ med återläggning. Vi har då alltså återigen ett stickprov med $n$ värden, men vissa av de ursprungliga mätvärdena saknas och andra förekommer mer en än gång. Utifrån detta stickprov beräknar vi punktskattningen $\theta_{1, \text { obs }}^{\star}$. Vi repeterar detta $B$ gånger och får då $B$ stycken punktskattningar $\theta_{1, o b s^{\prime}}^{\star} \theta_{2, \text { obs' }}^{\star}, \ldots, \theta_{B, \text { obs }}^{\star}$. Låt $\overline{\theta_{\text {obs }}^{\star}}$ beteckna det aritmetiska medelvärdet av dessa $B$ skattningar. Medelfelet kan då definieras som

$$
d\left(\theta^{\star}\right)=\sqrt{\frac{1}{B-1} \sum_{b=1}^{B}\left(\theta_{b, o b s}^{\star}-\overline{\theta_{\mathrm{obs}}^{\star}}\right)^{2}} .
$$

Utöver denna standardavvikelse kan vi betrakta histogrammet för punktskattningarna och på så sätt få en bättre uppfattning om hur mycket variation vi kan förvänta oss i skattningen. Denna metod kallas icke-parametrisk bootstrap och är speciellt användbar i situationer då vi inte har tillgång till $D\left[\theta^{\star}\right]$, vilket kan ske, till exempel, om $\theta_{\text {obs }}^{\star}$ fås som resultatet av en numerisk optimeringsalgoritm.

Exempel 9. Anta att vi har $n=300$ värden från en $\operatorname{Exp}(\lambda)$-fördelad variabel $X$. Vi har sett att ML-skattningen för $\lambda$ är $1 / \bar{\chi}$ så genom invariansegenskapen är $M L-$ skattningen för väntevärdet $\mu=\mathrm{E}[X]=1 / \lambda$ lika med $\bar{\chi}$. Standardavvikelsen för denna skattning $\mu^{\star}=\bar{X}$ fås som $\mathrm{D}[\bar{X}]=\mathrm{D}[X] / \sqrt{n}=\mu / \sqrt{n}$. Stoppar vi in skattningen $\mu_{\mathrm{obs}}^{\star}$ får vi medelfelet $d\left(\mu^{\star}\right)=\mu_{\mathrm{obs}}^{\star} / \sqrt{n}$, vilket kan jämföras med den sanna standardavvikelsen $\mu_{0} / \sqrt{n}$ där $\mu_{0}$ är parametern som använts för att generera värdena.

För $\mu_{0}=17.89$ får vi $\mu_{\mathrm{obs}}^{\star} \approx 17.77$ vilket $\operatorname{ger} d\left(\mu^{\star}\right) \approx 1.03$. Eftersom vi känner till det sanna värdet $\mu_{0}$ på parametern kan vi beräkna $\mathrm{D}\left[\mu^{\star}\right]$ och får detta också till 1.03. Skattningen av standardavvikelsen i form av medelfelet ovan är alltså ganska bra.

Med icke-parametrisk bootstrap utför vi $B=10000$ slumpmässiga urval ur stickprovet. Detta ger $B$ olika skattningar av $\mu$ vars standardavvikelse fås till 1.07. Denna skattning är alltså aningen sämre än den vi fick genom att sätta $\mu=\mu_{\mathrm{obs}}^{\star}$ i uttrycket för $\mathrm{D}\left[\mu^{\star}\right]$. Fördelen är att vi inte behövde känna till $\mathrm{D}\left[\mu^{\star}\right]$ eller egentligen något om fördelningen på $\mu^{\star}$ - skattningen av felet fick vi "gratis" genom att repetera skattningen på olika urval av stickprovet.

Som nämnt ovan kan vi också plotta det normaliserade histogrammet för dessa bootstrappade skattningar. Vi jämför med täthetsfunktionen för $\mu^{\star}$ (som vi kan visa har fördelningen Gamma( $\left(n, \mu_{0} / n\right)$ ) och ser att de överensstämmer ganska bra.

![](https://cdn.mathpix.com/cropped/2022_11_17_b74524338d87b0a48427g-14.jpg?height=634&width=871&top_left_y=1496&top_left_x=627)