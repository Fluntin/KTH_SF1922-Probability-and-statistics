\title{
Föreläsning sex
}

\author{
Joakim Andén
}

14 november 2022

\section{Summa av stokastiska variabler}

Givet två oberoende stokastiska variabler $X$ och $Y$ kan vi betrakta fördelningen hos summan $Z=X+Y$. Låt oss först anta att $X$ och $Y$ är diskreta. I så fall har vi

$$
\begin{aligned}
p_{Z}(z) &=\mathrm{P}(Z=z)=\mathrm{P}(X+Y=z) \\
&=\sum_{x, y \geq 0: x+y=z} p_{X, Y}(x, y) \\
&=\sum_{x=0}^{z} p_{X, Y}(x, z-x) \\
&=\sum_{x=0}^{z} p_{X}(x) p_{Y}(z-x)
\end{aligned}
$$

eftersom händelsen $\{X+Y=z\}$ är den (disjunkta) unionen av alla händelser $\{X=$ $x, Y=y\}$ så att $x+y=z$.

![](https://cdn.mathpix.com/cropped/2022_11_15_3361e119fb2eb8e8c901g-01.jpg?height=558&width=708&top_left_y=1843&top_left_x=730)

Detta kallas för den diskreta faltningsformeln. (En faltning är en operation som förekommer i många olika sammanhang, från polynommultiplikation till modellering av hålrumsresonatorer inom akustiken eller diffraktionsmönster inom optiken.) Faltningsformeln är kommutativ och vi kan därför skriva den på två sätt:

$$
p_{X+Y}(z)=\sum_{x=0}^{z} p_{X}(x) p_{Y}(z-x)=\sum_{y=0}^{z} p_{X}(z-y) p_{Y}(y)
$$

Sats 1. Låt $X, Y$ vara oberoende stokastiska variabler med fördelning Bin $(n, p)$ respektive Bin $(m, p)$. Då har $Z=X+Y$ fördelningen $\operatorname{Bin}(n+m, p)$.

Bevis. Vi har

$$
p_{X}(x)=\left(\begin{array}{l}
n \\
x
\end{array}\right) p^{x}(1-p)^{n-x} \text { och } p_{Y}(y)=\left(\begin{array}{l}
m \\
y
\end{array}\right) p^{y}(1-p)^{m-y}
$$

Sannolikhetsfunktionen för $Z$ är då

$$
\begin{aligned}
p_{z}(z) &=\sum_{y=0}^{z} p_{X}(z-y) p_{Y}(y) \\
&=\sum_{y=0}^{z}\left(\begin{array}{c}
n \\
z-y
\end{array}\right) p^{z-y}(1-p)^{n-z+y} \cdot\left(\begin{array}{c}
m \\
y
\end{array}\right) p^{y}(1-p)^{m-y} \\
&=p^{z}(1-p)^{n+m-z} \sum_{i=0}^{k}\left(\begin{array}{c}
n \\
z-y
\end{array}\right)\left(\begin{array}{c}
m \\
y
\end{array}\right)
\end{aligned}
$$

Summan kan förenklas genom Vandermondes identitet

$$
\left(\begin{array}{c}
n+m \\
k
\end{array}\right)=\sum_{i=0}^{k}\left(\begin{array}{c}
n \\
k-i
\end{array}\right)\left(\begin{array}{c}
m \\
i
\end{array}\right) .
$$

vilket ger

$$
p_{z}(z)=\left(\begin{array}{c}
n+m \\
z
\end{array}\right) p^{z}(1-p)^{n+m-z},
$$

som skulle visas.

Vandermondes identitet visas genom att dra $k$ kulor från en samling med $n$ blåa och $m$ röda kulor. Vi kan ta k blåa kulor och noll röda kulor, vilket kan göras på $\left(\begin{array}{l}n \\ k\end{array}\right)\left(\begin{array}{c}m \\ 0\end{array}\right)$ olika sätt. Eller så kan vi ta $k-1$ blåa kulor och en röda kula, vilket görs på $\left(\begin{array}{c}n \\ k-1\end{array}\right)\left(\begin{array}{c}m \\ 1\end{array}\right)$ sätt. Eller så tar vi $k-2$ blåa kulor och två röda kulor, vilket ger $\left(\begin{array}{c}n \\ k-2\end{array}\right)\left(\begin{array}{c}m \\ 2\end{array}\right)$ sätt, och så vidare. Totalt sett har vi

$$
\sum_{i=0}^{k}\left(\begin{array}{c}
n \\
k-i
\end{array}\right)\left(\begin{array}{c}
m \\
i
\end{array}\right)
$$

sätt att välja $k$ kulor på detta vis. Men om vi struntar i färgen och bara tar $k$ kulor bland alla $n+m$ kulor kan detta göras på

$$
\left(\begin{array}{c}
n+m \\
k
\end{array}\right)
$$

sätt, varför identiteten följer.

Sats 2. Låt $X, Y$ vara oberoende stokastiska variabler med fördelningar Po $(\mu)$ respektive Po( $\nu)$. Då har $Z=X+Y$ fördelningen $\operatorname{Po}(\mu+\nu)$.

Bevis. Aterigen tillämpar vi faltningsformeln

$$
\begin{aligned}
p_{z}(z) &=\sum_{y=0}^{z} \frac{\mu^{z-y}}{(z-y) !} e^{-\mu} \cdot \frac{v^{y}}{y !} e^{-v}=\frac{e^{-\mu-\nu}}{z !} \sum_{y=0}^{z} \frac{z !}{(z-y) ! y !} \mu^{z-y} \nu^{y} \\
&=\frac{e^{-\mu-\nu}}{z !} \sum_{y=0}^{z}\left(\begin{array}{l}
z \\
y
\end{array}\right) \mu^{z-y} \nu^{y}=\frac{e^{-(\mu+\nu)}}{z !}(\mu+\nu)^{z},
\end{aligned}
$$

där vi i sista raden tillämpat binomialsatsen

$$
(x+y)^{n}=\sum_{k=0}^{n}\left(\begin{array}{l}
n \\
k
\end{array}\right) x^{k} y^{n-k} .
$$

För kontinuerliga stokastiska variabler $X$ och $Y$ har vi att summan $Z$ har fördelningsfunktionen

$$
\begin{aligned}
F_{Z}(z) &=P(Z \leq z)=\mathrm{P}(X+Y \leq z) \\
&=\iint_{\{(x, y): x+y \leq z\}} f_{X, Y}(x, y) d x d y=\iint_{\{(x, y): x+y \leq z\}} f_{X}(x) f_{Y}(y) d x d y .
\end{aligned}
$$

![](https://cdn.mathpix.com/cropped/2022_11_15_3361e119fb2eb8e8c901g-03.jpg?height=667&width=810&top_left_y=1781&top_left_x=663)

Integrationsområdet $\{(x, y): x+y \leq z\}$ kan skrivas om som $\{(x, y): y \leq z-x\}$, vilket ger

$$
\begin{aligned}
F_{Z}(z) &=\int_{x=-\infty}^{+\infty} \int_{y=-\infty}^{z-x} f_{X}(x) f_{Y}(y) d y d x \\
&=\int_{x=-\infty}^{+\infty} f_{X}(x) \int_{y=-\infty}^{z-x} f_{Y}(y) d y d x \\
&=\int_{x=-\infty}^{+\infty} f_{X}(x) F_{Y}(z-x) d x
\end{aligned}
$$

Om vi nu deriverar med avseende på z får vi täthetsfunktionen

$$
\begin{aligned}
f_{Z}(z) &=\frac{\partial}{\partial z} F_{Z}(z)=\frac{\partial}{\partial z} \int_{x=-\infty}^{+\infty} f_{X}(x) F_{Y}(z-x) d x \\
&=\int_{X=-\infty}^{+\infty} f_{X}(x) \frac{\partial}{\partial z} F_{Y}(z-x) d x \\
&=\int_{x=-\infty}^{+\infty} f_{X}(x) f_{Y}(z-x) d x,
\end{aligned}
$$

vilket kallas den kontinuerliga faltningsformeln. Som innan är denna relation kommutativ och vi har således

$$
f_{X+Y}(z)=\int_{X=-\infty}^{+\infty} f_{X}(x) f_{Y}(z-x) d x=\int_{y=-\infty}^{+\infty} f_{X}(z-y) f_{Y}(y) d y
$$

Med hjälp av faltningsformlerna kan vi nu visa ett par användbara resultat gällande summor av vissa oberoende och identiskt fördelade stokastiska variabler.

Sats 3. Låt $X_{1}, X_{2}, \ldots, X_{n}$ vara oberoende stokastiska variabler fördelade enligt $\operatorname{Exp}(\lambda)$. Vi har då att $X_{1}+X_{2}+\ldots+X_{n} \sim \operatorname{Gamma}(n, \lambda)$.

Bevis. Vi visar detta med induktion på $n$. Eftersom Gamma(1, $\lambda)$ är detsamma som $\operatorname{Exp}(\lambda)$ vet vi att satsen gäller för $n=1$.

Antag nu att den gäller för $n-1$. Vi har då att $Y=X_{1}+X_{2}+\ldots+X_{n-1} \sim \operatorname{Gamma}(n-$ $1, \lambda)$, dvs.

$$
f_{Y}(y)=\frac{\lambda^{n-1}}{\Gamma(n-1)} y^{n-2} e^{-\lambda y} \quad \text { för } y \geq 0 \text {. }
$$

Om $Z=X_{1}+X_{2}+\ldots+X_{n}=Y+X_{n}$ får vi då, enligt faltningsformeln,

$$
f_{Z}(z)=\int_{y=-\infty}^{+\infty} f_{Y}(y) f_{X_{n}}(z-y) d y=\int_{y=0}^{z} f_{Y}(y) f_{X_{n}}(z-y) d y
$$

där vi har kunnat ersätta integrationsgränserna med 0 och $z$ eftersom $f_{Y}(y)=0$ för $y<0$ och $f_{X_{n}}(z-y)=0$ för $y>z$. Vi sätter in formlerna för täthetsfunktionerna $f_{Y}(y)$ och $f_{X_{n}}(x)$, vilket ger

$$
\begin{aligned}
f_{Z}(z) &=\int_{y=0}^{z} f_{Y}(y) f_{X_{n}}(z-y) d y \\
&=\int_{y=0}^{z} \frac{\lambda^{n-1}}{\Gamma(n-1)} y^{n-2} e^{-\lambda y} \cdot \lambda e^{-\lambda(z-y)} d y \\
&=\frac{\lambda^{n}}{\Gamma(n-1)} e^{-\lambda z} \int_{y=0}^{z} y^{n-2} d y \\
&=\frac{\lambda^{n}}{\Gamma(n-1)} e^{-\lambda z} \frac{z^{n-1}}{n-1}=\frac{\lambda^{n}}{\Gamma(n)} z^{n-1} e^{-\lambda z}
\end{aligned}
$$

eftersom $\Gamma(n)=(n-1) \Gamma(n-1)$

\section{Betingade fördelningar}

Om vi har två stokastiska variabler (dvs. en tvådimensionell stokastisk variabel) och vi vet att en av dem har ett visst utfall, hur påverkar det fördelningen hos den andra? Vi stötte på en liknande fråga tidigare när det gäller sannolikheten för olika händelser. Där definierade vi den betingade sannolikheten $\mathrm{P}(A \mid B)$ att $A$ inträffar givet att $B$ redan har inträffat.

För att översätta denna definition till stokastiska variabler låter vi $X$ och $Y$ vara två diskreta stokastiska variabler och betraktar händelserna $\{X=x\}$ samt $\{Y=y\}$. Vi bildar då den betingade sannolikheten

$$
\mathrm{P}(X=x \mid Y=y)=\frac{\mathrm{P}(X=x, Y=y)}{\mathrm{P}(Y=y)}=\frac{p_{X, Y}(x, y)}{p_{Y}(y)},
$$

där vi har satt in definitionen på sannolikhetsfunktionerna $p_{X, Y}(j, k)$ samt $p_{Y}(y)$. Detta ger då en naturlig definition på den betingade sannolikhetsfunktionen för $X$ givet $Y=y$ :

$$
p_{X \mid Y=y}(x)=\frac{p_{X, Y}(x, y)}{p_{Y}(y)},
$$

Precis som de betingade sannolikheter $\mathrm{P}(A \mid B)$ vi såg innan har dessa betingade sannolikhetsfunktioner ett antal användbara egenskaper:

$$
\begin{aligned}
p_{X, Y}(x, y) &=p_{X \mid Y=y}(x) p_{Y}(y) \\
p_{X}(x) &=\sum_{y=0}^{+\infty} p_{X \mid Y=y}(x) p_{Y}(y) \\
p_{X \mid Y=y}(x) &=\frac{p_{Y \mid X=y}(x) p_{X}(x)}{p_{Y}(y)}
\end{aligned}
$$

(lagen om total sannolikhet)

(Bayes sats)

Utöver detta beter sig de betingade sannolikhetsfunktionerna precis som vanliga sannolikhetsfunktioner så länge man håller betingningen $Y=y$ fix. Med andra ord har vi fördelningar för funktioner $g(X)$ av betingade stokastiska variabler $X$ givet $Y=y$. Vi har den betingade diskreta faltningsformeln för summor av betingade stokastiska variabler, och så vidare.

Exempel 4. Låt $(X, Y)$ vara två diskreta stokastiska variabler med simultan sannolikhetsfunktion vars värden ges av

$$
\begin{array}{lll}
p_{X, Y}(1,1)=2 / 18 & p_{X, Y}(1,2)=1 / 18 & p_{X, Y}(1,3)=3 / 18 \\
p_{X, Y}(2,1)=1 / 18 & p_{X, Y}(2,2)=4 / 18 & p_{X, Y}(2,3)=1 / 18 \\
p_{X, Y}(3,1)=0 & p_{X, Y}(3,2)=1 / 18 & p_{X, Y}(3,3)=5 / 18
\end{array}
$$

och som är noll för andra värden på $(x, y)$. Vi kan då beräkna marginalfördelningen för $X$ :

$$
\begin{aligned}
&p_{X}(1)=p_{X, Y}(1,1)+p_{X, Y}(1,2)+p_{X, Y}(1,3)=6 / 18=1 / 3 \\
&p_{X}(2)=\cdots=1 / 3 \\
&p_{X}(3)=\cdots=1 / 3 .
\end{aligned}
$$

Med andra ord är $X$ likformigt fördelad över $\{1,2,3\}$. Om vi betingar med avseende på $Y=1$ får vi en annan fördelning. Först har vi att

$$
p_{Y}(1)=p_{X, Y}(1,1)+p_{X, Y}(2,1)+p_{X, Y}(3,1)=1 / 6,
$$

vilket ger

$$
\begin{aligned}
&p_{X \mid Y=1}(1)=(2 / 18) /(1 / 6)=2 / 3 \\
&p_{X \mid Y=1}(2)=(1 / 18) /(1 / 6)=1 / 3 \\
&p_{X \mid Y=1}(3)=0 /(1 / 6)=0 .
\end{aligned}
$$

Så om vi bara observerar $X$ (oavsett värde på $Y$ ) får vi en likformig fördelning, medan om vi redan observerat $Y=1$ så har vi större sannolikhet att få $X=1$ och mindre sannolikhet att få $X=3$. Vad händer om vi istället hade observerat $Y=3$ ?

För kontinuerliga stokastiska variabler blir det mer komplicerat eftersom den betingande händelsen $\{Y=y\}$ har sannolikhet noll (och därför också sannolikheten för händelsen $\{X \leq x, Y=y\}$ ). Sannolikheten $\mathrm{P}(X \leq x \mid Y=y)$ är därför inte väldefinierad. En utväg är att konstatera att vi egentligen aldrig har $Y=y$ för en kontinuerlig variabel - detta skulle motsvara att vi känner till $Y:$ : utfall till oändlig precision, vilket inte är möjligt. Om något så vet vi att $Y=y$ med en viss precision, till exempel att $Y \leq[y, y+\Delta y]$ för något $\Delta y>0$.

Vi kan då skriva

$$
\begin{aligned}
\mathrm{P}(X \leq x \mid Y \in[y, y+\Delta y]) &=\frac{\mathrm{P}(X \leq x, Y \in[y, y+\Delta y])}{\mathrm{P}(Y \in[y, y+\Delta y])} \\
&=\frac{\int_{u=-\infty}^{x} \int_{v=y}^{y+\Delta y} f_{X, Y}(u, v) d v d u}{\int_{v=y}^{y+\Delta y} f_{Y}(v) d v} .
\end{aligned}
$$

Om vi använder medelvärdessatsen får vi att det finns två $\theta_{1}, \theta_{2} \in[0,1]$ så att integralerna med avseende på $v$ kan skrivas om

$$
\begin{gathered}
\int_{v=y}^{y+\Delta y} f_{X, Y}(u, v) d v=f_{X, Y}\left(u, y+\theta_{1} \Delta y\right) \Delta y \\
\int_{v=y}^{y+\Delta y} f_{Y}(v) d v=f_{Y}\left(y+\theta_{2} \Delta y\right) \Delta y .
\end{gathered}
$$

Vi sätter nu in dessa i sannolikhetsuttrycket ovan och får

$$
\begin{aligned}
P(X \leq x \mid Y \in[y, y+\Delta y]) &=\frac{\int_{u=-\infty}^{x} f_{X, Y}\left(u, y+\theta_{1} \Delta y\right) \Delta y d u}{f_{Y}\left(y+\theta_{2} \Delta y\right) \Delta y} \\
&=\frac{\int_{u=-\infty}^{x} f_{X, Y}\left(u, y+\theta_{1} \Delta y\right) d u}{f_{Y}\left(y+\theta_{2} \Delta y\right)} .
\end{aligned}
$$

Ett av problemen är nu löst: sannolikheterna i täljaren och nämnaren är både väldigt små när $\Delta y$ är litet, men båda är proportionerliga med $\Delta y$ så deras proportion är nollskilld.

Vi kan nu låta $\Delta y \rightarrow 0$ och får då

$$
\lim _{\Delta y \rightarrow 0} P(X \leq x \mid Y \in[y, y+\Delta y])=\frac{\int_{u=-\infty}^{x} f_{X, Y}(u, y) d u}{f_{Y}(y)},
$$

vilket är en sorts fördelningsfunktion för $X$ givet " $Y=y^{\prime \prime}$. Vi kan derivera denna med avseende på $x$ för att få en tillhörande täthetsfunktion

$$
\frac{\partial}{\partial x} \frac{\int_{u=-\infty}^{x} f_{X, Y}(u, y) d u}{f_{Y}(y)}=\frac{f_{X, Y}(x, y)}{f_{Y}(y)}
$$

enligt integralkalkylens fundamentalsats. Detta ger då en naturlig definition för den betingade täthetsfunktionen för $X$ givet $Y=y$,

$$
f_{X \mid Y=y}(x)=\frac{f_{X, Y}(x, y)}{f_{Y}(y)},
$$

som också överstämmer på formen med den betingade sannolikhetsfunktionen. (Tyvärr är inte denna definition helt oproblematisk. Gränsvärdet som togs ovan kan ibland göras på flera sätt, vilket leder till olika betingade täthetsfunktioner. Detta kallas Borel-Kolmogorovs paradox. I de flesta fall, och de fall som uppstår i kursen, kommer definitionen ovan dock inte ställa till några problem.) 
![](https://cdn.mathpix.com/cropped/2022_11_15_3361e119fb2eb8e8c901g-08.jpg?height=858&width=1282&top_left_y=286&top_left_x=411)

Som i det diskreta fallet har vi ett antal användbara egenskaper hos denna betingade täthetsfunktion:

$$
\begin{aligned}
f_{X, Y}(x, y) &=f_{X \mid Y=y}(x) f_{Y}(Y) \\
f_{X}(x) &=\int_{y=-\infty}^{+\infty} f_{X \mid Y=y}(x) f_{Y}(y) d y \quad \text { (Iagen om total sannolikhet) } \\
f_{X \mid Y=y}(x) &=\frac{f_{Y \mid X=x}(y) f_{X}(x)}{f_{Y}(y)} \\
\text { (Bayes sats) }
\end{aligned}
$$

På samma sätt beter sig de betingade täthetsfunktionerna som vanliga (obetingade) täthetsfunktioner, givet att $Y=y$ hålls fixt. Vi har betingade fördelningsfunktioner $F_{X \mid Y=y}(X)$ som kan användas till att beskriva fördelningen hos betingade maximum $F_{\max }\left(X_{1}, X_{2}\right) \mid Y=y(X)=F_{X_{1} \mid Y=y}(X) F_{X_{2} \mid Y=y}(X)$. Vi kan också betrakta betingade summor av stokastiska variabler, och så vidare.

Exempel 5. Låt oss anta att $(X, Y)$ är slumpmässiga punkter på enhetsskivan $\{(x, y)$ : $\left.x^{2}+y^{2} \leq 1\right\} \subset \mathbb{R}^{2}$. Med andra ord har vi täthetsfunktionen

$$
f_{X, Y}(x, y)= \begin{cases}\frac{1}{\pi}, & x^{2}+y^{2} \leq 1 \\ 0, & \text { annars }\end{cases}
$$

eftersom enhetsskivan har area $\pi$. Notera att vi kan skriva definitionen på enhetsskivan som

$$
\left\{(x, y):-1 \leq y \leq 1,-\sqrt{1-y^{2}} \leq x \leq \sqrt{1-y^{2}}\right\} .
$$

Marginalfördelningen $f_{Y}(y)$ med avseende på $Y$ blir nu då

$$
f_{Y}(y)=\int_{\mathbb{R}} f_{X, Y}(x, y) d x=\int_{-\sqrt{1-y^{2}}}^{\sqrt{1-y^{2}}} \frac{1}{\pi} d x=\frac{2 \sqrt{1-y^{2}}}{\pi},
$$

för $-1 \leq y \leq 1$ och noll annars eftersom värden på y utanför intervallet $[-1,1]$ ger att den simultana täthetsfunktionen $f_{X, Y}(x, y)$ blir noll. Alltså har y större sannolikhet att vara nära noll än nära ett eller minus ett. Detta är naturligt då enhetsskivan är "tjockare" (sett från y-axeln) nära noll. På samma sätt fås också

$$
f_{X}(x)=\frac{2 \sqrt{1-x^{2}}}{\pi}
$$

för $-1 \leq x \leq 1$ och noll annars.

Den betingade täthetsfunktionen för $X$ givet $Y=y$ är då

$$
f_{X \mid Y=y}(x)=\frac{f_{X, Y}(x, y)}{f_{Y}(y)}=\frac{\frac{1}{\pi}}{\frac{2 \sqrt{1-y^{2}}}{\pi}}=\frac{1}{2 \sqrt{1-y^{2}}},
$$

för $-\sqrt{1-y^{2}} \leq x \leq \sqrt{1-y^{2}}$ och noll annars (då täljaren är noll för $x$ utanför detta intervall). Detta är den likformiga fördelningen över intervallet $\left[-\sqrt{1-y^{2}}, \sqrt{1-y^{2}}\right]$.
![](https://cdn.mathpix.com/cropped/2022_11_15_3361e119fb2eb8e8c901g-09.jpg?height=388&width=1272&top_left_y=1443&top_left_x=426)

Eftersom vi började med en (tvådimensionell) likformig fördelning så är det naturligt att den betingade fördelningen också är likformig, eftersom vi endast håller den ena variabeln (y) fix medan vi betraktar den andra $(x)$, som då fortsätter att vara likformigt fördelad.

Notera att den betingade täthetsfunktionen för $X$ givet $Y=y$ skiljer sig markant från den marginella täthetsfunktionen för $X$. Den senare avser tätheten för $X$ oavsett värdet på $Y$ medan den tidigare avser tätheten för $X$ givet ett visst värde på $Y$.

Vi har nu också en alternativ definition för oberoende stokastiska variabler. De stokastiska variablerna $X$ och $Y$ är oberoende om och endast om

$$
\begin{aligned}
&p_{X \mid Y=y}(x)=p_{X}(x) \\
&f_{X \mid Y=y}(x)=f_{X}(x) .
\end{aligned}
$$

(diskret)

(kontinuerlig) 

\section{Väntevärde}

Antag att vi har en stokastisk variabel $X$. Hur $X$ beter sig beskrivs som bekant av dess fördelning, antingen genom en sannolikhetsfunktion eller en täthetsfunktion. Ibland kan det vara användbart att beskriva $X$ med endast ett värde som sammanfattar dess beteende. Till exempel, kan det vara användbart att veta vad $X$ tar för värde "i genomsnitt". Med andra ord, om vi repeterar samma slumpförsök, skriver ner de olika utfallen hos $X$, vad blir medelvärdet?

Exempel 6. Låt oss anta att vid ett tärningskast får vi följande vinster:

\begin{tabular}{c|cccccc} 
Tärning & 1 & 2 & 3 & 4 & 5 & 6 \\
\hline Vinst & $1 k r$ & $2 k r$ & $2 k r$ & $4 k r$ & $4 k r$ & $4 k r$
\end{tabular}

Vad är medelvinsten? Alternativt, vad är ett rimligt pris för att delta i spelet?

Låt $X$ beteckna vinsten vid ett tärningskast. Detta är en diskret stokastisk variabel som tar värden i $\{1,2,4\}$ och har sannolikhetsfunktion

$$
p_{x}(x)= \begin{cases}1 / 6, & x=1 \\ 1 / 3, & x=2 \\ 1 / 2, & x=4 \\ 0, & \text { annars }\end{cases}
$$

Enligt frekvenstolkningen av sannolikheten förväntar vi oss att om vi slår ett stort antal tärningskast så kommer vi att vinna en krona 1/6 av gångerna, två kronor 1/3 av gångerna och fyra kronor $1 / 2$ av gångerna. I medel vinner vi då

$$
\frac{1}{6} \cdot 1+\frac{1}{3} \cdot 2+\frac{1}{2} \cdot 4=\frac{17}{6}
$$

kronor. Detta är då också ett rimligt pris för att delta i spelet eftersom man då (i genomsnitt) vinner tillbaka lika mycket som man betalat in vid ett stort antal försök. (Troligen vill nog spelarrangören också generera en liten vinst, så hen kanske sätter priset lite högre.)

För en diskret stokastisk variabel $X$ definierar vi då dess väntevärde som

$$
\mathrm{E}[X]=\sum_{x=0}^{+\infty} x p_{X}(x) .
$$

Detta betecknas också $\mu$ eller $\mu_{x}$. Vissa föredrar också att skriva E som $\mathbb{E}$ för att inte förväxla denna med en stokastisk variabel. (Bokstaven E kommer från engelskans "expected value" eller "expectation".)

Exempel 7. Antag att $X \sim \operatorname{Bin}(n, p)$. I detta fall har vi

$$
p_{x}(x)=\left(\begin{array}{l}
n \\
x
\end{array}\right) p^{x}(1-p)^{n-x}
$$

för $x=0,1, \ldots, n$ och noll annars. Väntevärdet blir då

$$
\begin{aligned}
& \mathrm{E}[X]=\sum_{x=0}^{n} x \cdot\left(\begin{array}{l}n \\x\end{array}\right) p^{x}(1-p)^{n-x} \\
& =\sum_{x=1}^{n} x \cdot\left(\begin{array}{l}n \\x\end{array}\right) p^{x}(1-p)^{n-x} \\
& \text { (termen } x=0 \text { utgår) } \\
& =\sum_{x=1}^{n} x \frac{n !}{(n-x) ! x !} p^{x}(1-p)^{n-x} \\
& \text { (utveckling av } \left.\left(\begin{array}{l}n \\x\end{array}\right)\right) \\
& =\sum_{x=1}^{n} n p \frac{(n-1) !}{(n-x) !(x-1) !} p^{x-1}(1-p)^{n-x} \\
& \text { (förkorta } x, \text { faktorera ut } n \text { och } p \text { ) } \\
& =n p \sum_{k=0}^{n-1} \frac{(n-1) !}{(n-1-k) ! k !} p^{k}(1-p)^{n-1-k} \\
& (\text { sätt } k=x-1) \\
& =n p(p+(1-p))^{n-1}=n p \text {. }
\end{aligned}
$$

(binomialsatsen)

Exempel 8. Låt $X \sim \operatorname{Po}(\mu)$. Då har vi

$$
p_{x}(x)=\frac{\mu^{x}}{x !} e^{-\mu}
$$

för $x=0,1,2, \ldots$ Väntevärdet ges av

$$
\begin{aligned}
\mathrm{E}[X] &=\sum_{x=0}^{+\infty} x \cdot \frac{\mu^{x}}{x !} e^{-\mu}=\sum_{x=1}^{+\infty} x \cdot \frac{\mu^{x}}{x !} e^{-\mu} \\
&=\sum_{x=1}^{+\infty} \mu \cdot \frac{\mu^{x-1}}{(x-1) !} e^{-\mu} \\
&=\mu \sum_{k=0}^{+\infty} \frac{\mu^{k}}{k !} e^{-\mu} \\
&=\mu .
\end{aligned}
$$

(termen $x=0$ utgår)

(förkorta $x$, faktorera ut $\mu$ )

$($ sätt $k=x-1)$

(sannolikhetsfunktionen summerar till ett)

För kontinuerliga variabler ersätter vi summan med en integral och får

$$
\mathrm{E}[X]=\int_{-\infty}^{+\infty} x f_{X}(x) d x
$$

I båda fallen kan vi tolka $E[X]$ som "tyngdpunkten" hos massfördelningen som beskrivs av $p_{X}(x)$ eller $f_{X}(x)$. Väntevärdet brukar därför kallas för ett lägesmått för den stokastiska variabeln $X$ - den beskriver var $X$ befinner sig, i genomsnitt. Andra användbara lägesmått är medianen $\chi_{0.50}$ (dvs. 50\%-kvantilen) som delar fördelningen i två lika stora (lika sannolika) delar samt typvärdet, vilket är det värde på $x$ som maximerar täthetsfunktionen (eller sannolikhetsfunktionen). En nackdel med dessa alternativ är att de inte alltid är entydiga. Exempel 9. Låt $X \sim \operatorname{Exp}(\lambda)$. Då har vi

$$
f_{x}(x)=\left\{\begin{array}{cc}
\lambda e^{-\lambda x}, & x \geq 0 \\
0, & \text { annars }
\end{array}\right.
$$

Detta ger då väntevärdet

$$
\begin{aligned}
\mathrm{E}[X] &=\int_{x=-\infty}^{+\infty} x f_{x}(x)=\int_{x=0}^{+\infty} x \lambda e^{-\lambda x} d x=\left[\frac{x \lambda e^{-\lambda x}}{-\lambda}\right]_{x=0}^{+\infty}-\frac{\lambda}{-\lambda} \int_{x=0}^{+\infty} e^{-\lambda x} d x \\
&=0+\int_{x=0}^{+\infty} e^{-\lambda x} d x=\frac{1}{\lambda}
\end{aligned}
$$

Exempel 10. Antag att $X$ har en cauchyfördelning med täthetsfunktion

$$
f_{X}(x)=\frac{1}{\pi} \frac{1}{1+x^{2}} .
$$

En sådan fördelning uppstår, till exempel, om vi delar två oberoende normalfördelade variabler med varandra. Vi ser att integralen av $f_{X}(x)$ är lika med ett genom substitutionen $x=\tan \theta$. Täthetsfunktionen är symmetrisk runt noll, så det skulle vara ett rimligt "genomsnitt".

Väntevärdet får vi till

$$
\mathrm{E}[X]=\int_{x=-\infty}^{+\infty} x \cdot \frac{1}{\pi} \frac{1}{1+x^{2}} d x=\frac{1}{\pi} \int_{x=-\infty}^{0} \frac{x}{1+x^{2}} d x+\frac{1}{\pi} \int_{x=0}^{+\infty} \frac{x}{1+x^{2}} d x .
$$

Båda integralerna divergerar här (den första mot $-\infty$ och den andra mot $+\infty$ ) så väntevärdet är inte väldefinierat. (Däremot är väntevärdena $\mathrm{E}\left[|X|^{p}\right]$ för $p<1$ väldefinierade.)

Vad betyder detta? Jo, om vi drar olika värden på $X$ så kommer deras fördelning att vara centrerad runt noll, precis som täthetsfunktionen ovan beskriver, men deras medelvärde kommer inte konvergera mot noll. Chansen att vi drar ett mycket stort (positivt eller negativt) värde på $X$ är helt enkelt för stor för att dessa ska ta ut varandra i längden.

Om vi istället använder andra mått för att sammanfatta "genomsnittet" hos X, som medianen eller typvärdet, får vi det "naturliga" svaret noll.

Vi kan också beräkna väntevärden hos funktioner $g(X)$ av en stokastisk variabel $X$. Eftersom $Y=g(X)$ också är en stokastisk variabel kan vi beräkna dess fördelning och sedan beräkna väntevärdet. Det visar sig att detta inte är nödvändigt. Rent konkret har vi, för en diskret stokastisk variabel $X$,

$$
\begin{aligned}
\mathrm{E}[g(X)]=\mathrm{E}[Y] &=\sum_{y=0}^{+\infty} y p_{Y}(y)=\sum_{y=0}^{+\infty} y \mathrm{P}(Y=y) \\
&=\sum_{y=0}^{+\infty} y \mathrm{P}(g(X)=y)=\sum_{y=0}^{+\infty} y \sum_{x: g(x)=y} \mathrm{P}(X=x) \\
&=\sum_{y=0}^{+\infty} y \sum_{y=g(x)=y} p_{x}(x)=\sum_{y=0}^{+\infty} \sum_{x: g(x)=y} g(x) p_{x}(x) \\
&=\sum_{x=0}^{+\infty} g(x) p_{x}(x),
\end{aligned}
$$

där den sista raden fås eftersom $\{x: g(x)=0\},\{x: g(x)=1\}, \ldots$ bildar en partition $\operatorname{av} \mathbb{N}_{0}$.

På liknande sätt har vi för kontinuerliga stokastiska variabler

$$
\mathrm{E}[g(X)]=\int_{x=-\infty}^{+\infty} g(x) f_{x}(x) d x .
$$

Vi kan också utvidga definitionen så att den innefattar funktioner av två (eller flera) stokastiska variabler:

$$
\mathrm{E}[g(X, Y)]=\left\{\begin{array}{lr}
\sum_{x, y=0}^{+\infty} g(x, y) p_{X, Y}(x, y) & \text { (diskreta } X, Y) \\
\int_{x, y=-\infty}^{+\infty} g(x, y) f_{X, Y}(x, y) & \text { (kontinuerliga } X, Y)
\end{array}\right.
$$

En mycket användbar egenskap hos väntevärdet är dess linjäritet, dvs. att

$$
\mathrm{E}[a X+b]=a \mathrm{E}[X]+b,
$$

vilket följer från faktumet att summor och integraler är linjära samt att $\sum_{x=0}^{+\infty} p_{x}(x)=$ 1 och $\iint_{X=-\infty}^{+\infty} f_{X}(X) d x=1$. Med två variabler $X, Y$ har vi på liknande sätt att $E[a X+$ $b Y+c]$ är lika med

$$
\begin{aligned}
&\iint_{X, y=-\infty}^{+\infty}(a x+b y+c) f_{X, Y}(x, y) d x d y \\
&\quad=\iint_{X, y=-\infty}^{+\infty} a x f_{X, Y}(x, y) d x d y+\iint_{X, y=-\infty}^{+\infty} b y f_{X, Y}(x, y) d x d y+\iint_{X, y=-\infty}^{+\infty} c f_{X, Y}(x, y) d x d y \\
&\quad=a \int_{X=-\infty}^{+\infty} x \int_{y=-\infty}^{+\infty} f_{X, Y}(x, y) d y d x+b \int_{y=-\infty}^{+\infty} y \int_{X=-\infty}^{+\infty} f_{X, Y}(x, y) d x d y+c \\
&=a \int_{X=-\infty}^{+\infty} x f_{X}(x) d x+b \int_{y=-\infty}^{+\infty} y f_{Y}(y) d y+c=a \mathrm{E}[X]+b \mathrm{E}[Y]+c
\end{aligned}
$$

Denna identitet gäller också i det diskreta fallet.

Den kan till exempel användas för en alternativ härledning $\mathrm{E}[X]=n p$ för $X \sim$ $\operatorname{Bin}(n, p)$. Vi noterar först att $X$ kan skrivas som en summa av $n$ oberoende stokastiska variabler, var och en fördelad enligt $\operatorname{Ber}(p)$. Dessa har var och en väntevärdet $1 \cdot p+0 \cdot(1-p)=p$, vilket ger att väntevärdet för $X$ är summan av dessa $n$ väntevärden $p$, dvs. np.

Om $X$ och $Y$ är oberoende har vi att (i det kontinuerliga fallet)

$$
\begin{aligned}
\mathrm{E}[X Y]=& \iint_{X, y=-\infty}^{+\infty} x y f_{X, Y}(x, y) d x d y \\
&=\int_{X=-\infty}^{+\infty} \int_{y=-\infty}^{+\infty} x y f_{X}(X) f_{Y}(Y) d y d x \\
&=\int_{X=-\infty}^{+\infty} x f_{X}(x) \int_{y=-\infty}^{+\infty} y f_{Y}(Y) d y d x \\
&=\int_{X=-\infty}^{+\infty} x f_{X}(x) \mathrm{E}[Y] d x=\mathrm{E}[X] \mathrm{E}[Y]
\end{aligned}
$$

Båda dessa identiteter gäller också för diskreta variabler och kan generaliseras till fler än två variabler. Till exempel, om $X_{1}, X_{2}, \ldots, X_{n}$ är oberoende stokastiska variabler fås

$$
\mathrm{E}\left[X_{1} X_{2} \cdots X_{n}\right]=\mathrm{E}\left[X_{1}\right] \mathrm{E}\left[X_{2}\right] \cdots \mathrm{E}\left[X_{n}\right]
$$

\section{Varians}

Som vi såg ovan är väntevärdet ett lägesmått för den stokastiska variabeln $X$. Ett annat mått som sammanfattar $X$ är ett spridningsmått. Om väntevärdet indikerar att $X$ befinner sig runt $\mu=E[X]$ så bestämmer ett spridningsmått hur koncentrerad fördelningen är runt $\mu$.
![](https://cdn.mathpix.com/cropped/2022_11_15_3361e119fb2eb8e8c901g-14.jpg?height=376&width=1260&top_left_y=1861&top_left_x=470)

Ett tillvägagångssätt är att betrakta $|X-\mu|$, den stokastiska variabeln som mäter avståndet mellan $X$ och $\mu$. Dess väntevärde $E[|X-\mu|]$ kallas den genomsnittliga avvikelsen och ger ett vettigt spridningsmått. Vi kan också betrakta medianen av $|X-\mu|$ eller byta ut $\mu$ mot $\chi_{0.50}$. En annan variant är interkvartilavståndet $\chi_{0.25}-$ $x_{0.75}$, dvs. skillnaden mellan $25 \%-k v a n t i l e n$ och $75 \%-k v a n t i l e n$. Alla dessa varianter ger olika spridningsmått. Tyvärr kan dessa vara svåra att beräkna och har inte alltid de egenskaper vi söker.

Istället betraktar vi väntevärdet hos kvadraten $|X-\mu|^{2}$ av avståndet mellan $X$ och $\mu$. Detta kallas variansen och skrivs

$$
\mathrm{V}[X]=\mathrm{E}\left[|X-\mu|^{2}\right]=\mathrm{E}\left[(X-\mu)^{2}\right] .
$$

Ett problem med variansen är att den inte behåller samma enheter som $X$ och $\mu$. Därför tar vi ofta kvadratroten av variansen vilket ger standardavvikelsen

$$
\mathrm{D}[X]=\sqrt{\mathrm{V}[X]}=\sqrt{\mathrm{E}\left[(X-\mu)^{2}\right]} .
$$

Notera att detta inte är samma sak som den genomsnittliga avvikelsen $\mathrm{E}[|X-\mu|]$. (Vi har faktiskt alltid att $\mathrm{E}[|X-\mu|] \leq \sqrt{\mathrm{E}\left[|X-\mu|^{2}\right]}$ för alla stokastiska variabler $X$ med väldefinierad varians.) Utöver dessa definierar vi också, för positiva stokastiska variabler $X$, variationskoefficienten

$$
\mathrm{R}[X]=\frac{\mathrm{D}[X]}{\mathrm{E}[X]},
$$

vilket beskriver den relativa spridningen runt väntevärdet $E[X]$.

För att beräkna variansen använder vi ofta identiteten

$$
\begin{aligned}
\mathrm{V}[X] &=\mathrm{E}\left[(X-\mu)^{2}\right]=\mathrm{E}\left[X^{2}-2 \mu X+\mu^{2}\right] \\
&=\mathrm{E}\left[X^{2}\right]-2 \mu \mathrm{E}[X]+\mu^{2}=\mathrm{E}\left[X^{2}\right]-2 \mu \cdot \mu+\mu^{2} \\
&=\mathrm{E}\left[X^{2}\right]-\mu^{2}=\mathrm{E}\left[X^{2}\right]-\mathrm{E}[X]^{2} .
\end{aligned}
$$

Ȧterigen är det viktigt att hålla i sär $\mathrm{E}\left[X^{2}\right]$ (väntevärdet av kvadraten) samt $\mathrm{E}[X]^{2}$ (kvadraten av väntevärdet).

Exempel 11. För $X \sim \operatorname{Bin}(n, p)$ behöver vi beräkna $\mathrm{E}\left[X^{2}\right]$. Vi använder samma trick som för beräkningen av $\mathrm{E}[X], d v s$. att termen $x=0$ utgår och att

$$
x\left(\begin{array}{l}
n \\
x
\end{array}\right)=x \frac{n !}{(n-x) ! x !}=n \frac{(n-1) !}{(n-x) !(x-1) !}=n\left(\begin{array}{c}
n-1 \\
x-1
\end{array}\right) .
$$

Detta ger då

$$
\begin{aligned}
\mathrm{E}\left[X^{2}\right] &=\sum_{x=0}^{n} x^{2}\left(\begin{array}{c}
n \\
x
\end{array}\right) p^{x}(1-p)^{n-x} \\
&=\sum_{x=1}^{n} n p x\left(\begin{array}{c}
n-1 \\
x-1
\end{array}\right) p^{x-1}(1-p)^{n-x} \\
&=n p \sum_{k=0}^{n-1}(k+1)\left(\begin{array}{c}
n-1 \\
k
\end{array}\right) p^{k}(1-p)^{n-1-k} \\
&=n p \sum_{k=0}^{n-1} k\left(\begin{array}{c}
n-1 \\
k
\end{array}\right) p^{k}(1-p)^{n-1-k}+n p \sum_{k=0}^{n-1}\left(\begin{array}{c}
n-1 \\
k
\end{array}\right) p^{k}(1-p)^{n-1-k} \quad(k=x-1) \\
&=n p \cdot(n-1) p+n p \cdot 1=n(n-1) p^{2}+n p,
\end{aligned}
$$

där den sista raden fås från faktumet att den första summan är vantevärdet hos en Bin( $(n-1, p)$-fördelad variabel och den andra summan är summan av en sannolikhetsfunktion.

Om vi använder formeln ovan får vi

$$
\mathrm{V}[X]=\mathrm{E}\left[X^{2}\right]-\mathrm{E}[X]^{2}=n(n-1) p^{2}+n p-n^{2} p^{2}=-n p^{2}+n p=n p(1-p)
$$

En liknande beräkning ger att för $X \sim \operatorname{Po}(\mu)$ har vi $\mathrm{E}\left[X^{2}\right]=\mu^{2}+\mu$, vilket ger $\mathrm{V}[X]=$ $\mathrm{E}\left[X^{2}\right]-\mathrm{E}[X]^{2}=\mu^{2}+\mu-\mu^{2}=\mu$. Variansen för en Poissonfördelad stokastisk variabel är alltså densamma som väntevärdet, $\mu$.

Exempel 12. Vi återkommer till $X \sim \operatorname{Exp}(\lambda)$. Från innan har vi $\mu=\mathrm{E}[X]=1 / \lambda$ och får

$$
\begin{aligned}
\mathrm{E}\left[X^{2}\right] &=\int_{x=-\infty}^{+\infty} x^{2} f_{x}(x) d x=\int_{x=0}^{+\infty} x^{2} \lambda e^{-\lambda x} d x \\
&=\left[x^{2} \frac{\lambda e^{-\lambda x}}{-\lambda}\right]_{x=0}^{+\infty}-\int_{x=0}^{+\infty} 2 x \frac{\lambda e^{-\lambda x}}{-\lambda} d x \\
&=0+2 \int_{x=0}^{+\infty} x e^{-\lambda x} \\
&=2\left[x \frac{e^{-\lambda x}}{-\lambda}\right]_{x=0}^{+\infty}-2 \int_{x=0}^{+\infty} \frac{e^{-\lambda x}}{-\lambda} d x \\
&=\frac{2}{\lambda} \int_{x=0}^{+\infty} e^{-\lambda x} d x=\frac{2}{\lambda^{2}}
\end{aligned}
$$

Alltså blir variansen

$$
\mathrm{V}[X]=\mathrm{E}\left[X^{2}\right]-\mathrm{E}[X]^{2}=\frac{2}{\lambda^{2}}-\frac{1}{\lambda^{2}}=\frac{1}{\lambda^{2}}
$$

och standardavvikelsen $\mathrm{D}[X]=1 / \lambda$. Variationskoefficienten $\mathrm{R}[X]$ är då alltid 1 .

Om vi tar en enkel linjärtransformation $Y=a X+b$ av $X$ har vi sedan innan

$$
\mu_{Y}=\mathrm{E}[Y]=\mathrm{E}[a X+b]=a \mathrm{E}[X]+b=a \mu_{X}+b .
$$

Variansen blir då

$$
\begin{aligned}
\mathrm{V}[a X+b] &=\mathrm{V}[Y]=\mathrm{E}\left[\left(Y-\mu_{Y}\right)^{2}\right]=\mathrm{E}\left[\left(a X+b-\left(a \mu_{X}+b\right)\right)^{2}\right] \\
&=\mathrm{E}\left[\left(a X-a \mu_{X}\right)^{2}\right]=\mathrm{E}\left[a^{2}\left(X-\mu_{X}\right)^{2}\right]=a^{2} \mathrm{E}\left[\left(X-\mu_{X}\right)^{2}\right] \\
&=a^{2} \mathrm{~V}[X] .
\end{aligned}
$$

Med andra ord är variansen inte linjär i $X$. Den ändras inte om vi skiftar $X$ med en konstant $b$, vilket är en bra egenskap hos ett spridningsmått - det ska inte bero på läget. Om vi skalar $X$ med en faktor a skalar variansen med kvadraten $a^{2}$. Standardavvikelsen $D(a X+b)$ är däremot $|a| D(X)$, dvs. skalas med $|a|$ (vi får inte en "negativ" spridning bara för att vi multiplicerar med $-1$, till exempel). Hur ser variansen $V(X+Y)$ ut för summan av två stokastiska variabler $X$ och $Y$ ? Har vi också där $V(X+Y)=V(X)+V(Y)$ som i fallet med väntevärdet? Inte nödvändigtvis. Om vi till exempel tar $Y=-X$ så skulle vi då få $V(0)=V(X-X)=V(X)+V(-X)=$ $2 V(X)$, vilket inte verkar särskilt vettigt. Ett fullständigt svar på denna fråga måste därför beakta beroendet mellan $X$ och $Y$ - förstärks eller reduceras spridningen när vi summerar dem?