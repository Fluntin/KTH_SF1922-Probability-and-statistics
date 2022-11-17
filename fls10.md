\title{
Föreläsning tio
}

\author{
Joakim Andén
}

28 november 2022

\section{Intervallskattning}

I föregående föreläsningar har vi diskuterat punktskattningar. Dessa skattningar ger ett visst värde $\theta_{\text {obs }}^{\star}$ på en sökt parameter $\theta$, men inget mer. Punktskattningen kan ha flera bra egenskaper som väntevärdesriktighet, konsistens och effektivitet. Detta betyder att skattningen är någorlunda exakt, speciellt om stickprovsstorleken $n$ är stor, men detta säger inte så mycket om hur säker vår punktskattning är, rent konkret.

För att få en uppfattning om måttet av osäkerhet i skattningen såg vi i den senaste föreläsningen att vi kan skatta standardavvikelsen hos punktskattningen i form av medelfelet $d\left(\theta^{\star}\right)$. Detta säger att den sanna parametern $p$ borde ligga någonstans mellan $\theta_{\text {obs }}^{\star}-d\left(\theta^{\star}\right)$ och $\theta_{\text {obs }}^{\star}+d\left(\theta^{\star}\right)$. Vi ska nu vidareutveckla detta och skatta parametrar med hjälp av intervall som innehåller det sanna värdet på parametern med en viss sannolikhet. Med andra ord söker vi inte längre påståenden på formen

Andelen p som tänker rösta ja är ungefär $0.45$, utan

Andelen p som tänker rösta ja ligger mellan $0.43$ och $0.47$ med $95 \%$ sannolikhet

eller

Andelen p som tänker rösta ja är större än $0.44$ med $95 \%$ sannolikhet.

Formellt söker vi funktioner $a_{1}\left(x_{1}, x_{2}, \ldots, x_{n}\right)$ och $a_{2}\left(x_{1}, x_{2}, \ldots, x_{n}\right)$ av mätvärdena $x_{1}, x_{2}, \ldots, x_{n}$ så att för stickprovet $x_{1}, x_{2}, \ldots, x_{n}$ gäller

$$
\mathrm{P}\left(a_{1}\left(X_{1}, X_{2}, \ldots, X_{n}\right)<\theta<a_{2}\left(X_{1}, X_{2}, \ldots, X_{n}\right)\right)=1-\alpha
$$

för något $\alpha>0$. Vi säger då att $I_{\theta}=\left[a_{1}\left(x_{1}, x_{2}, \ldots, x_{n}\right), a_{2}\left(x_{1}, x_{2}, \ldots, x_{n}\right)\right]$ är ett konfidensintervall för $\theta$ med konfidensgrad $1-\alpha$. 

![](https://cdn.mathpix.com/cropped/2022_11_17_e94059db2c7bd7807eb9g-02.jpg?height=444&width=1174&top_left_y=266&top_left_x=497)

Notera att slumpmässigheten i uttrycket ovan härstammar inte från parametern $\theta$ (som är konstant), utan från stickprovet $X_{1}, X_{2}, \ldots, X_{n}$. Med andra ord så ska vi inte se detta som sannolikheten att ett slumpmässigt $\theta$ ligger i det fixa intervallet $I_{\theta}$ utan som sannolikheten att det slumpmässiga intervallet $I_{\theta}$ täcker det fixa $\theta$.

Om både $a_{1}$ och $a_{2}$ är ändliga kallas konfidensintervallet $I_{\theta}$ för tvåsidigt. Om någon av dem är oändliga (dvs. om $a_{1}=-\infty$ eller $a_{2}=+\infty$ ) kallas intervallet ensidigt och motsvarar

$$
\mathrm{P}\left(\theta<a_{2}\left(X_{1}, X_{2}, \ldots, X_{n}\right)\right)=1-\alpha \text { eller } \mathrm{P}\left(a_{1}\left(X_{1}, X_{2}, \ldots, X_{n}\right)<\theta\right)=1-\alpha .
$$

Exempel 1. Vi vet att $X \sim N(\theta, \sigma)$, dvs. ett stickprov met endast ett mätvärde $(n=1)$. Standardavvikelsen $\sigma$ är känd, men vi vill skatta väntevärdet $\theta$ utifrån ett utfall $x$ av $X$.

I detta fall vet vi att

$$
Z=\frac{x-\mu}{\sigma} \sim N(0,1),
$$

och kan då använda kvantilerna $\lambda_{\alpha}$ för den standardiserade normalfördelningen och få

$$
P\left(-\lambda_{\alpha / 2}<Z<\lambda_{\alpha / 2}\right)=1-\alpha .
$$

(Kom ihåg att $\lambda_{1-\alpha / 2}=-\lambda_{\alpha / 2}$ eftersom $N(0,1)$ är symmetrisk.) Relationen $-\lambda_{\alpha / 2}<$ $Z<\lambda_{\alpha / 2}$ består av olikheterna $-\lambda_{\alpha / 2}<Z$ och $Z<\lambda_{\alpha / 2}$, vilka kan omvandlas enligt

$$
\begin{aligned}
-\lambda_{\alpha / 2} &<Z=\frac{X-\theta}{\sigma} \\
-\lambda_{\alpha / 2} \sigma &<X-\theta \\
-X-\lambda_{\alpha / 2} \sigma &>-\theta \\
\theta &<X+\lambda_{\alpha / 2} \sigma
\end{aligned}
$$

och vi får på samma sätt

$$
x-\lambda_{\alpha / 2} \sigma<\theta,
$$

vilket ger den sammansatta relationen

$$
X-\lambda_{\alpha / 2} \sigma<\theta<X+\lambda_{\alpha / 2} \sigma
$$

Vi får då sannolikheten

$$
P\left(X-\lambda_{\alpha / 2} \sigma<\theta<X+\lambda_{\alpha / 2} \sigma\right)=1-\alpha .
$$

Med andra ord om vi tar $a_{1}(x)=x-\lambda_{\alpha / 2} \sigma$ och $a_{2}(x)=x+\lambda_{\alpha / 2} \sigma$ har vi konfidensintervallet $I_{\theta}=\left[a_{1}(x), a_{2}(x)\right]$ för $\theta$ med konfidensgraden $1-\alpha$.

![](https://cdn.mathpix.com/cropped/2022_11_17_e94059db2c7bd7807eb9g-03.jpg?height=404&width=746&top_left_y=622&top_left_x=684)

Låt oss anta att $x=-0.69$ och $\sigma=0.66$. Med $\alpha=0.05$ får vi $\lambda_{\alpha / 2}=\lambda_{0.025} \approx$ $1.96$, vilket ger konfidensintervallet $I_{\theta}=[-1.98,0.61]$. (Utfallet $x$ var i detta fall genererat med parametern $\theta=0.1$, så denna ingick $i$ intervallet för skattningen.)

Vad händer med intervallet när vi ändrar parametrarna? Om $\sigma$ ökar så får vi ett bredare intervall. Detta motsvarar att vårt mätvärde $x$ ger mindre information om parametern $\theta$ som vi söker. På samma sätt kan vi minska $\alpha$ (dvs. öka konfidensgraden $1-\alpha$ ). Detta ger då ett större värde på $\lambda_{\alpha}$, vilket $i$ sin tur ger ett bredare intervall. Tolkningen är här att om vi vill vara säkrare på att intervallet verkligen täcker $\theta$ så måste vi öka storleken.

Exemplet ovan anger en generell metod som kan användas för de flesta intervallskattningarna.

(i) Hitta en punktskattning $\theta^{\star}$ för parametern $\theta$ givet utfallet $x_{1}, x_{2}, \ldots, x_{n}$ av stickprovet $X_{1}, X_{2}, \ldots, X_{n}$. Detta kan, till exempel, vara en ML- eller MK-skattning, ett stickprovsmedelvärde eller en stickprovsvarians. (Ovan hade vi bara utfallet $x$ självt.)

(ii) Bestäm fördelningen för $\theta^{\star}$. Denna beror då oftast på det sanna värdet på parametern $\theta$. (Ovan hade vi $X \sim N(\theta, \sigma)$.)

(iii) Transformera $\theta^{\star}$ så att dess fördelning inte beror på parametern $\theta$. Detta kallas för en pivotvariabel. (Ovan var detta $Z=(X-\theta) / \sigma \sim N(0,1)$.)

(iv) Använd kvantiler hos pivotvariabelns fördelning för att bilda ett intervall för pivotvariabeln som håller med sannolikhet $1-\alpha$. (Ovan hade vi $-\lambda_{\alpha / 2}<Z<$ $\lambda_{\alpha / 2 .)}$

(v) Transformera detta till ett konfidensintervall för $\theta$ där ändpunkterna beror på stickprover $X_{1}, X_{2}, \ldots, X_{n}$. (Ovan gav detta $I_{\theta}=\left[x-\lambda_{\alpha / 2} \sigma, x+\lambda_{\alpha / 2} \sigma\right]$.)

Vi kommer nu tillämpa denna metod i olika former på ett par typexempel. 

\section{Normalfördelat stickprov}

Vi kommer nu betrakta fallet då stickprovet $X_{1}, X_{2}, \ldots, X_{n}$ består av oberoende normalfördelade variabler och vi vill skatta väntevärdet $\mu$, standardavvikelsen $\sigma$ eller båda två.

Exempel 2. (Skatta $\mu$, känt o) Antag att vi har ett stickprov $x_{1}, x_{2}, \ldots, x_{n}$ av oberoende stokastiska variabler fördelade enligt $\mathrm{N}(\mu, \sigma)$. Vi antar att $\sigma$ är känd och vill skatta $\mu$ utifrain $x_{1}, x_{2}, \ldots, x_{n}$.

För detta använder vi förslagsvis ML-skattningen, dvs. stickprovsmedelvärdet,

$$
\bar{x}=\frac{1}{n} \sum_{i=1}^{n} x_{i} .
$$

Den motsvarande stickprovsvariabeln $\bar{X}$ har fördelningen $N(\mu, \sigma / \sqrt{n})$. Utifrån denna bildar vi pivotvariabeln

$$
Z=\frac{\bar{x}-\mu}{\sigma / \sqrt{n}} \sim \mathrm{N}(0,1)
$$

vars fördelning är oberoende av $\mu$ (i det här fallet också oberoende av $\sigma$, vilket förenklar nästa steg ytterligare). Med denna använder vi kvantilerna $-\lambda_{\alpha / 2}$ och $\lambda_{\alpha / 2}$ för den standardiserade normalfördelningen och får

$$
P\left(-\lambda_{\alpha / 2}<\frac{\bar{X}-\mu}{\sigma / \sqrt{n}}<\lambda_{\alpha / 2}\right)=1-\alpha .
$$

Vi transformerar nu detta (se föregående exempel) till ett intervall runt $\mu$, vilket ger

$$
P\left(\bar{X}-\frac{\lambda_{\alpha / 2} \sigma}{\sqrt{n}}<\mu<\bar{X}+\frac{\lambda_{\alpha / 2} \sigma}{\sqrt{n}}\right)=1-\alpha .
$$

Ett tvåsidigt konfidensintervall för $\mu$ med konfidensgrad $1-\alpha$ är då

$$
I_{\mu}=\left[\bar{x}-\frac{\lambda_{\alpha / 2} \sigma}{\sqrt{n}}, \bar{x}+\frac{\lambda_{\alpha / 2} \sigma}{\sqrt{n}}\right] .
$$

Intervallet blir snävt när $\sigma$ är litet eller $n$ är stort. I dessa fall har vi högt förtroende (dvs. konfidens) till vår punktskattning $\theta^{\star}$ och denna ligger med stor sannolikhet nära det sanna värdet $\theta$.

På samma sätt erhåller vi ensidiga konfidensintervall med konfidensgrad $1-\alpha$ på formen

$$
\left(-\infty, \bar{x}+\frac{\lambda_{\alpha} \sigma}{\sqrt{n}}\right) \text { och }\left(\bar{x}-\frac{\lambda_{\alpha} \sigma}{\sqrt{n}},+\infty\right) \text {. }
$$

Fallet ovan med ett känt $\sigma$ uppkommer till exempel när kalibrerad mätutrustning används för vilken standardavvikelsen är specificerad. Dock är det vanligt att standardavvikelsen inte är känd (eller given men inte helt tillförlitlig). I detta fall måste vi skatta både $\mu$ och $\sigma$. Låt oss börja med $\mu$. Exempel 3. (Skatta $\mu$, okänt $\sigma$ ) Ȧterigen antar vi att vi har ett stickprov $X_{1}, X_{2}, \ldots, X_{n}$ av oberoende stokastiska variabler fördelade enligt $\mathrm{N}(\mu, \sigma)$. Nu är både $\mu$ och $\sigma$ okända och vi vill skatta $\mu$ utifrån $x_{1}, x_{2}, \ldots, x_{n}$.

Om vi använder stickprovsmedelvärdet $\bar{X}$ och försöker bilda pivotvariabeln

$$
Z=\frac{\bar{x}-\mu}{\sigma / \sqrt{n}}
$$

ser vi genast ett problem: vi kan inte dela med $\sigma$ eftersom denna inte är känd (mer exakt så måste $\sigma$ ingå $i$ ändpunkterna hos intervallet, vilket inte är möjligt eftersom den inte är känd). Istället har vi en skattning, stickprovsstandardavvikelsen

$$
S=\sqrt{\frac{1}{n-1} \sum_{i=1}\left(X_{i}-\bar{X}\right)^{2}} .
$$

Om vi sätter in denna istället för $\sigma$ för vi

$$
T=\frac{\bar{X}-\mu}{S / \sqrt{n}}=\frac{(\bar{X}-\mu) \sqrt{n}}{S} .
$$

Frågan är nu om $T$ är en pivotvariabel, dvs. om fördelningen av $T$ beror på de okända parametrarna $\mu$ och $\sigma$.

Eftersom $X_{i}$ är normalfördelad med väntevärde $\mu$ och standardavvikelse $\sigma$ kan vi skriva

$$
X_{i}=\mu+\sigma Z_{i}
$$

där $Z_{i} \sim \mathrm{N}(0,1)$. Om vi betecknar $\bar{Z}=\frac{1}{n} \sum_{i=1}^{n} Z_{i}$ har vi då $\bar{X}=\mu+\sigma \bar{Z}$, vilket ger

$$
\bar{X}-\mu=\sigma \bar{Z}
$$

och is kan vi då faktorera ut $\sigma$ och få

$$
S=\sqrt{\frac{1}{n-1} \sum_{i=1}\left(X_{i}-\bar{X}\right)^{2}}=\sigma \sqrt{\frac{1}{n-1} \sum_{i=1}\left(Z_{i}-\bar{Z}\right)^{2}} .
$$

Vi kan då skriva om $T$ som

$$
T=\frac{\bar{Z} \sqrt{n}}{\sqrt{\frac{1}{n-1} \sum_{i=1}^{n}\left(Z_{i}-\bar{Z}\right)^{2}}} .
$$

Den stokastiska variabeln $T$ beror alltså bara på de standardiserade variablerna $Z_{i}$ och dess fördelning kan således inte bero på $\mu$ eller $\sigma$.

Vad är då T:s fördelning? Man kan visa dess täthetsfunktion är

$$
f_{T}(t)=\frac{\Gamma(n / 2)}{\sqrt{(n-1) \pi} \Gamma\left(\frac{n-1}{2}\right)}\left(1+\frac{t^{2}}{n-1}\right)^{-n / 2} .
$$

Fördelningen kallas t-fördelningen med $n-1$ frihetsgrader (detta motsvarar antalet oberoende termer $i$ kvadratsumman $\left.\sum_{i=1}^{n}\left(Z_{i}-\bar{Z}\right)^{2}\right)$ och betecknas $t(n-1)$. Vi betecknar dess kvantiler med $\mathrm{t}_{\alpha}(n-1)$, dvs. att

![](https://cdn.mathpix.com/cropped/2022_11_17_e94059db2c7bd7807eb9g-06.jpg?height=604&width=742&top_left_y=381&top_left_x=667)

Likt normalfördelningen är t-fördelningen symmetrisk $\left(f_{T}(-t)=f_{T}(t)\right)$, vilket ger att $\mathrm{t}_{1-\alpha}(n-1)=-\mathrm{t}_{\alpha}(n-1)$. Vi har då

$$
P\left(-\mathrm{t}_{\alpha / 2}(n-1)<T<\mathrm{t}_{\alpha / 2}(n-1)\right)=1-\alpha,
$$

$d v s$.

$$
P\left(-\mathrm{t}_{\alpha / 2}(n-1)<\frac{(\bar{X}-\mu) \sqrt{n}}{S}<\mathrm{t}_{\alpha / 2}(n-1)\right)=1-\alpha,
$$

vilket ger

$$
P\left(\bar{x}-\frac{S}{\sqrt{n}} \mathrm{t}_{\alpha / 2}(n-1)<\mu<\bar{x}+\frac{S}{\sqrt{n}} \mathrm{t}_{\alpha / 2}(n-1)\right)=1-\alpha .
$$

Ett konfidensintervall för $\mu$ med konfidensgrad $1-\alpha$ är alltså

$$
I_{\mu}=\left[\bar{x}-\frac{s}{\sqrt{n}} \mathrm{t}_{\alpha / 2}(n-1), \bar{x}+\frac{s}{\sqrt{n}} \mathrm{t}_{\alpha / 2}(n-1)\right] .
$$

Låt oss jämföra dessa två fall: känd och okänd standardavvikelse $\sigma$. Om $\sigma=1.2$ och $n=9$ får vi $\sigma / \sqrt{n}=0.4$. Med $1-\alpha=0.95$ har vi $\alpha=0.05$, vilket ger ett konfidensintervall

$$
\begin{aligned}
I_{\mu} &=\left[\bar{x}-0.4 \lambda_{0.025}, \bar{x}+0.4 \lambda_{0.025}\right] \\
& \approx[\bar{x}-0.4 \cdot 1.96, \bar{x}+0.4 \cdot 1.96] \approx[\bar{x}-0.78, \bar{x}+0.78] .
\end{aligned}
$$

Antag nu att $\sigma$ är okänd och vi skattar den genom s. Vi antar vidare att vi har tur och $s$ landar exakt på den sanna standardavvikelsen 1.2. Detta ger då $s / \sqrt{n}=0.4$ som innan, men konfidensintervallet med $\alpha=0.05$ blir då

$$
\begin{aligned}
I_{\mu} &=\left[\bar{x}-0.4 \mathrm{t}_{0.025}(8), \bar{x}+0.4 \mathrm{t}_{0.025}(8)\right] \\
& \approx[\bar{x}-0.4 \cdot 2.31, \bar{x}+0.4 \cdot 2.31] \approx[\bar{x}-0.92, \bar{x}+0.92] .
\end{aligned}
$$

Konfidensintervallet blir då längre ( $1.84$ istället för $1.56)$ när vi skattar $\sigma$ jämfört med om $\sigma$ redan är känt. Anledningen är att vi "bakar in" osäkerheten hos vår skattning av $\sigma$ i skattningen av felet hos skattningen av $\mu$.

Detta motiverar delvis förfarandet i föregående föreläsning där vi ansatte att medelfelet $d\left(\theta^{\star}\right)$ hos en punktskattning kan fås genom att ersätta $\theta$ i uttrycket för $D\left[\theta^{\star}\right]$ med skattningen $\theta_{\text {obs }}^{\star}$. I fallet med normalfördelade stickprov kan vi göra detta argument rigoröst genom tillämpningen av t-fördelningen ovan.

Det är också värt att notera att $t(n-1)$ går mot $N(0,1)$ när $n \rightarrow+\infty$. (Vi ser detta genom att låta $n \rightarrow+\infty$ i täthetsfunktionen och använda faktumet att $\Gamma(n+$ $1 / 2) /(\sqrt{n} \Gamma(n)) \rightarrow 1$ då $n \rightarrow+\infty$.) För små $n$ är $t(n-1)$-fördelningen "bredare" än $\mathrm{N}(0,1)$ men närmar sig den senare för större $n$. Vi kan se detta som att för stora $n$ är skattningen $s$ av $\sigma$ så pass exakt att ersättandet av $\sigma$ med $s$ har en mycket liten effekt och $T=(\bar{X}-\mu) \sqrt{n} / s \approx(\bar{X}-\mu) \sqrt{n} / \sigma \sim N(0,1)$.

I fallet med okänt $\sigma$ kan det också vara av intresse att bestämma ett konfidensintervall för denna parameter. Detta görs enkelt med hjälp av en annan fördelning.

Exempel 4. (Skatta $\sigma$, okänt $\mu$ ) Vi antar igen att vi har oberoende $X_{1}, X_{2}, \ldots, X_{n}$ med fördelning $\mathrm{N}(\mu, \sigma$ ) och både $\mu$ och $\sigma$ är okända (fallet med okänd $\sigma$ och känd $\mu$ behandlas på liknande sätt, men antal frihetsgrader blir $n$ istället för $n-1$ ). Vi har då punktskattningen s med stickprovsvariabeln

$$
S=\sqrt{\frac{1}{n-1} \sum_{i=1}^{n}\left(X_{i}-\bar{X}\right)^{2}} .
$$

Om vi återigen $\operatorname{tar} X_{i}=\mu+\sigma Z_{i}$ för $Z_{i} \sim N(0,1)$ får vi

$$
S=\sigma \sqrt{\frac{1}{n-1} \sum_{i=1}^{n}\left(Z_{i}-\bar{Z}\right)^{2}} .
$$

En rimlig pivotvariabel vore då

$$
Y=\frac{S}{\sigma}
$$

eftersom denna fås genom kombination av de standardiserade stokastiska variablerna $Z_{1}, Z_{2}, \ldots, Z_{n}$. Vad har denna variabel för fördelning?

Man kan visa att kvadratsumman

$$
\sum_{i=1}^{n}\left(Z_{i}-\bar{Z}\right)^{2}
$$

har en så kallad $\chi^{2}$-fördelning med $n-1$ frihetsgrader, vilket betecknas $\chi^{2}(n-1)$. (Kvadratsumman av $n$ oberoende $\mathrm{N}(0,1)$-fördelade stokastiska variabler är fördelad enligt $\chi^{2}(n)$. Att vi har $n-1$ frihetsgrader har att göra med att vi subtraherar $\bar{Z}$ innan vi kvadrerar.) Denna fördelning har täthetsfunktionen

$$
f(x)=\frac{1}{2^{\frac{n-1}{2}} \Gamma\left(\frac{n-1}{2}\right)} x^{\frac{n-3}{2}} e^{-x / 2}
$$

och vi betecknar dess kvantiler med $\chi_{\alpha}^{2}(n-1)$, vilket ger

$$
P\left(\sum_{i=1}^{n}\left(Z_{i}-\bar{Z}\right)^{2}>\chi_{\alpha}^{2}(n-1)\right)=\alpha .
$$

(Notera att eftersom $\chi^{2}(n-1)$ inte är symmetrisk har inte att $\chi_{1-\alpha}^{2}(n-1)$ är lika med $\left.-\chi_{\alpha}^{2}(n-1)\right)$

![](https://cdn.mathpix.com/cropped/2022_11_17_e94059db2c7bd7807eb9g-08.jpg?height=401&width=742&top_left_y=591&top_left_x=648)

Eftersom

$$
Y=\sqrt{\frac{1}{n-1} \sum_{i=1}^{n}\left(Z_{i}-\bar{Z}\right)^{2}}
$$

och kvadratroten är en strikt monoton funktion ger detta

$$
\begin{array}{r}
P\left(\sum_{i=1}^{n}\left(Z_{i}-\bar{Z}\right)^{2}>\chi_{\alpha}^{2}(n-1)\right)=\alpha \\
P\left(\sqrt{\frac{1}{n-1} \sum_{i=1}^{n}\left(Z_{i}-\bar{Z}\right)^{2}}>\sqrt{\left.\frac{\chi_{\alpha}^{2}(n-1)}{n-1}\right)}=\alpha\right. \\
P\left(Y>\sqrt{\left.\frac{\chi_{\alpha}^{2}(n-1)}{n-1}\right)}=\alpha .\right.
\end{array}
$$

På samma sätt får vi

$$
P\left(Y<\sqrt{\frac{\chi_{1-\alpha}^{2}(n-1)}{n-1}}\right)=\alpha .
$$

Om vi ersätter $\alpha$ med $\alpha / 2$ har vi då

$$
P\left(Y<\sqrt{\frac{\chi_{1-\alpha / 2}^{2}(n-1)}{n-1}} \text { eller } \sqrt{\frac{\chi_{\alpha / 2}^{2}(n-1)}{n-1}}<Y\right)=\alpha / 2+\alpha / 2=\alpha .
$$

Sedan tar vi komplementet, vilket ger

$$
P\left(\sqrt{\frac{\chi_{1-\alpha / 2}^{2}(n-1)}{n-1}}<Y<\sqrt{\frac{\chi_{\alpha / 2}^{2}(n-1)}{n-1}}\right)=1-\alpha \text {. }
$$

Eftersom $Y=S / \sigma$ kan vi nu stuva om (samma princip som innan) och får

$$
P\left(S \sqrt{\frac{n-1}{\chi_{\alpha / 2}^{2}(n-1)}}<\sigma<S \sqrt{\frac{n-1}{\chi_{1-\alpha / 2}^{2}(n-1)}}\right)=\alpha \text {. }
$$

(Notera att vi måste vända på ändpunkterna ovan för att gå från $1 / \sigma$ till $\sigma$.) Utifrån utfallen $x_{1}, x_{2}, \ldots, x_{n}$ har vi alltså konfidensintervallet

$$
I_{\sigma}=\left[s \sqrt{\frac{n-1}{\chi_{\alpha / 2}^{2}(n-1)}}, s \sqrt{\frac{n-1}{\chi_{1-\alpha / 2}^{2}(n-1)}}\right]
$$

med konfidensgrad $1-\alpha$.

\section{Två normalfördelade stickprov}

En annan vanlig situation är att vi har två oberoende stickprov som vi vill jämföra. Det kan röra sig om skillnaden för någon viss egenskap mellan två kemiska föreningar. Eller vi kanske vill mäta skillnaden i effektivitet mellan två medicinska behandlingar för att bestämma om den ena är bättre än den andra. Vi skulle kunna jämföra punktskattningarna, men om de ligger tillräckligt nära varandra kan det vara svårt att säga om den ena verkligen är större än den andra.

I härledningarna nedan antar vi som innan att det rör sig om normalfördelade stickprov.

Exempel 5. (Skatta $\mu_{1}-\mu_{2}$, känd $\sigma_{1}, \sigma_{2}$ ) Vi har nu två oberoende stickprov: oberoende och $\mathrm{N}\left(\mu_{1}, \sigma_{1}\right)$-fördelade $X_{1}, X_{2}, \ldots, X_{n_{1}}$ samt oberoende och $\mathrm{N}\left(\mu_{2}, \sigma_{2}\right)$-fördelade $Y_{1}, Y_{2}, \ldots, Y_{n_{2}}$. Standardavvikelserna $\sigma_{1}$ och $\sigma_{2}$ antas kända och vi söker väntevärdesskillnaden $\mu_{1}-\mu_{2}$.

Utifrån utfallen $x_{1}, x_{2}, \ldots, x_{n_{1}}$ och $y_{1}, y_{2}, \ldots, y_{n_{2}}$ bildar vi punktskattningen

$$
\bar{x}-\bar{y}
$$

för $\mu_{1}-\mu_{2}$. Den motsvarande stickprovsvariabeln $\bar{X}-\bar{Y}$ har fördelningen $\mathrm{N}^{2} \mu_{1}-$ $\mu_{2}, \sqrt{\sigma_{1}^{2} / n_{1}+\sigma_{2}^{2} / n_{2}}$ ). Vi bildar då pivotvariabeln

$$
Z=\frac{(\bar{X}-\bar{Y})-\left(\mu_{1}-\mu_{2}\right)}{\sqrt{\sigma_{1}^{2} / n_{1}+\sigma_{2}^{2} / n_{2}}}
$$

och med samma resonemang som tidigare får vi alltså

$$
P\left(\bar{X}-\bar{Y}-\lambda_{\alpha / 2} \sqrt{\sigma_{1}^{2} / n_{1}+\sigma_{2}^{2} / n_{2}}<\mu_{1}-\mu_{2}<\bar{X}-\bar{Y}+\lambda_{\alpha / 2} \sqrt{\sigma_{1}^{2} / n_{1}+\sigma_{2}^{2} / n_{2}}\right)=1-\alpha,
$$

vilket ger konfidensintervallet

$$
I_{\mu_{1}-\mu_{2}}=\left[\bar{x}-\bar{y}-\lambda_{\alpha / 2} \sqrt{\sigma_{1}^{2} / n_{1}+\sigma_{2}^{2} / n_{2}}, \bar{x}-\bar{y}+\lambda_{\alpha / 2} \sqrt{\sigma_{1}^{2} / n_{1}+\sigma_{2}^{2} / n_{2}}\right]
$$

för $\mu_{1}-\mu_{2}$ med konfidensgrad $1-\alpha$. Som innan har vi också det intressanta fallet med okända standardavvikelser. Exempel 6. (Skatta $\mu_{1}-\mu_{2}$, okänd $\sigma_{1}=\sigma_{2}=\sigma$ ) För enkelhetens skull antar vi att de okända standardavvikelserna $\sigma_{1}$ och $\sigma_{2}$ är lika och betecknar de som $\sigma$. Detta uppstår, till exempel, om vi använder samma mätinstrument eller procedur för de båda stickproven, vilket leder till samma felstorlek i mätvärdena.

Vi har alltså två oberoende stickprov: $X_{1}, X_{2}, \ldots, X_{n_{1}}$ oberoende och $\mathrm{N}\left(\mu_{1}, \sigma\right)$-fördelade stokastiska variabler samt $Y_{1}, Y_{2}, \ldots, Y_{n_{2}}$ oberoende och $\mathrm{N}\left(\mu_{2}, \sigma\right)$-fördelade stokastiska variabler. Från dessa har vi utfallen $x_{1}, x_{2}, \ldots, x_{n_{1}}$ respektive $y_{1}, y_{2}, \ldots, y_{n_{2}}$. Vi skattar återigen $\mu_{1}-\mu_{2}$ med $\bar{x}-\bar{y}$. Den motsvarande stickprovsvariabeln $\bar{X}-\bar{Y}$ har fördelningen $\mathrm{N}\left(\mu_{1}-\mu_{2}, \sigma \sqrt{1 / n_{1}+1 / n_{2}}\right)$.

För att bilda en pivotvariabel behöver vi alltså skatta $\sigma$. Vi såg i föregående föreläsning att

$$
s=\sqrt{\frac{\sum_{i=1}^{n_{1}}\left(x_{i}-\bar{x}\right)^{2}+\sum_{j=1}^{n_{2}}\left(x_{i}-\bar{x}\right)^{2}}{\left(n_{1}-1\right)+\left(n_{2}-1\right)}}
$$

är en lämplig punktskattning för $\sigma$. Med hjälp av den motsvarande stickprovsvariabeln $S$ bildar vi alltså pivotvariabeln

$$
T=\frac{(\bar{X}-\bar{Y})-\left(\mu_{1}-\mu_{2}\right)}{S \sqrt{1 / n_{1}+1 / n_{2}}}
$$

Man kan visa att $T$ beror varken på $\mu_{1}, \mu_{2}$ eller $\sigma$ och har fördelningen $\mathrm{t}\left(\left(n_{1}-1\right)+\right.$ $\left.\left(n_{2}-1\right)\right)$

Om vi låter $f=\left(n_{1}-1\right)+\left(n_{2}-1\right)$ får vi enligt samma resonemang som för ett stickprov konfidensintervallet

$$
I_{\mu_{1}-\mu_{2}}=\left[\bar{x}-\bar{y}-t_{\alpha / 2}(f) s \sqrt{1 / n_{1}+1 / n_{2}}, \bar{x}-\bar{y}+t_{\alpha / 2}(f) s \sqrt{1 / n_{1}+1 / n_{2}}\right]
$$

för $\mu_{1}-\mu_{2}$ med konfidensgrad $1-\alpha$.

Vi avslutar med ett subtilt fall som liknar fallet ovan med två stickprov. I stället för att jämföra väntevärdena mellan två olika stickprov är vi intresserade av den systematiska skillnaden mellan par av mätningar. (Vi har alltså ett stickprov bestående av par istället för ett par av stickprov.)

Detta uppstår om vi vill utvärdera effekten av ett visst läkemedel på ett mätvärde hos olika patienter. Vi kan ta två stickprov, en kontrollgrupp och en interventionsgrupp, och jämföra medelvärdena. Detta är så klart möjligt, men problemet är att stickproven också kommer att innehålla den naturliga variationen mellan patienter (oberoende av läkemedlet) och därför ge stor spridning i väntevärdesskattningen. För att få ett snävt konfidensintervall krävs alltså stora stickprovsstorlekar. Om vi istället mäter varje patient två gånger, före och efter läkemedlet administreras, kan vi bli av med denna extra variation genom att jämföra mätvärdena i par och skatta den genomsnittliga skillnaden.

Exempel 7. (Stickprov i par) Vi har alltså ett stickprov $\left(X_{1}, Y_{1}\right),\left(X_{2}, Y_{2}\right), \ldots,\left(X_{n}, Y_{n}\right)$ bestående av oberoende par med fördelningar $X_{i} \sim \mathrm{N}\left(\mu_{i}, \sigma_{1}\right)$ samt $Y_{i} \sim \mathrm{N}\left(\mu_{i}+\Delta, \sigma_{2}\right)$ (dvs. stickprovet är inte likafördelat). Notera att väntevärdena $\mu_{i}$ tillåts variera genom stickprovet. Detta motsvarar (den icke intressanta) variationen som vi försöker eliminera.

Från detta stickprov har vi utfall $\left(x_{1}, y_{1}\right),\left(x_{2}, y_{2}\right), \ldots,\left(x_{n}, y_{n}\right)$ och vi vill skatta $\Delta$. Standardavvikelserna $\sigma_{1}$ och $\sigma_{2}$ kan vara kända eller okända.

Eftersom vi bara är intresserade av $\Delta$ bildar vi differenserna

$$
z_{1}=y_{1}-x_{1}, z_{2}=y_{2}-x_{2}, \ldots, z_{n}=y_{n}-x_{n},
$$

med de motsvarande stokastiska variablerna

$$
Z_{1}=Y_{1}-X_{1}, Z_{2}=Y_{2}-X_{2}, \ldots, Z_{n}=Y_{n}-X_{n} .
$$

Dessa har då alla fördelningen $\mathrm{N}(\Delta, \sigma)$ där $\sigma=\sqrt{\sigma_{1}^{2}+\sigma_{2}^{2}}$. Vi har nu återfått situationen med ett stickprov. Om $\sigma_{1}$ och $\sigma_{2}$ är kända har vi alltså konfidensintervallet

$$
I_{\Delta}=\left[\bar{z}-\lambda_{\alpha / 2} \sqrt{\sigma_{1}^{2}+\sigma_{2}^{2}} / \sqrt{n}, \bar{z}+\lambda_{\alpha / 2} \sqrt{\sigma_{1}^{2}+\sigma_{2}^{2}} / \sqrt{n}\right]
$$

för $\Delta$ med konfidensgrad $1-\alpha$. Om $\sigma_{1}$ och $\sigma_{2}$ är okända skattar vi $\sigma$ med

$$
s=\sqrt{\frac{1}{n-1} \sum_{i=1}^{n}\left(z_{i}-\bar{z}\right)^{2}}
$$

och får konfidensintervallet

$$
I_{\Delta}=\left[\bar{z}-\mathrm{t}_{\alpha / 2}(n-1) s / \sqrt{n}, \bar{z}+\mathrm{t}_{\alpha / 2}(n-1) s / \sqrt{n}\right]
$$

för $\Delta$ med konfidensgrad $1-\alpha$.

\section{Approximativ intervallskattning}

Hittills har vi betraktat normalfördelade stickprov, vilket ger punktskattningar vars stickprovsvariabler har bekanta fördelningar (normalfördelning, t-fördelning och $\chi^{2}$ fördelning). Normalfördelade stickprov är vanliga, men ofta förekommer stickprov med andra fördelningar. I dessa fall kan vi ibland tillämpa centrala gränsvärdessatsen om stickprovsstorleken $n$ är tillräckligt stor.

Antag att vi har en punktskattning $\theta_{\text {obs }}^{\star}$ med stickprovsvariabel $\theta^{\star}$. Vi antar vidare att den är väntevärdesriktig och har känd standardavvikelse $D$. Om denna är väntevärdesriktig och approximativt normalfördelad har vi att

$$
Z=\frac{\theta^{\star}-\theta}{D}
$$

är approximativt $N(0,1)$-fördelad. Ett approximativt konfidensintervall för $\theta$ med konfidensgrad $1-\alpha$ är då

$$
I_{\theta}=\left[\theta_{\text {obs }}^{\star}-\lambda_{\alpha / 2} D, \theta_{\text {obs }}^{\star}+\lambda_{\alpha / 2} D\right] .
$$

Om standardavvikelsen inte är känd skattar vi den med $d$. Detta ger ett mindre exakt konfidensintervall, men om $n$ är stort kan vi fortfarande bilda det approximativa konfidensintervallet

$$
I_{\theta}=\left[\theta_{\text {obs }}^{\star}-\lambda_{\alpha / 2} d, \theta_{\text {obs }}^{\star}+\lambda_{\alpha / 2} d\right],
$$

med konfidensgrad $1-\alpha$. Notera att i detta fall använder vi inte t-fördelningen eftersom vid $n$ stort så är det så liten skillnad mellan $t(n-1)$ och $N(0,1)$ att det inte har så stor effekt. Felet som introduceras av normalapproximationen via centrala gränsvärdessatsen är troligen större.

Exempel 8. Vi återgår till opinionsundersökningen med $X \sim \operatorname{Bin}(n, p)$ med $n=1000$ och utfallet $x=450$. Vår punktskattning $p_{\text {obs }}^{\star}=x / n$ har motsvarande stickprovsvariabel $p^{\star}=X / n$.

Vi har sett sedan innan att $X$ kan skrivar som en summa av $n$ oberoende Bernoullifördelade stokastiska variabler, vilket gör att vi kan tillämpa centrala gränsvärdessatsen för stora $n$, vilket ger att att $p^{*}=X / n$ approximativt har fördelningen $N(p, \sqrt{p(1-p) / n})$. Enligt härledningen ovan har vi då det approximativa konfidensintervallet

$$
I_{p}=\left[p_{\mathrm{obs}}^{\star}-\lambda_{\alpha / 2} d, p_{\mathrm{obs}}^{\star}+\lambda_{\alpha / 2} d\right],
$$

med konfidensgrad $1-\alpha$ där $d=\sqrt{p_{\text {obs }}^{\star}\left(1-p_{\text {obs }}^{\star}\right) / n}$. Med värdena $n=1000, x=450$ får vi $p_{\text {obs }}^{\star}=0.45$ och $d=0.016$, vilket ger, för $1-\alpha=0.99$,

$$
I_{p}=[0.45-2.58 \cdot 0.016,0.45+2.58 \cdot 0.016] \approx[0.41,0.49] .
$$

Med andra ord så täcker intervallet $[0.41,0.49]$ med sannolikhet $0.99$ det sanna värdet på p. Vi kan därför dra slutsatsen att det är högst osannolikt att andelen ja-svar i en folkomröstning skulle räcka för att rösta igenom frågan.