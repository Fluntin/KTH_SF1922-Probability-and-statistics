\title{
Föreläsning tolv
}

\author{
Joakim Andén
}

\section{5 december 2022}

\section{Enkel linjär regression}

Vi har hittills betraktat skattning av parametrar i olika statistiska modeller i form av punktskattning, intervallskattning och hypotestest. I dagens föreläsning ska vi tillämpa dessa begrepp på en specifik (och mycket användbar) modell: linjär regression. En regressionsmodell beskriver ett samband mellan två storheter, ofta betecknade $x$ och $y$. Detta kan vara ett samband mellan tryck och smältpunkt för en viss kemisk förening, antal motionstimmar per vecka och livslängd eller något annat. En enkel linjär regressionsmodell har formen

$$
y=\alpha+\beta x
$$

dvs. vi ansätter ett linjärt samband mellan $x$ och $y$. Denna ekvation, med de sanna värdena på $\alpha$ och $\beta$, kallas för den teoretiska regressionslinjen. Variabeln $x$ kallas regressionsvariabel, förklarande variabel eller oberoende variabel medan y kallas beroende variabel. Notera att vi kan behandla en större klass av (icke-linjära) modeller genom transformation av variablerna. Om vi till exempel har sambandet

$$
u=a t^{b}
$$

(dvs. ett rent potensförhållande) mellan den oberoende variabeln $t$ och den beroende variabeln $u$ kan vi logaritmera och då få

$$
\log u=\log a+b \log t
$$

vilket ger den linjära modellen $y=\alpha+\beta x$ genom att definiera $y=\log u, x=\log t, \alpha=$ $a, \beta=b$.

Om vi har tillgång till exakta värden (dvs. utan fel) på $x$ och y räcker det med två par $\left(x_{1}, y_{1}\right)$ och $\left(x_{2}, y_{2}\right)$ för att lösa ut $\alpha$ och $\beta$. Tyvärr är detta sällan fallet och vi måste skatta parametrarna utifrån datapunkter behäftade med mätfel. Ofta har vi då datapunkterna $\left(x_{1}, y_{1}\right),\left(x_{2}, y_{2}\right), \ldots,\left(x_{n}, y_{n}\right)$ som uppfyller

$$
y_{i}=\alpha+\beta x_{i}+e_{i}
$$

för $i=1,2, \ldots, n$ där $e_{i}$ är mätfelet för det i:te mätvärdet. 

![](https://cdn.mathpix.com/cropped/2022_11_17_b42a0778021117a00dafg-02.jpg?height=677&width=1260&top_left_y=217&top_left_x=408)

Exempel 1. Antag att vi har undersökt $n=20$ nyfödda barn och mätt deras bilirubinhalt $x$ samt koncentrationen hos ett visst protein $y$ i ryggmärgsvätskan genom lumbarpunktion. Eftersom mätning bilirubinhalt är mindre invasiv (kan göras genom ett litet blodprov) än lumbarpunktion vill vi gärna kunna förutsäga proteinkoncentrationen utifrån bilirubinhalten. Antag att vi har erhållit datapunkterna

\begin{tabular}{r|rrrrrrrrrr}
$x$ & $0.14$ & $0.08$ & $0.07$ & $0.26$ & $0.08$ & $0.02$ & $0.03$ & $0.22$ & $0.06$ & $0.23$ \\
$y$ & 83 & 65 & 71 & 140 & 135 & 30 & 30 & 128 & 80 & 168 \\
$x$ & $0.29$ & $0.04$ & $0.13$ & $0.14$ & $0.07$ & $0.05$ & $0.13$ & $0.06$ & $0.05$ & $0.08$ \\
$y$ & 139 & 88 & 121 & 125 & 56 & 98 & 101 & 96 & 73 & 116
\end{tabular}

Vi söker alltså $\alpha$ och $\beta$ så att modellen $y=\alpha+\beta x$ passar så bra som möjligt för datapunkterna ovan.

Ett sätt att angripa skattningen av $\alpha$ och $\beta$ är att betrakta $e_{i}$ som utfall av oberoende stokastiska variabler $E_{i}$ med fördelning $N(0, \sigma)$ för någon (känd) $\sigma$. Vi får då att $y_{i}$ är ett utfall av de oberoende stokastiska variablerna

$$
Y_{i}=\alpha+\beta x_{i}+E_{i}
$$

för $i=1,2, \ldots, n$ och har då $Y_{i} \sim N\left(\mu_{i}, \sigma\right)$ för $\mu_{i}=\alpha+\beta x_{i}$. Vi har alltså $n$ oberoende stokastiska variabler, men de är inte likafördelade.

För att skatta $\alpha$ och $\beta$ kan vi bilda likelihoodfunktionen

$$
\begin{aligned}
L(\alpha, \beta) &=L\left(\alpha, \beta ; y_{1}, y_{2}, \ldots, y_{n}\right) \\
&=\prod_{i=1}^{n} \frac{1}{\sqrt{2 \pi \sigma^{2}}} e^{-\frac{\left(y_{i}-\alpha-\beta x_{i}\right)^{2}}{2 \sigma^{2}}} \\
&=\frac{1}{\left(2 \pi \sigma^{2}\right)^{n / 2}} e^{-\frac{1}{2 \sigma^{2}} \sum_{i=1}^{n}\left(y_{i}-\alpha-\beta x_{i}\right)^{2}}
\end{aligned}
$$

vilket ger log-likelihoodfunktionen

$$
\log L(\alpha, \beta)=-\frac{n}{2} \log \sigma^{2}-\frac{1}{2 \sigma^{2}} \sum_{i=1}^{n}\left(y_{i}-\alpha-\beta x_{i}\right)^{2}+C
$$

där $C$ är en konstant som inte beror på $\alpha, \beta$ eller $\sigma^{2}$.

Om vi deriverar $\log L(\alpha, \beta)$ med avseende på $\alpha$ och $\beta$ får vi

$$
\begin{aligned}
\frac{\partial}{\partial \alpha} \log L(\alpha, \beta) &=\frac{1}{\sigma^{2}} \sum_{i=1}^{n} y_{i}-\alpha-\beta x_{i} \\
\frac{\partial}{\partial \beta} \log L(\alpha, \beta) &=\frac{1}{\sigma^{2}} \sum_{i=1}^{n} x_{i}\left(y_{i}-\alpha-\beta x_{i}\right) .
\end{aligned}
$$

Om vi sätter dessa till noll och multiplicerar med $\sigma^{2}$ får vi ekvationssystemet

$$
\left\{\begin{array}{l}
\sum_{i=1}^{n}\left(y_{i}-\alpha-\beta x_{i}\right)=0 \\
\sum_{i=1}^{n} x_{i}\left(y_{i}-\alpha-\beta x_{i}\right)=0 .
\end{array}\right.
$$

Den första ekvationen ger då

$$
\alpha=\frac{1}{n} \sum_{i=1}^{n} y_{i}-\beta x_{i}=\bar{y}-\beta \bar{x}
$$

och medan den andra ger

$$
\beta \sum_{i=1}^{n} x_{i}^{2}=\sum_{i=1}^{n} x_{i} y_{i}-\alpha x_{i}=-n \alpha \bar{\chi}+\sum_{i=1}^{n} x_{i} y_{i} .
$$

Om vi sätter in uttrycket för $\alpha$ får vi

$$
\beta \sum_{i=1}^{n} x_{i}^{2}=-n(\bar{y}-\beta \bar{x}) \bar{x}+\sum_{i=1}^{n} x_{i} y_{i}=-n \beta \bar{x}^{2}+\sum_{i=1}^{n} x_{i} y_{i}-n \bar{x} \bar{y} .
$$

Sedan löser vi ut $\beta$, vilket ger

$$
\beta=\frac{\sum_{i=1}^{n} x_{i} y_{i}-n \bar{x} \bar{y}}{\sum_{i=1}^{n} x_{i}^{2}-n \bar{x}^{2}}=\frac{s_{x y}}{s_{x x}},
$$

där vi har infört beteckningarna

$$
s_{x y}=\sum_{i=1}^{n} x_{i} y_{i}-n \bar{x} \bar{y} \text { och } s_{x x}=\sum_{i=1}^{n} x_{i}^{2}-n \bar{x}^{2} .
$$

Notera att dessa kan skrivas om som

$$
s_{x y}=\sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)\left(y_{i}-\bar{y}\right) \text { och } s_{x x}=\sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)^{2},
$$

men att de första uttrycken oftast är enklare att använda i beräkningar.

Vi kan visa att denna kritiska punkt för $\log L(\alpha, \beta)$ utgör ett globalt maximum. Notera först att för $z_{1}, z_{2}, \ldots, z_{n}$ har vi

$$
\sum_{i=1}^{n}\left(z_{i}-\alpha\right)^{2} \leq \sum_{i=1}^{n}\left(z_{i}-\bar{z}\right)^{2}
$$

för alla $\alpha \in \mathbb{R}$, dvs. att $\bar{z}$ är ett minimum för $\alpha \mapsto \sum_{i=1}^{n}\left(z_{i}-\alpha\right)^{2}$. Om vi då tar $z_{i}=y_{i}-\beta x_{i}$ får vi

$$
\sum_{i=1}^{n}\left(y_{i}-\beta x_{i}-\alpha\right)^{2} \leq \sum_{i=1}^{n}\left(y_{i}-\beta x_{i}-\bar{y}+\beta \bar{x}\right)^{2}
$$

vilket efter multiplikation med $-1 / 2 \sigma^{2}$ plus en konstant då ger

$$
\log L(\alpha, \beta) \leq \log L(\bar{y}-\beta \bar{x}, \beta)
$$

för alla $\alpha \in \mathbb{R}$. Det räcker alltså att maximera högerledet $\log L(\bar{y}-\beta \bar{x}, \beta)$ med avseende på $\beta$. Vi har redan sett att $\beta=s_{x y} / s_{x x}$ utgör en kritisk punkt, så vi måste visa att detta är ett globalt maximum. Vi har alltså

$$
\begin{aligned}
\frac{d}{d \beta} \log L(\bar{y}-\beta \bar{x}, \beta) &=\frac{d}{d \beta}\left(-\frac{1}{2 \sigma^{2}} \sum_{i=1}^{n}\left(y_{i}-\beta x_{i}-\bar{y}+\beta \bar{x}\right)^{2}\right) \\
&=\frac{d}{d \beta}\left(-\frac{1}{2 \sigma^{2}} \sum_{i=1}^{n}\left(y_{i}-\bar{y}-\beta\left(x_{i}-\bar{x}\right)\right)^{2}\right) \\
&=\frac{1}{\sigma^{2}} \sum_{i=1}^{n}\left(y_{i}-\bar{y}-\beta\left(x_{i}-\bar{x}\right)\right)\left(x_{i}-\bar{x}\right) \\
&=\frac{1}{\sigma^{2}} \sum_{i=1}^{n}\left(y_{i}-\bar{y}\right)\left(x_{i}-\bar{x}\right)-\beta\left(x_{i}-\bar{x}\right)^{2}=\frac{1}{\sigma^{2}}\left(s_{x y}-\beta s_{x x}\right) .
\end{aligned}
$$

Detta ger alltså att $\beta=s_{x y} / s_{x x}$ är en kritisk punkt, som väntat. Andraderivatan är

$$
\frac{d^{2}}{d \beta^{2}} \log L(\bar{y}-\beta \bar{x}, \beta)=-\frac{s_{x x}}{\sigma^{2}},
$$

så om $s_{x x} \neq 0$ så är andraderivatan strikt negativ, vilket ger att $\beta=s_{x y} / s_{x x}$ är ett globalt maximum. (Fallet $s_{x x}=0$ motsvarar att $x_{1}=x_{2}=\cdots=x_{n}$ och i detta fall kan vi inte passa en regressionslinje genom punkterna.)

Vi har då att ML-skattningen för $(\alpha, \beta)$ är

$$
\alpha_{\mathrm{obs}}^{\star}=\bar{y}-\beta_{\mathrm{obs}}^{\star} \bar{x} \text { och } \beta_{\mathrm{obs}}^{\star}=\frac{s_{x y}}{s_{x x}} .
$$

Om vi stoppar in dessa värden i ekvationen $y=\alpha+\beta x$ får vi

$$
y=\alpha_{\mathrm{obs}}^{\star}+\beta_{\mathrm{obs}}^{\star} \chi,
$$

vilket kallas den skattade regressionlinjen. Ofta är vi också intresserade i att förutsäga, dvs. göra en prediktion, av väntevärdet $\mu(x)$ för ett visst värde på $x$. Vi har då det skattade väntevärdet

$$
\mu_{\mathrm{obs}}^{\star}(x)=\alpha_{\mathrm{obs}}^{\star}+\beta_{\mathrm{obs}}^{\star} x .
$$

(I boken används notationen $\mu_{0}^{\star}$ och $x_{0}$ istället för $\mu_{\mathrm{obs}}^{\star}(x)$ och $x$, men detta gör det svårare att skilja på skattning och stickprovsvariabel, så vi undviker detta här.)

![](https://cdn.mathpix.com/cropped/2022_11_17_b42a0778021117a00dafg-05.jpg?height=645&width=1266&top_left_y=802&top_left_x=405)

Exempel 2. Vi återkommer nu till bilirubinmodellen ovan. Utifrån mätdata har vi

$$
\sum_{i=1}^{n} x_{i}=2.33 \sum_{i=1}^{n} x_{i}^{2}=0.3701 \quad \sum_{i=1}^{n} y_{i}=1943 \quad \sum_{i=1}^{n} x_{i} y_{i}=259.79
$$

vilket ger $\bar{x}=0.1115, \bar{y}=97.15, s_{x y}=43.1455$ och $s_{x x}=0.121455$. Enligt formlerna ovan ger detta punktskattningarna

$$
\beta_{\mathrm{obs}}^{\star} \approx 355.2 \text { och } \alpha_{\mathrm{obs}}^{\star} \approx 57.5 \text {. }
$$

Låt oss säga att vi har en viss bilirubinhalt $x=0.20$ och vill skatta proteinkoncentrationen. Vi får då

$$
\mu_{\mathrm{obs}}^{\star}(0.20)=\alpha_{\mathrm{obs}}^{\star}+\beta_{\mathrm{obs}}^{\star} \cdot 0.20 \approx 57.5+355.2 \cdot 0.20 \approx 129 .
$$

En viktig egenskap är att skattningarna $\alpha_{\text {obs }}^{\star}$ och $\beta_{\text {obs }}^{\star}$ är linjära i observationerna $y_{1}, y_{2}, \ldots, y_{n}$, dvs. att de kan skrivar som linjärkombinationer av värdena $y_{1}, y_{2}, \ldots, y_{n}$. Detta är en konsekvens av att regressionsmodellen för $y=\alpha+\beta x$ själv är linjär $\mathrm{i}$ $x$. Notera att vi inte har linjäritet för $\alpha_{\text {obs }}^{\star}$ och $\beta_{\text {obs }}^{\star}$ med avseende på $x_{1}, x_{2}, \ldots, x_{n}$, men detta skapar inga större problem eftersom $x$-värdena hålls fixa i modellen. För att göra detta förhållande mer tydligt skriver vi om $\beta_{\text {obs }}^{\star}$ som

$$
\begin{aligned}
\beta_{\mathrm{obs}}^{\star} &=\frac{s_{x y}}{s_{x x}}=\frac{1}{s_{x x}} \sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)\left(y_{i}-\bar{y}\right) \\
&=\frac{1}{s_{x x}}\left(\sum_{i=1}^{n}\left(x_{i}-\bar{x}\right) y_{i}-\sum_{i=1}^{n}\left(x_{i}-\bar{x}\right) \bar{y}\right) \\
&=\frac{1}{s_{x x}}\left(\sum_{i=1}^{n}\left(x_{i}-\bar{x}\right) y_{i}-0\right)=\sum_{i=1}^{n} \frac{x_{i}-\bar{x}}{s_{x x}} y_{i}=\sum_{i=1}^{n} c_{i} y_{i}
\end{aligned}
$$

där $c_{i}=\left(x_{i}-\bar{x}\right) / s_{x x}$. På samma sätt har vi

$$
\alpha_{\mathrm{obs}}^{\star}=\bar{y}-\beta_{\mathrm{obs}}^{\star} \bar{x}=\frac{1}{n} \sum_{i=1}^{n} y_{i}-\sum_{i=1}^{n} c_{i} y_{i} \bar{x}=\sum_{i=1}^{n}\left(\frac{1}{n}-c_{i} \bar{x}\right) y_{i}=\sum_{i=1}^{n} d_{i} y_{i},
$$

där $d_{i}=1 / n-c_{i} \bar{x}$.

Vi kan nu använda linjäritetsrelationerna ovan för att undersöka väntevärdet och variansen hos våra skattningar. Vi har alltså stickprovsvariablerna

$$
\beta^{\star}=\sum_{i=1}^{n} c_{i} Y_{i} \quad \text { och } \quad \alpha^{\star}=\sum_{i=1}^{n} d_{i} Y_{i}
$$

för skattningarna $\beta_{\text {obs }}^{\star}$ respektive $\alpha_{\text {obs }}^{\star}$. För $\beta^{\star}$ har vi då väntevärdet

$$
\begin{aligned}
\mathrm{E}\left[\beta^{\star}\right] &=\mathrm{E}\left[\sum_{i=1}^{n} c_{i} Y_{i}\right]=\sum_{i=1}^{n} c_{i} \mathrm{E}\left[Y_{i}\right]=\sum_{i=1}^{n} c_{i}\left(\alpha+\beta x_{i}\right) \\
&=\frac{1}{s_{x x}} \sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)\left(\alpha+\beta x_{i}\right) \\
&=\frac{1}{s_{x x}}\left(\alpha \sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)+\beta \sum_{i=1}^{n} x_{i}\left(x_{i}-\bar{x}\right)\right) \\
&\left.=\frac{1}{s_{x x}}\left(\alpha \cdot 0+\beta \sum_{i=1}^{n} x_{i}^{2}-\beta \bar{x} \sum_{i=1}^{n} x_{i}\right)\right) \\
&=\frac{1}{s_{x x}} \beta\left(\sum_{i=1}^{n} x_{i}^{2}-n \bar{x}^{2}\right)=\frac{1}{s_{x x}} \beta s_{x x}=\beta,
\end{aligned}
$$

där vi har använt att $\sum_{i=1}^{n} x_{i}-\bar{x}=0$. Skattningen $\beta_{\text {obs }}^{\star}$ är alltså väntevärdesriktig. Eftersom $Y_{1}, Y_{2}, \ldots, Y_{n}$ antas vara oberoende med samma varians $\sigma^{2}$ får vi

$$
\mathrm{V}\left[\beta^{\star}\right]=\mathrm{V}\left[\sum_{i=1}^{n} c_{i} Y_{i}\right]=\sum_{i=1}^{n} c_{i}^{2} \mathrm{~V}\left[Y_{i}\right]=\frac{\sigma^{2}}{s_{x x}^{2}} \sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)^{2}=\frac{\sigma^{2}}{s_{x x}^{2}} s_{x x}=\frac{\sigma^{2}}{s_{x x}} .
$$

Standardavvikelsen är då $\mathrm{D}\left[\beta^{\star}\right]=\sigma / \sqrt{S_{x x}}$ och kan skrivas om som

$$
\mathrm{D}\left[\beta^{\star}\right]=\frac{\sigma}{\sqrt{n}} \cdot \frac{1}{\sqrt{s_{x x} / n}} .
$$

Felet i skattningen blir alltså litet om mätfelet $\sigma$ är litet, antalet mätvärden $n$ är stort eller spridningen $s_{x x} / n$ av $x$-värdena är stor. Eftersom felet går mot noll då $n \rightarrow+\infty$ så är skattningen konsistent.

Istället för att beräkna väntevärdet och variansen för $\alpha^{\star}$ utför vi beräkningen för $\mu^{\star}(x)$. Vi får då värdena för $\alpha^{\star}$ genom att sätta in $x=0$ eftersom $\alpha^{\star}=\mu^{\star}(0)$. Först har vi alltså väntevärdet

$$
\begin{aligned}
\mathrm{E}\left[\mu^{\star}(x)\right] &=\mathrm{E}\left[\alpha^{\star}+\beta^{\star} x\right]=\mathrm{E}\left[\sum_{i=1}^{n}\left(d_{i}+c_{i} x\right) Y_{i}\right]=\sum_{i=1}^{n}\left(d_{i}+c_{i} x\right) \mathrm{E}\left[Y_{i}\right] \\
&=\sum_{i=1}^{n}\left(\frac{1}{n}-c_{i} \bar{x}+c_{i} x\right)\left(\alpha+\beta x_{i}\right) \\
&=\sum_{i=1}^{n}\left(\frac{1}{n}+c_{i}(x-\bar{x})\right)\left(\alpha+\beta x_{i}\right) \\
&=\sum_{i=1}^{n} \frac{\alpha}{n}+\alpha c_{i}(x-\bar{x})+\frac{\beta x_{i}}{n}+\beta x_{i} c_{i}(x-\bar{x}) \\
&=\alpha+\beta \bar{x}+(x-\bar{x}) \sum_{i=1}^{n} c_{i}+\beta(x-\bar{x}) \sum_{i=1}^{n} x_{i} c_{i}
\end{aligned}
$$

Vi kan förenkla detta uttryck genom att beräkna

$$
\sum_{i=1}^{n} c_{i}=\frac{1}{s_{x x}} \sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)=\frac{1}{s_{x x}}\left(\sum_{i=1}^{n} x_{i}-n \bar{x}\right)=\frac{1}{s_{x x}}(n \bar{x}-n \bar{x})=0
$$

och

$$
\sum_{i=1}^{n} x_{i} c_{i}=\frac{1}{s_{x x}} \sum_{i=1}^{n} x_{i}\left(x_{i}-\bar{x}\right)=\frac{1}{s_{x x}}\left(\sum_{i=1}^{n} x_{i}^{2}-\bar{x} \sum_{i=1}^{n} x_{i}\right)=\frac{1}{s_{x x}}\left(\sum_{i=1}^{n} x_{i}^{2}-n \bar{x}^{2}\right)=\frac{1}{s_{x x}} \cdot s_{x x}=1 \text {. }
$$

Om vi sätter in dessa identiteter får vi

$$
\mathrm{E}\left[\mu^{\star}(x)\right]=\alpha+\beta \bar{x}+\beta(x-\bar{x})=\alpha+\beta x .
$$

Med andra ord är skattningen $\mu_{\mathrm{obs}}^{\star}(\chi)$ väntevärdesriktig (och likaså $\alpha_{\mathrm{obs}}^{\star}=\mu_{\mathrm{obs}}^{\star}(0)$ ). Variansen fås på liknande sätt:

$$
\begin{aligned}
\mathrm{V}\left[\mu^{\star}(x)\right] &=\mathrm{V}\left[\sum_{i=1}^{n}\left(d_{i}+c_{i} \chi\right) Y_{i}\right]=\sum_{i=1}^{n}\left(d_{i}+c_{i} \chi\right)^{2} \mathrm{~V}\left[Y_{i}\right]=\sigma^{2} \sum_{i=1}^{n}\left(\frac{1}{n}+c_{i}(x-\bar{x})\right)^{2} \\
&=\sigma^{2} \sum_{i=1}^{n} \frac{1}{n^{2}}+2 \frac{(x-\bar{x})}{n} c_{i}+c_{i}^{2}(x-\bar{x})^{2} \\
&=\sigma^{2}\left(\frac{1}{n}+2 \frac{(x-\bar{x})}{n} \sum_{i=1}^{n} c_{i}+(x-\bar{x})^{2} \sum_{i=1}^{n} c_{i}^{2}\right) \\
&=\sigma^{2}\left(\frac{1}{n}+2 \frac{(x-\bar{x})}{n} \cdot 0+(x-\bar{x})^{2} \frac{1}{s_{x x}}\right)=\sigma^{2}\left(\frac{1}{n}+\frac{(x-\bar{x})^{2}}{s_{x x}}\right)
\end{aligned}
$$

där vi har använt att $\sum_{i=1}^{n} c_{i}=0$ och att

$$
\sum_{i=1}^{n} c_{i}^{2}=\frac{1}{s_{x x}^{2}} \sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)^{2}=\frac{1}{s_{x x}^{2}} \cdot s_{x x}=\frac{1}{s_{x x}} .
$$

Om vi tar ut faktorn $1 / n$ får vi då standardavvikelsen

$$
\mathrm{D}\left[\mu^{\star}(x)\right]=\frac{\sigma}{\sqrt{n}} \cdot \sqrt{1+\frac{(x-\bar{x})^{2}}{s_{\chi x} / n}} .
$$

![](https://cdn.mathpix.com/cropped/2022_11_17_b42a0778021117a00dafg-08.jpg?height=632&width=1258&top_left_y=1527&top_left_x=409)

Låt oss analysera detta fel lite närmare. Först har vi den bekanta $\sigma / \sqrt{n}$-faktorn felet är proportionellt med det ursprungliga mätfelet $\sigma$ och avtar som kvadratroten av stickprovsstorleken $n$. Den andra faktorn $\sqrt{1+(x-\bar{x})^{2} /\left(s_{x x} / n\right)}$ är ny. Vi såg $s_{x x} / n$ innan i samband med felet i skattningen $\beta_{\text {obs }}^{\star}$ - detta motsvarar spridningen i $x-$ värdena. Om kvadratavståndet $(x-\bar{x})^{2}$ är litet med avseende på denna spridning får vi ett litet fel (så litet som grundfelet $\sigma / \sqrt{n}$ tillåter). Om å andra sidan $x$ ligger långt ifrån $\bar{x}$, längre bort än $x$-värdena $x_{1}, x_{2}, \ldots, x_{n}$ (som använts för att skatta $\alpha$ och $\beta$ ) ligger, då får vi ett större fel. Anledningen till detta är att vi går från interpolering till extrapolering. Nära $\bar{x}$ har vi god kännedom av regressionslinjen, vi har många $x$-och $y$-värden som tvingar vår skattning $\mu_{\text {obs }}^{\star}(x)$ in i ett snävt intervall. Längre bort finns många olika linjer som skulle passa de givna $x$-och $y$-värdena lika bra och vi har därför större osäkerhet.

Innan vi går vidare ska vi gå tillbaka till regressionsmodellen $Y_{i}=\alpha+\beta x_{i}+E_{i}$. Vi har skattat $\alpha$ och $\beta$ men antagit att $V\left[E_{i}\right]=\sigma^{2}$ är känd (även om detta inte spelar någon roll såvida vi behöver standardavvikelserna $D\left[\beta^{\star}\right]$ och $D\left[\mu^{\star}(x)\right]$ ). Så behöver inte nödvändigtvis vara fallet. För att åstadkomma detta behöver vi skatta $\alpha, \beta$ och $\sigma^{2}$ samtidigt. Som innan sätter vi då upp likelihoodfunktionen

$$
\begin{aligned}
L\left(\alpha, \beta, \sigma^{2}\right) &=L\left(\alpha, \beta, \sigma^{2} ;\left(x_{1}, y_{1}\right),\left(x_{2}, y_{2}\right), \ldots,\left(x_{n}, y_{n}\right)\right) \\
&=\frac{1}{\left(2 \pi \sigma^{2}\right)^{n / 2}} e^{-\frac{1}{2 \sigma^{2}} \sum_{i=1}^{n}\left(y_{i}-\alpha-\beta x_{i}\right)^{2}} .
\end{aligned}
$$

Vi kan då beräkna partialderivatorna med avseende på $\alpha, \beta$ och $\sigma^{2}$, sätta dessa till noll för att hitta en kritisk punkt. Vi visar sedan att denna punkt är ett globalt maximum och därför utgör vår ML-skattning för parametrarna. För $\alpha$ och $\beta$ får vi samma $\alpha_{\text {obs }}^{\star}$ och $\beta_{\text {obs }}^{\star}$ som innan och för $\sigma^{2}$ får vi skattningen

$$
\left(\sigma^{2}\right)_{\mathrm{obs}}^{\star}=\frac{1}{n} \sum_{i=1}^{n}\left(y_{i}-\alpha_{\mathrm{obs}}^{\star}-\beta_{\mathrm{obs}}^{\star}\right)^{2} .
$$

Värdena $y_{i}-\alpha_{\text {obs }}^{\star}-\beta_{\text {obs }}^{\star}$ brukar kallas regressionsmodellens residualer och betecknas ofta med $r_{i}$. Eftersom $\alpha_{\text {obs }}^{\star}=\bar{y}-\beta_{\text {obs }}^{\star} \bar{x}$ har vi att

$$
\begin{aligned}
& \sum_{i=1}^{n} r_{i}^{2}=\sum_{i=1}^{n}\left(\left(y_{i}-\bar{y}\right)-\beta_{\mathrm{obs}}^{\star}\left(x_{i}-\bar{x}\right)\right)^{2} \\
& =\sum_{i=1}^{n}\left(y_{i}-\bar{y}\right)^{2}-2 \beta_{\mathrm{obs}}^{\star} \sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)\left(y_{i}-\bar{x}\right)+\left(\beta_{\mathrm{obs}}^{\star}\right)^{2} \sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)^{2} \\
& =s_{y y}-2 \beta_{\mathrm{obs}}^{\star} s_{x y}+\left(\beta_{\mathrm{obs}}^{\star}\right)^{2} s_{x x}=s_{y y}-\frac{s_{x y}^{2}}{s_{x x}},
\end{aligned}
$$

där vi infört notationen $s_{y y}=\sum_{i=1}^{n}\left(y_{i}-\bar{y}\right)^{2}$. ML-skattningen ovan är då

$$
\left(\sigma^{2}\right)_{\mathrm{obs}}^{\star}=\sum_{i=1}^{n} r_{i}^{2} / n=\left(s_{y y}-s_{x y}^{2} / s_{x x}\right) / n
$$

Denna är tyvärr inte väntevärdesriktig och måste korrigeras genom multiplikation med faktorn $n /(n-2)$, vilket ger den väntevärdesriktiga skattningen

$$
s^{2}=\frac{1}{n-2} \sum_{i=1}^{n}\left(y_{i}-\alpha_{\mathrm{obs}}^{\star}-\beta_{\mathrm{obs}}^{\star}\right)^{2}=\frac{1}{n-2} \sum_{i=1}^{n} r_{i}^{2}=\frac{s_{y y}-s_{x y}^{2} / s_{x x}}{n-2} .
$$

Kvadratroten s utgör då en punktskattning för $\sigma$. (Faktorn $n-2$ i nämnaren fås eftersom summan av residualerna är utfall av en $\chi^{2}$-fördelning med $n-2$ frihetsgrader. Anledningen till att vi har "förlorat" två frihetsgrader är att vi redan skattat två parametrar $\alpha$ och $\beta$ och dessa då är "fixa" när vi bildar kvadratsumman.) Exempel 3. I bilirubinexemplet är inte standaravvikelsen $\sigma$ känd utan måste skattas. Utifrån datan har vi

$$
\sum_{i=1}^{n} y_{i}^{2}=215061
$$

vilket ger $s_{y y}=26298.55$. Sedan innan hade vi $s_{x y}=43.1455$ och $s_{x x}=0.1211455$ så vi har då

$$
s^{2}=\frac{s_{y y}-s_{x y}^{2} / s_{x x}}{n-2} \approx 609.5
$$

och vi får då skattningen $s \approx 24.69 \mathrm{av} \sigma$.

Om vi stoppar in detta istället för $\sigma$ i formeln för standardavvikelsen $\mathrm{D}\left[\beta^{\star}\right]$ får vi medelfelet

$$
d\left(\beta^{\star}\right)=s / \sqrt{s_{x x}} \approx 70.84 .
$$

För $x=0.20$ har $v i$

$$
d\left(\mu^{\star}(0.20)\right)=(s / \sqrt{n}) \sqrt{1+(0.20-\bar{x})^{2} /\left(s_{x x} / n\right)} \approx 8.35 .
$$

Med tanke på att skattningarna själva är $\beta_{\text {obs }}^{\star} \approx 355.2$ respektive $\mu_{\text {obs }}^{\star}(0.20) \approx 129$ så är dessa fel varken mycket små eller mycket stora. Om vi istället skulle skatta $\mu(x)$ för ett $x$ långt ifrån $\bar{x}=0.1115$ skulle vi få ett större medelfel.

\section{Intervallskattning och hypotestest}

Som vi såg ovan är skattningarna $\alpha_{\mathrm{obs}}^{\star}{ }^{\prime} \beta_{\mathrm{obs}}^{\star}$ och $\mu_{\mathrm{obs}}^{\star}(x)$ linjärkombinationer av mätvärden $y_{1}, y_{2}, \ldots, y_{n}$. Eftersom mätvärdena är utfall av de oberoende, normalfördelade stokastiska variablerna $Y_{1}, Y_{2}, \ldots, Y_{n}$ så gäller att även stickprovsvariablerna $\alpha^{\star}, \beta^{\star}$ och $\mu^{\star}$ är normalfördelade. Utifrån de beräknade väntevärdena och standardavvikelserna ovan får vi då att

$$
\beta^{\star} \sim \mathrm{N}\left(\beta, \frac{\sigma}{\sqrt{n}} \cdot \frac{1}{\sqrt{s_{x x} / n}}\right) \quad \text { och } \mu^{\star}(x) \sim \mathrm{N}\left(\alpha+\beta x, \frac{\sigma}{\sqrt{n}} \cdot \sqrt{1+\frac{(x-\bar{x})^{2}}{s_{x x} / n}}\right) \text {. }
$$

(Återigen får vi fördelningen för $\alpha^{\star}$ genom förhållandet $\alpha^{\star}=\mu^{\star}(0)$.)

Om $\sigma$ är känd har vi då konfidensintervallen

$$
\begin{aligned}
I_{\beta} &=\left[\beta_{\mathrm{obs}}^{\star}-\lambda_{p / 2} D, \beta_{\mathrm{obs}}^{\star}+\lambda_{p / 2} D\right] & \text { där } D=\frac{\sigma}{\sqrt{n}} \cdot \frac{1}{\sqrt{s_{x x} / n}}, \\
I_{\mu(x)} &=\left[\mu_{\mathrm{obs}}^{\star}(x)-\lambda_{p / 2} D, \mu_{\mathrm{obs}}^{\star}(x)+\lambda_{p / 2} D\right] & \text { där } D=\frac{\sigma}{\sqrt{n}} \cdot \sqrt{1+\frac{(x-\bar{x})^{2}}{s_{x x} / n}},
\end{aligned}
$$

med konfidensgrad $1-p$. (Vi använder beteckningen $p$ här istället för $\alpha$ eftersom denna redan används för konstanttermen i regressionsmodellen.) Om $\sigma$ är okänd måste denna skattas med $s=\sqrt{\left(s_{y y}-s_{x y}^{2} / s_{x x}\right) /(n-2)}$ och man kan då visa att

$$
\frac{\beta^{\star} \sqrt{S_{x x} / n}}{s / \sqrt{n}} \sim \mathrm{t}(n-2) \quad \text { och } \frac{\mu^{\star}(x)\left(1+\frac{(x-\bar{x})^{2}}{s_{x x} / n}\right)^{-1 / 2}}{s / \sqrt{n}} \sim \mathrm{t}(n-2) .
$$

Detta ger då konfidensintervallen

$$
\begin{array}{rlr}
I_{\beta} & =\left[\beta_{\mathrm{obs}}^{\star}-t_{p / 2}(n-2) d, \beta_{\mathrm{obs}}^{\star}+t_{p / 2}(n-2) d\right] \quad & \text { där } d=\frac{s}{\sqrt{n}} \cdot \frac{1}{\sqrt{s_{x x} / n}}, \\
I_{\mu(x)} & =\left[\mu_{\mathrm{obs}}^{\star}(x)-t_{p / 2}(n-2) d, \mu_{\mathrm{obs}}^{\star}(x)+t_{p / 2}(n-2) d\right] & \text { där } d=\frac{s}{\sqrt{n}} \cdot \sqrt{1+\frac{(x-\bar{x})^{2}}{s_{x x} / n}},
\end{array}
$$

med konfidensgrad $1-p$

Dessa konfidensintervall kan också användas för att konstruera hypotesttest genom konfidensmetoden. Till exempel kan vi pröva nollhypotesen att $y$ inte beror på $x$, dvs. $H_{0}: \beta=0$ genom att $H_{0}$ förkastas med signifikansnivå $p$ om $0 \notin I_{\beta}$, där $I_{\beta}$ är ett konfidensintervall för $\beta$ med konfidensgrad $1-p$.

Exempel 4. I bilirubinexemplet fann vi att $\beta_{\text {obs }}^{\star} \approx 355.2$ och $s \approx 24.69$, vilket gav medelfelet $d\left(\beta^{\star}\right) \approx 70.84$. Eftersom $n=20$ har vi då kvantilerna $\mathrm{t}_{p / 2}(n-2)=$ $t_{0.025}(18) \approx 2.101$ för konfidensgraden $1-p=0.95$, vilket ger konfidensintervallet

$$
\begin{aligned}
I_{\beta} &=\beta_{\mathrm{obs}_{\star}} \pm \mathrm{t}_{0.025}(18) d\left(\beta^{\star}\right) \\
& \approx 355.2 \pm 2.101 \cdot 70.84 \\
& \approx 355.2 \pm 138.8 \approx[216.8,494.5] .
\end{aligned}
$$

Vi kan alltså förkasta hypotesen $H_{0}: \beta=0$ med signifikansnivå $p=0.05$ - det finns alltså troligen ett samband mellan bilirubinhalt och proteinkoncentration. Intervallet är däremot stort, vilket betyder att vi inte kan bestämma detta samband särskilt exakt med de data som vi har att tillgå. Samma kalkyl för $\mu(0.20)$ ger intervallet

$$
I_{\mu(0.20)} \approx 129 \pm 16.4 \approx[112,145],
$$

vilket också är ganska brett.

\section{Multipel linjär regression}

Vi noterar till sist att den linjära regressionsmodellen kan generaliseras till fler än en regressionsvariabel. Vi har då modellen

$$
y=\alpha+\beta_{1} x_{1}+\beta_{2} x_{2}+\cdots+\beta_{k} x_{k},
$$

där vi behöver skatta parametrarna $\alpha, \beta_{1}, \beta_{2}, \ldots, \beta_{k}$ utifrån mätdata

$$
\left(x_{11}, x_{21}, \ldots, x_{k 1}, y_{1}\right),\left(x_{12}, x_{22}, \ldots, x_{k 2}, y_{2}\right), \ldots,\left(x_{1 n}, x_{2 n}, \ldots, x_{k n}, y_{n}\right) \text {. }
$$

Vi betraktar då $y$-värdena $y_{1}, y_{2}, \ldots, y_{n}$ som utfall av oberoende stokastiska variabler $Y_{1}, Y_{2}, \ldots, Y_{n}$ med fördelningar

$$
Y_{i} \sim N\left(\mu_{i}, \sigma\right) \quad \text { där } \mu_{i}=\alpha+\beta_{1} \chi_{1 i}+\beta_{2} x_{2 i}+\ldots+\beta_{k} x_{k i},
$$

för $i=1,2, \ldots, n$. Som innan kan vi då bilda likelihoodfunktionen $L\left(\alpha, \beta_{1}, \beta_{2}, \ldots, \beta_{k}\right)$ och maximera denna för att få ML-skattningarna $\alpha_{\text {obs }}^{\star}\left(\beta_{1}\right)_{\text {obs }}^{\star}\left(\beta_{2}\right)_{\text {obs }}^{\star}, \ldots,\left(\beta_{n}\right)_{\text {obs }}^{\star}$. Från dessa kan vi utveckla intervallskattningar och hypotestest precis som innan. Tyvärr blir beräkningarna här mer komplicerade och kräver verktyg som ligger utanför denna kurs. Mer information om regression (både enkel och multipel) kommer att behandlas i fortsättningskursen SF2930 Regressionanalys. Vi kommer också att utforska multipel regression i sista uppgiften av den andra datorlaborationen.