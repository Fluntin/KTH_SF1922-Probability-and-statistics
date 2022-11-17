\title{
Föreläsning fjorton
}

\author{
Joakim Andén
}

12 december 2022

\section{Kredibilitetsintervall}

Förutom punktskattningar finns det andra sätt att sammanfatta aposteriorifördelningen. Till exempel kan man använda kredibilitetsintervall (eller aposterioriintervall) för utfallen $x_{1}, x_{2}, \ldots, x_{k}$ som är det intervall $I_{\theta}$ så att

$$
P\left(\theta \in I_{\theta} \mid x_{1}, x_{2}, \ldots, x_{k}\right)=1-\alpha,
$$

dvs. sannolikheten att $\theta$ ligger $\mathrm{i}$ intervallet givet datapunkterna $x_{1}, x_{2}, \ldots, x_{k}$ är $1-\alpha$, vilket kallas kredibilitetsgraden. Ofta beräknas intervallet med hjälp av kvantilerna hos aposteriorifördelningen $\pi\left(\theta \mid x_{1}, x_{2}, \ldots, x_{k}\right)$.

![](https://cdn.mathpix.com/cropped/2022_11_17_44901e6e03a4337a35d5g-1.jpg?height=472&width=724&top_left_y=1431&top_left_x=690)

Exempel 1. Låt $\theta \sim N(0,2)$ och $X \mid \theta \sim N(\theta, 4)$. Om vi har $k=5$ utfall så att $\bar{x}=2$, vad är då ett $95 \%$ kredibilitetsintervall?

Först har vi uppdateringen av parametrarna $(0,2)$, vilket ger

$$
(0,2) \mapsto\left(\left(\frac{0}{2^{2}}+\frac{5 \cdot 2}{4^{2}}\right) /\left(\frac{1}{4}+\frac{5}{16}\right), \frac{1}{\sqrt{\frac{1}{4}+\frac{5}{16}}}\right)=\left(\frac{10}{16} / \frac{9}{16}, \sqrt{\frac{16}{9}}\right)=\left(\frac{10}{9}, \frac{4}{3}\right) \text {. }
$$

Med $\alpha=0.05$ får vi då, eftersom $\lambda_{\alpha / 2}=\lambda_{0.025} \approx 1.96$, kredibilitetsintervallet

$$
I_{\theta}=\frac{10}{9} \pm \lambda_{0.025} \frac{4}{3} \approx 1.11 \pm 1.96 \cdot 1.33 \approx 1.11 \pm 2.61 \approx[-1.50,3.72] .
$$

Det går att beräkna kredibilitetsintervall för andra aposteriorifördelningar, men detta kräver oftast numeriska beräkningar eftersom kvantilerna inte kan sammanfattas i tabell lika enkelt som för normalfördelningen.

\section{Förlust och risk}

Vi har studerat olika sätt att konstruera punktskattningar av en parameter: enkla stickprovsmedelvärden och stickprovsvarianser, ML-skattningar, MK-skattningar, betingade medelvärden och maximum aposteriori-skattningar. I vissa fall har vi kunnat härleda vissa egenskaper: väntevärdesriktighet, konsistens och effektivitet. Problemet är att dessa egenskaper inte nödvändigtvis säger något om vad vår skattning har för effekt när vi tillämpar den i olika sammanhang. Vi kanske vill använda skattningen för att dimensionera en konstruktion eller verkställa en köp- eller säljorder. Konsekvenserna av en felskattning kan vara stora i dessa fall och vi vill därför försöka minimera riskerna associerade med skattningen.

För att formalisera detta definierar vi en förlustfunktion $L(\theta, a)$ som motsvarar den förväntade förlusten givet att det sanna parametervärdet är $\theta$, men vi skattar den som $a$. Om vi skattar korrekt, dvs. har $a=\theta$, får vi $L(\theta, a)=L(\theta, \theta)=0$. Utöver detta kräver vi att $L(\theta, a) \geq 0$.

Alasoleftel

![](https://cdn.mathpix.com/cropped/2022_11_17_44901e6e03a4337a35d5g-2.jpg?height=276&width=447&top_left_y=1323&top_left_x=359)

Kvadratfel

![](https://cdn.mathpix.com/cropped/2022_11_17_44901e6e03a4337a35d5g-2.jpg?height=252&width=443&top_left_y=1346&top_left_x=841)

o 1-fel

![](https://cdn.mathpix.com/cropped/2022_11_17_44901e6e03a4337a35d5g-2.jpg?height=228&width=452&top_left_y=1371&top_left_x=1281)

Några exempel på vanliga förlustfunktioner är

Absolutfelet $L(\theta, a)=|\theta-a|-$ felet är i proportion till skillnaden mellan $a$ och $\theta$

■ Kvadratfelet $L(\theta, a)=|\theta-a|^{2}$ - felet är kvadratiskt i skillnaden, dvs. större fel viktas större, relativt sett, än mindre fel.

-0-1-felet

$$
L(\theta, a)= \begin{cases}0, & a=\theta \\ 1, & a \neq \theta .\end{cases}
$$

(gäller bara om parametern $\theta$ är diskret) - alla fel är lika viktiga.

Man kan också definiera en förlustfunktion genom att modifiera någon av de ovanstående standardförlusterna:

$$
L(\theta, a)= \begin{cases}2|a-\theta|, & a>\theta \\ |a-\theta|, & a \leq \theta\end{cases}
$$

I detta fall viktar vi felen i proportion till skillnaden, men överskattningar viktas dubbelt så mycket som underskattningar. Oftast använder vi kvadratfelet $L(\theta, a)=$ $|\theta-a|^{2}$ eftersom detta förenklar många beräkningar.

Antag att vi har en förlustfunktion $L(\theta, a)$ och en punktskattning $\theta_{\text {obs }}^{\star}=g(x)$ givet utfallet $x$ av stickprovsvariabeln $X$ vars fördelning beror på $\theta$. Vi definierar då punktskattningens riskfunktion

$$
R\left(\theta, \theta^{\star}\right)=\int_{x(\Omega)} L(\theta, g(x)) f(x \mid \theta) d x,
$$

där vi har antagit att $X$ är kontinuerlig med täthetsfunktion $f(x \mid \theta)$. Notera att $\theta$ inte nödvändigtvis behöver vara en stokastisk variabel här, utan kan också bara vara en konstant, i vilket fall vi har $f(x \mid \theta)=f(x ; \theta)$ enligt den tidigare beteckningen. Om $x$ är diskret har vi, likt innan,

$$
R\left(\theta, \theta^{\star}\right)=\sum_{x \in X(\Omega)} L(\theta, g(x)) p(x \mid \theta),
$$

där $p(x \mid \theta)$ är $X$ :s sannolikhetsfunktion. Vi kan sammanfatta båda fallen som

$$
R\left(\theta, \theta^{\star}\right)=\mathrm{E}[L(\theta, g(X)) \mid \theta] .
$$

Båda dessa definitioner kan generaliseras till fallet med flera utfall $x_{1}, x_{2}, \ldots, x_{n}$ av oberoende stickprovsvariabler $x_{1}, x_{2}, \ldots, x_{n}$, vilket ger

$$
R\left(\theta, \theta^{\star}\right)=\mathrm{E}\left[L\left(\theta, g\left(X_{1}, X_{2}, \ldots, X_{n}\right)\right) \mid \theta\right] .
$$

För enkelhets skull kommer vi att presentera fallet med ett utfall $x$, men alla resultat kan generaliseras till flera utfall.

Med kvadratfelet $L(\theta, a)=|\theta-a|^{2}$ har vi att riskfunktionen $R\left(\theta, \theta^{\star}\right)$ är lika med medelkvadratfelet MSE för $\theta^{\star}$. Vi kan då utnyttja uppdelningen i varians och systematiskt fel:

$$
R\left(\theta, \theta^{\star}\right)=\mathrm{V}\left[\theta^{\star}\right]+\left|\mathrm{E}\left[\theta^{\star}\right]-\theta\right|^{2} .
$$

Exempel 2. Antag att $X \sim \operatorname{Bin}(n, \theta)$. Vi har då ML-skattningen av $\theta$

$$
\theta^{\star}=\frac{x}{n} .
$$

Om vi antar att $\theta \sim \operatorname{Beta}(\alpha, \beta)$ kan vi se fördelningen av $X$ som betingad på $\theta$, bilda aposteriorifördelningen $\pi(\theta \mid x)$ och beräkna dess väntevärde

$$
\hat{\theta}=\mathrm{E}[\theta \mid X]=\frac{\alpha+X}{\alpha+\beta+n} .
$$

Hur ser riskfunktionerna ut för dessa punktskattningar under kvadratfelets förlustfunktion $L(\theta, a)=|\theta-a|^{2}$ ? $V i$ använder uppdelningen $i$ varians och systematiskt fel. Eftersom $\mathrm{E}[X]=n \theta$ och $\mathrm{V}[X]=n \theta(1-\theta)$ har $v i$

$$
\mathrm{E}\left[\theta^{\star} \mid \theta\right]=\theta \quad \text { och } \quad \mathrm{V}\left[\theta^{\star} \mid \theta\right]=\frac{\theta(1-\theta)}{n},
$$

vilket ger

$$
R\left(\theta, \theta^{\star}\right)=\frac{\theta(1-\theta)}{n} .
$$

Risken är allstå stor då $\theta=1 / 2$ och avtar när $\theta$ närmar sig noll eller ett.

För $\hat{\theta}$ har vi

och

$$
\mathrm{E}[\hat{\theta} \mid \theta]=\frac{\alpha+n \theta}{\alpha+\beta+n}
$$

$$
\mathrm{V}[\hat{\theta} \mid \theta]=\frac{n \theta(1-\theta)}{(\alpha+\beta+n)^{2}} \text {. }
$$

Detta ger riskfunktionen

$$
R(\theta, \hat{\theta})=\frac{n \theta(1-\theta)}{(\alpha+\beta+n)^{2}}+\left(\frac{\alpha+n \theta}{\alpha+\beta+n}-\theta\right)^{2}=\frac{n \theta(1-\theta)+(\alpha(1-\theta)-\beta \theta)^{2}}{(\alpha+\beta+n)^{2}} .
$$

Riskfunktionens utseende beror alltså på valet av aprioriparametrar $\alpha, \beta$, vilket ger oss en del flexibilitet. Till exempel kan det vara önskvärt att riskfunktionen är densamma oavsett $\theta$ eftersom vi inte vet vad för värde som $\theta$ kommer att anta. Man kan visa att riskfunktionen är konstant om $\alpha=\beta=\sqrt{n / 4}$. Detta ger

$$
\hat{\theta}=\frac{x+\sqrt{n / 4}}{n+\sqrt{n}}
$$

och

$$
R(\theta, \hat{\theta})=\frac{n}{4(n+\sqrt{n})^{2}}=\frac{1}{4(\sqrt{n}+1)^{2}} .
$$

![](https://cdn.mathpix.com/cropped/2022_11_17_44901e6e03a4337a35d5g-4.jpg?height=659&width=751&top_left_y=1852&top_left_x=665)

Det betingade väntevärdet med apriorifördelningen $\operatorname{Beta}(\sqrt{n / 4}, \sqrt{n / 4})$ ger då mindre risk för de flesta $\theta$ när $n$ är stort, undantaget områdena precis vid noll och ett.

\section{Bayesskattning}

Riskfunktionen ger en bra uppfattning om hur stor vår förlust blir för en viss punktskattning givet ett visst värde på parametern $\theta$. Problemet är att vi inte känner till $\theta$ i förväg, vilket gör det svårt att jämföra olika skattningar utifrån deras riskfunktioner. Vi behöver alltså ett sätt att sammanfatta risken.

Ett alternativ är att beräkna $\max _{\theta \in \Omega_{\theta}} R\left(\theta, \theta^{\star}\right)$, den så kallade maxrisken. Detta motsvarar alltså det värsta tänkbara händelseförloppet. Vi kan då söka en skattning som minimerar denna maxrisk, vilket då kallas för en minimaxskattning.

Om vi har en apriorifördelning $\pi(\theta)$ för $\theta$ kan vi använda denna för att beräkna väntevärdet för risken över denna fördelning, dvs.

$$
r\left(\pi, \theta^{\star}\right)=\int_{\Omega_{\theta}} R\left(\theta, \theta^{\star}\right) \pi(\theta) d \theta=\mathrm{E}\left[R\left(\theta, \theta^{\star}\right)\right] .
$$

Detta kallas för Bayesrisken av $\theta^{\star}$ givet apriorifördelningen $\pi(\theta)$. Som innan så ersätter vi integralen med en summa när $\theta$ är en diskret parameter (och $\pi(\theta)$ då är en sannolikhetsfunktion). Den punktskattning som minimerar Bayesrisken kallas för en Bayesskattning (givet apriorifördelningen $\pi(\theta)$ ).

Det kan verka komplicerat att minimera $r\left(\pi, \theta^{\star}\right)$ för att hitta Bayesskattningen, men det visar sig att vi kan vända på integrationsordningen, vilket förenklar minimeringen avsevärt. Vi utvecklar uttrycket för Bayesrisken genom att sätta in definitionen hos riskfunktionen och får då

$$
\begin{aligned}
r\left(\pi, \theta^{\star}\right) &=\int_{\Omega_{\theta}} R\left(\theta, \theta^{\star}\right) \pi(\theta) d \theta \\
&=\int_{\Omega_{\theta}} \int_{X(\Omega)} L(\theta, g(x)) f(x \mid \theta) d x \pi(\theta) d \theta \\
&=\int_{X(\Omega)} \int_{\Omega_{\theta}} L(\theta, g(x)) f(x \mid \theta) \pi(\theta) d \theta d x .
\end{aligned}
$$

Enligt Bayes sats har vi att $f(x \mid \theta) \pi(\theta)=\pi(\theta \mid x) m(x)$, vilket då ger

$$
\begin{aligned}
r\left(\pi, \theta^{\star}\right) &=\int_{X(\Omega)} \int_{\Omega_{\theta}} L(\theta, g(x)) \pi(\theta \mid x) m(x) d \theta d x \\
&=\int_{X(\Omega)} \int_{\Omega_{\theta}} L(\theta, g(x)) \pi(\theta \mid x) d \theta m(x) d x \\
&=\int_{X(\Omega)} r\left(\theta^{\star} \mid x\right) m(x) d x,
\end{aligned}
$$

där vi har infört beteckningen

$$
r\left(\theta^{\star} \mid x\right)=\int_{\Omega_{\theta}} L(\theta, g(x)) \pi(\theta \mid x) d \theta=\mathrm{E}[L(\theta, g(x)) \mid x]
$$

för den så kallade aposterioririsken för $\theta^{\star}=g(X)$ givet utfallet $x$ med apriorifördelningen $\pi(\theta)$.

För att minimera Bayesrisken $r\left(\pi, \theta^{\star}\right)$ räcker det alltså att minimera aposterioririsken $r\left(\theta^{\star} \mid x\right)$ för varje $x$. Detta kan göras separat för varje $x$. Alternativt, om vi bara är intresserade av ett specifikt utfall $x$ räcker det då att hitta det a som minimerar

$$
\mathrm{E}[L(\theta, a) \mid x] .
$$

Detta $a$ är då Bayesskattningen av $\theta$ givet $x$ för apriorifördelningen $\pi(\theta)$.

Låt oss anta att $L(\theta, a)=|\theta-a|^{2}$. Eftersom $L(\theta, a)=(\theta-a)^{2}=\theta^{2}-2 \theta a+a^{2}$ har vi

$$
\mathrm{E}[L(\theta, a) \mid x]=\int_{\Sigma_{\theta}} \theta^{2} \pi(\theta \mid x) d \theta-2 a \int_{\Sigma_{\theta}} \theta \pi(\theta \mid x) d \theta+a^{2} .
$$

Den första termen beror inte på $a$, så vi kan ignorera den. Den andra termen är lika med $2 a \mathrm{E}[\theta \mid x]$, så vi vill alltså minimera

$$
a^{2}-2 a \mathrm{E}[\theta \mid x]
$$

med avseende på $a$, vilket fås när $a=E[\theta \mid x]$. Bayesskattningen för kvadratfelet är alltså lika med det betingade väntevärdet.

Vi antar nu att $L(\theta, a)=|\theta-a|$. Detta kan skrivas om som

$$
L(\theta, a)= \begin{cases}-(\theta-a), & \theta \leq a \\ \theta-a, & \theta>a .\end{cases}
$$

Vi antar att $\theta$ är kontinuerlig och att väntevärdet då kan skrivas som en integral över $\mathbb{R}$, vilket ger

$$
\begin{aligned}
\mathrm{E}[L(\theta, a) \mid x] &=\int_{\mathbb{R}} L(\theta, a) \pi(\theta \mid x) d \theta \\
&=-\int_{-\infty}^{a}(\theta-a) \pi(\theta \mid x) d \theta+\int_{a}^{+\infty}(\theta-a) \pi(\theta \mid x) d \theta \\
&=a \int_{-\infty}^{a} \pi(\theta \mid x) d \theta-a \int_{a}^{+\infty} \pi(\theta \mid x) d \theta-\int_{-\infty}^{a} \theta \pi(\theta \mid x) d \theta+\int_{a}^{+\infty} \theta \pi(\theta \mid x) d \theta .
\end{aligned}
$$

Vi vill nu derivera detta med avseende på $a$ och använder då integralkalkylens fundamentalsats som lyder

$$
\frac{d}{d a} \int_{-\infty}^{a} g(x) d x=g(a) \quad \frac{d}{d a} \int_{a}^{+\infty} g(x) d x=-g(a) .
$$

Detta ger då

$$
\begin{aligned}
\frac{d}{d a} \mathrm{E}[L(\theta, a) \mid x] &=\int_{-\infty}^{a} \pi(\theta \mid x) d \theta+a \pi(a \mid x)-\int_{a}^{+\infty} \pi(\theta \mid x) d \theta+a \pi(a \mid x)-a \pi(a \mid x)-a \pi(a \mid x) \\
&=\int_{-\infty}^{a} \pi(\theta \mid x) d \theta+\left(1-\int_{-\infty}^{a} \pi(\theta \mid x) d \theta\right) \\
&=2 \int_{-\infty}^{a} \pi(\theta \mid x) d \theta-1 .
\end{aligned}
$$

Med andra ord söker vi $a$ så att

$$
\int_{-\infty}^{a} \pi(\theta \mid x) d \theta=\frac{1}{2},
$$

dvs. medianen av aposteriorifördelningen $\pi(\theta \mid x)$. Eftersom derivatan är växande i $a$ så utgör medianen ett globalt minimum för aposterioririsken Bayesskattningen för absolutfelet är alltså medianen hos aposteriorifördelningen

Vi avslutar med 0-1-felet

$$
L(\theta, a)= \begin{cases}0, & a=\theta \\ 1, & a \neq \theta,\end{cases}
$$

och antar då att $\theta$ är diskret. I detta fall har vi aposterioririsken

$$
\mathrm{E}[L(\theta, a) \mid x]=\sum_{\theta \in \Omega_{\theta}} L(\theta, a) \pi(\theta \mid x) .
$$

Eftersom $L(\theta, a)=1$ för alla $a \neq \theta$ får vi då

$$
\mathrm{E}[L(\theta, a) \mid x]=1-\pi(a \mid x) .
$$

Aposterioririsken minimeras alltså för det a som maximerar $\pi(a \mid x)$, dvs. maximum aposteriori-skattningen. Bayesskattningen för 0-1-felet är alltså maximum aposterioriskattningen.