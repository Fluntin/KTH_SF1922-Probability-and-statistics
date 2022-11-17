\title{
Föreläsning fem
}

\author{
Joakim Andén
}

10 november 2022

\section{Repetition}

En stokastisk variabel är en funktion som avbildar utfallsrummet $\Omega$ på $\mathbb{R}$

$$
X: \Omega \rightarrow \mathbb{R} .
$$

Om värdemängden $X(\Omega)$ är ändlig eller uppräkneligt oändlig sägs $X$ vara en diskret stokastisk variabel. Vi har då en sannolikhetsfunktion

$$
p_{X}(x)=P(X=x) .
$$

Om den stokastiska variabeln inte är diskret, men det finns en funktion $f_{X}(x)$ så att

$$
\mathrm{P}(X \in A)=\int_{A} f_{X}(x) d x
$$

säger vi att $X$ är en kontinuerlig stokastisk variabel med täthetsfunktion $f_{X}(x)$.

\section{Funktioner av stokastiska variabler}

Om vi har en stokastisk variabel $X$ och vill beräkna en funktion av denna $Y=g(X)$. Det kan röra sig om att vi har mätt en längden på en kvadrat och vill beräkna arean. Eftersom vi har ett visst mätfel kan det då vara intressant att se hur mätfelet fortplantar sig i areavärdet.

I fallet då både $X$ och $Y$ är diskreta stokastiska variabler finns ett enkelt tillvägagångssätt: för varje värde $y$ som $Y$ antar, lägg ihop sannolikheterna för det värden $x$ på $X$ vars avbildning $g(x)$ är lika med $y$. Med andra ord har vi en sannolikhetstabell för $X$ som vi omvandlar till en sannolikhetstabell för $Y$. Formellt kan detta skrivas

$$
p_{Y}(y)=\sum_{x: g(x)=y} p_{X}(x) .
$$

Om $Y$ är diskret men $X$ är kontinuerlig blir det lite mer arbete, men vi kan fortfarande konstruera en sannolikhetstabell för $Y$ enligt samma princip. Vi har då

$$
p_{Y}(y)=P(g(X)=y)=\int_{\{x: g(x)=y\}} f_{X}(x) d x .
$$

När $Y$ är kontinuerlig kan vi inte längre konstruera en sannolikhetstabell utan måste använda en annan metod. Om vi försöker beräkna fördelningsfunktionen för $Y$ får vi

$$
F_{Y}(y)=\mathrm{P}(Y \leq y)=\mathrm{P}(g(X) \leq y) .
$$

Vi skulle nu vilja omvandla denna olikhet $g(X) \leq y$ på $g(X)$ till en olikhet på $X$. Om $g(x)$ har en invers $g^{-1}(y)$ kan vi göra detta. Så är fallet om $g(x)$ är strikt monoton, dvs. strikt växande eller strikt avtagande. Då har vi följande sats.

Sats 1. Låt $g(x)$ vara strikt monoton och låt $X$ vara en kontinuerlig stokastisk variabel. Då gäller att

$$
f_{Y}(y)=f_{X}\left(g^{-1}(y)\right)\left|\frac{d}{d y} g^{-1}(y)\right| .
$$

Bevis. Vi antar först att $g(x)$ är strikt växande. I så fall har vi att

$$
g(x) \leq y \Leftrightarrow x \leq g^{-1}(y),
$$

vilket ger

$$
F_{Y}(y)=\mathrm{P}(Y \leq y)=\mathrm{P}(g(X) \leq y)=\mathrm{P}\left(X \leq g^{-1}(y)\right)=F_{X}\left(g^{-1}(y)\right) .
$$

Om vi deriverar med avseende på y och använder kedjeregeln får vi

$$
f_{Y}(y)=\frac{d}{d x} F_{X}\left(g^{-1}(y)\right) \frac{d}{d y} g^{-1}(y)=f_{X}\left(g^{-1}(y)\right) \cdot \frac{d}{d y} g^{-1}(y) .
$$

Eftersom $g(x)$ är växande har vi att dess derivata är positiv, vilket ger

$$
f_{Y}(y)=f_{X}\left(g^{-1}(y)\right) \cdot\left|\frac{d}{d y} g^{-1}(y)\right| .
$$

Om $g(x)$ är strikt avtagande gäller

$$
g(x) \leq y \Leftrightarrow x \geq g^{-1}(y) .
$$

Samma kalkyl ger då

$$
F_{Y}(y)=1-F_{X}\left(g^{-1}(y)\right)
$$

och vi får tätheten

$$
f_{Y}(y)=f_{X}\left(g^{-1}(y)\right) \cdot-\frac{d}{d y} g^{-1}(y) .
$$

En avtagande funktion har en negativ derivata, så dess negation är positiv. Eftersom $g(x)$ är avtagande är dess invers $g^{-1}(y)$ också avtagande så vi får

$$
f_{Y}(y)=f_{X}\left(g^{-1}(y)\right) \cdot\left|\frac{d}{d y} g^{-1}(y)\right| \text {. }
$$

Det går också att beräkna täthetsfunktioner och fördelningsfunktioner för andra $g(x)$ som inte är strikt monotona. Då kan vi dela upp funktionen i mindre intervall på vilka den är monoton och arbeta med dem. Nyckeln är oavsett att arbeta med fördelningsfunktionen istället för att försöka sig på täthetsfunktionen direkt. 

\section{Tvådimensionella stokastiska variabler}

Vid ett slumpmässigt försök kan vi erhålla mer än ett värde. Till exempel, om vi drar en slumpmässig bowlingboll kan vi associera flera värden:

■ vikten i kg (värde i $\mathbb{R}_{>0}$ ),

■ volymen i $m^{3}$ (värde i $\mathbb{R}_{>0}$ ),

■ färgen som röd-grön-blå-trippel (RGB) (värde i $[0,1] \times[0,1] \times[0,1]$ ),

- och så vidare.

Låt oss säga att vi tar vikten $X$ och volymen $Y$. Dessa bildar då en avbildning $(X, Y)$ från utfallsrummet $\Omega$ (av möjliga bowlingbollar) på $\mathbb{R} \times \mathbb{R}=\mathbb{R}^{2}$. Med andra ord, för varje utfall $\omega$ (bowlingboll) har vi $X(\omega)$ (vikten) och $Y(\omega)$ (volymen). Vi kan då betrakta sannolikheten att $(X, Y) \in A$ för någon delmängd $A \subset \mathbb{R}^{2}$,

$$
P((X, Y) \in A)=P(\{\omega \in \Omega:(X(\omega), Y(\omega)) \in A\}),
$$

och säger att $(X, Y)$ bildar en tvådimensionell stokastisk variabel.
![](https://cdn.mathpix.com/cropped/2022_11_15_49206fc77cb12aa300e8g-03.jpg?height=382&width=1282&top_left_y=1106&top_left_x=450)

Av speciellt intresse är sannolikheten att $(X, Y)$ ligger i delmängden $\{(u, v): u \leq$ $x, v \leq y\}$, dvs. funktionen

$$
F_{X, Y}(x, y)=\mathrm{P}(X \leq x, Y \leq y)
$$

som kallas fördelningsfunktionen för $X, Y$ (eller den simultana fördelningsfunktionen).

Vi noterar att detta kan också utvidgas till fler än två variabler. Detta ger då flerdimensionella stokastiska variabler. Till exempel kan vi ha avbildningen som tar ett utfall $\omega \in \Omega$ och tilldelar den en trippel $(X(\omega), Y(\omega), Z(\omega))$. Detta gäller också begreppen vi introducerar nedan i två dimensioner - de kan ofta generaliseras på ett naturligt sätt till tre eller högre dimensioner.

\section{Diskreta tvådimensionella stokastiska variabler}

Om värdemängderna $X(\Omega)$ och $Y(\Omega)$ båda är ändliga eller uppräkneligt oändliga kallas $(X, Y)$ en diskret tvådimensionell stokastisk variabel. Vi kan då definiera sannolikhetsfunktionen (den simultana sannolikhetsfunktionen)

$$
p_{X, Y}(x, y)=P(X=x, Y=y)=P(\{\omega \in \Omega: X(\omega)=x, Y(\omega)=y\}) .
$$

Som innan kommer vi anta att $X(\Omega)=\mathbb{N}_{0}, Y(\Omega)=\mathbb{N}_{0}$, dvs. att $X$ och $Y$ antar ickenegativa heltal $0,1,2, \ldots$ som värden. Alla resultat gäller naturligtvis också i det mer generella fallet.

Vi kan nu beräkna

$$
\begin{aligned}
P((X, Y) \in A) &=\sum_{(x, y) \in A} p_{X, Y}(x, y) \\
F_{X, Y}(x, y) &=\sum_{u \leq x} \sum_{v \leq y} p_{X, Y}(u, v) .
\end{aligned}
$$

Sannolikhetsfunktionen har egenskaperna

(i) $p_{X, Y}(x, y) \in[0,1]$, och

(ii) $\sum_{x=0}^{+\infty} \sum_{y=0}^{+\infty} p_{X, Y}(x, y)=1$.

Låt oss säga att vi har en tvådimensionell stokastisk variabel $(X, Y)$, men vi inte är intresserade av värdet på $Y$ - det kan vara vad som helst. I det fallet vill vi ha fördelningen för enbart $X$. Eftersom vi arbetar med diskreta stokastiska variabler betraktar vi sannolikhetsfunktionen $p_{x}(x)$. Denna kan fås från den simultana sannolikhetsfunktionen $p_{X, Y}(x, y)$ genom följande identitet:

$$
p_{X}(x)=\mathrm{P}(X=x)=\mathrm{P}(X=x, Y \in \mathbb{R})=\sum_{y=0}^{+\infty} p_{X, Y}(x, y) .
$$

Detta är den marginella sannolikhetsfunktionen för $X$. Vi säger också att fördelningen för $X$ är marginalfördelningen för $X$ med avseende på den tvådimensionella stokastiska variabeln $(X, Y)$. På samma sätt ges den marginella sannolikhetsfunktionen för $Y$ av

$$
p_{Y}(y)=\sum_{\chi=0}^{+\infty} p_{X, Y}(x, y)
$$

\section{Kontinuerliga tvådimensionella stokastiska variabler}

På samma sätt som vi inte kan definiera en sannolikhetsfunktion för endimensionella stokastiska variabler när värdemängden är ouppräkneligt stor kan vi inte heller göra detta i det tvådimensionella fallet. Vi måste därför betrakta "tätheten", sannolikheten per areaenhet, hos sannolikhetsmåttet i olika punkter. $\operatorname{Om}(X, Y)$ är en tvådimensionell stokastisk variabel och det finns en funktion $f_{X, Y}(x, y)$ så att

$$
\mathrm{P}((X, Y) \in A)=\iint_{A} f_{X, Y}(x, y) d x d y
$$

säger vi att $(X, Y)$ är en kontinuerlig tvådimensionell stokastisk variabel med täthetsfunktionen $f_{X, Y}(x, y)$ (kallas också den simultana täthetsfunktionen)

Om detta gäller har vi fördelningsfunktionen

$$
F_{X, Y}(x, y)=\mathrm{P}(X \leq x, Y \leq y)=\int_{u=-\infty}^{x} \int_{v=-\infty}^{y} f_{X, Y}(u, v) d v d u .
$$

Vi kan beräkna täthetsfunktionen utifrån fördelningsfunktionen genom att derivera med avseende på $x$ och $y$ och tillämpa integralkalkylens fundamentalsats två gånger (en gång på $x$ och en gång på $y$ ):

$$
\begin{aligned}
\frac{\partial}{\partial y}\left(\frac{\partial}{\partial x} F_{X, Y}(x, y)\right) &=\frac{\partial}{\partial y}\left(\frac{\partial}{\partial x} \int_{u=-\infty}^{x} \int_{v=-\infty}^{y} f_{X, Y}(u, v) d v d u\right) \\
&=\frac{\partial}{\partial y} \int_{v=-\infty}^{y} f_{X, Y}(x, v) d v \\
&=f_{X, Y}(x, y) .
\end{aligned}
$$

Vi har alltså

$$
f_{X, Y}(x, y)=\frac{\partial^{2}}{\partial X \partial y} F_{X, Y}(x, y) \text {. }
$$

Täthetsfunktionen har egenskaperna
■ $f_{X, Y}(x, y) \geq 0$, och
■ $\iint_{\mathbb{R}^{2}} f_{X, Y}(x, y) d x d y=1$

![](https://cdn.mathpix.com/cropped/2022_11_15_49206fc77cb12aa300e8g-05.jpg?height=610&width=1003&top_left_y=1218&top_left_x=385)

Som för det diskreta fallet kan vi definiera de kontinuerliga marginalfördelningarna för $X$ och $Y$ som har täthetsfunktionerna

$$
f_{X}(x)=\int_{y=-\infty}^{+\infty} f_{X, Y}(x, y) d y \text { och } f_{Y}(y)=\int_{X=-\infty}^{+\infty} f_{X, Y}(x, y) d x
$$

Ett exempel på en kontinuerlig tvådimensionell fördelning är den likformiga fördelningen över $D$ som har täthetsfunktion

$$
f_{X, Y}(x, y)=\left\{\begin{array}{cc}
\frac{1}{\iint_{D} d x d y}, & (x, y) \in D \\
0, & \text { annars, }
\end{array}\right.
$$

där $\iint_{D} d x d y$ helt enkelt är arean av $D$. Notera att det också finns tvådimensionella stokastiska variabler som varken är diskreta eller kontinuerliga (i alla fall enligt definitionen ovan). Det kan vara att vi kombinerar en kontinuerlig stokastisk variabel $X$ (bowlingbollens vikt) med en diskret stokastisk variabel (antal hål i bowlingbollen).

![](https://cdn.mathpix.com/cropped/2022_11_15_49206fc77cb12aa300e8g-06.jpg?height=537&width=661&top_left_y=488&top_left_x=729)

Vi kan också stöta på singulära fördelningar som inte kan skrivas som en sådan kombination, till exempel den likformiga fördelningen över enhetscirkeln $\{(x, y)$ : $\left.x^{2}+y^{2}=1\right\}$. För $A=\{(x, y): a \leq x \leq b, c \leq y \leq d\}$ med $b, d>1$ och $a, c \in[0, \sqrt{2}]$ har vi då

$$
\mathrm{P}((X, Y) \in A)=\frac{\cos ^{-1}(a)-\sin ^{-1}(c)}{2 \pi},
$$

vilket inte kan skrivas som en dubbelintegral av någon funktion $f_{X, Y}(x, y)$ över $A$.

\section{Oberoende stokastiska variabler}

Antag att vi har en tvådimensionell stokastisk variabel $(X, Y)$. Låt oss vidare anta att vi vet att om $X$ antar ett visst värde så påverkar inte detta fördelningen för $Y$ och vice versa. Med andra ord "beror inte" $Y$ på $X$ eller $X$ på $Y$.

Beskriver vi detta med händelser får vi att för alla $A, B \subset \mathbb{R}$ är händelserna

$$
\{X \in A\}=\{\omega \in \Omega: X(\omega) \in A\} \quad \text { och } \quad\{Y \in B\}=\{\omega \in \Omega: Y(\omega) \in B\}
$$

oberoende - att den ena inträffar påverkar inte sannolikheten att den andra inträffar. Detta ger då

$$
\mathrm{P}(X \in A, Y \in B)=\mathrm{P}(\{X \in A\} \cap\{Y \in B\})=\mathrm{P}(X \in A) \mathrm{P}(Y \in B) .
$$

Om vi tar $A=(-\infty, x]$ och $B=(-\infty, y]$ får vi en relation mellan den simultana och de marginella fördelningsfunktionerna:

$$
\begin{aligned}
\mathrm{P}(X \leq x, Y \leq y) &=\mathrm{P}(X \leq x) \mathrm{P}(Y \leq y) \\
F_{X, Y}(x, y) &=F_{X}(\chi) F_{Y}(y) .
\end{aligned}
$$

Antag nu att vi har kontinuerliga stokastiska variabler. Deriverar vi denna relation med avseende på $x$ och $y$ får vi täthetsfunktionen

$$
\begin{aligned}
f_{X, Y}(x, y) &=\frac{\partial^{2}}{\partial x \partial y} F_{X, Y}(x, y) \\
&=\frac{\partial}{\partial x}\left(\frac{\partial}{\partial y} F_{X}(x) F_{Y}(y)\right) \\
&=\frac{\partial}{\partial x} F_{X}(x) f_{Y}(y) \\
&=f_{X}(x) f_{Y}(y),
\end{aligned}
$$

dvs. den simultana täthetsfunktionen faktoriseras i de marginella täthetsfunktionerna.

![](https://cdn.mathpix.com/cropped/2022_11_15_49206fc77cb12aa300e8g-07.jpg?height=558&width=635&top_left_y=968&top_left_x=585)

En naturlig definition är då att två kontinuerliga stokastiska variabler $X$ och $Y$ anses vara oberoende om

$$
f_{X, Y}(x, y)=f_{X}(x) f_{Y}(y) .
$$

Vi kan visa att detta är ekvivalent med att händelserna ovan är oberoende.

Sats 2. De kontinuerliga stokastiska variablerna $X$ och $Y$ är oberoende om och endast om, för varje $A, B \subset \mathbb{R}$

$$
P(X \in A, Y \in B)=P(X \in A) P(Y \in B) .
$$

Bevis. Om $X$ och $Y$ är oberoende har vi

$$
\begin{aligned}
\mathrm{P}(X \in A, Y \in B) &=\mathrm{P}((X, Y) \in A \times B) \\
&=\iint_{A \times B} f_{X, Y}(x, y) d x d y \\
&=\int_{x \in A} \int_{y \in B} f_{X}(x) f_{Y}(y) d y d x \\
&=\int_{x \in A} f_{X}(x) \int_{y \in B} f_{Y}(y) d y d x \\
&=\int_{x \in A} f_{X}(x) \mathrm{P}(Y \in B) d x \\
&=\mathrm{P}(X \in A) \mathrm{P}(Y \in B) .
\end{aligned}
$$

Den andra riktningen fås genom att följa resonemanget ovan för motiveringen av definitionen för oberoende kontinuerliga stokastiska variabler.

På liknande sätt säger vi att de två diskreta stokastiska variablerna $X$ och $Y$ är oberoende om

$$
p_{X, Y}(x, y)=p_{X}(x) p_{Y}(y) .
$$

Även i detta fall kan vi visa att denna definition är ekvivalent med att de associerade händelserna är oberoende.

Ett vanligt förfarande inom sannolikhetsteorin och statistiken är att vi använder oberoenderelationen för att kombinera olika stokastiska variabler. Med andra ord så är det ofta lämpligt att två värden mäts eller på annat sätt produceras oberoende av varandra, till exempel genom repeterade experiment. Detta gör det enkelt att bilda den simultana stokastiska variabeln, man behöver då bara multiplicera täthetsfunktionerna eller sannolikhetsfunktionerna.

Exempel 3. Antag att vi kastar en tärning två gånger och låt $X$ vara antalet ögon $i$ första kastet och $Y$ vara antalet ögon i andra kastet. Då har vi två oberoende diskreta stokastiska variabler med den simultana sannolikhetsfunktionen

$$
p_{X, Y}(x, y)=p_{X}(x) p_{Y}(y)=\frac{1}{6} \cdot \frac{1}{6}=\frac{1}{36} .
$$

för $x, y \in\{1,2, \ldots, 6\}$.

Exempel 4. Antag att vi har två glödlampor med livslängd i timmar fördelade enligt Exp(1). Vi tänder den ena lampan och väntar tills den går ut, sedan tänder vi den andra. Vad är sannolikheten att den totala brinntiden (dvs. från att vi tänt den första tills den andra har gått ut) är mindre än en timme?

Vi har två oberoende stokastiska variabler $X \sim \operatorname{Exp}(1)$ och $Y \sim \operatorname{Exp}(1)$. Deras simultana täthetsfunktion är då

$$
f_{X, Y}(x, y)=f_{X}(x) f_{Y}(y)=e^{-x} e^{-y}=e^{-x-y},
$$

vilket ger den sökta sannolikheten

$$
\begin{aligned}
P(X+Y \leq 1) &=P(\{(X, Y) \in\{(x, y): x, y \geq 0, x+y \leq 1\})\\
&=\iint_{D} f_{X, Y}(x, y) d x d y
\end{aligned}
$$

där $D=\{(x, y): x, y \geq 0, x+y \leq 1\}$.

![](https://cdn.mathpix.com/cropped/2022_11_15_49206fc77cb12aa300e8g-09.jpg?height=349&width=442&top_left_y=590&top_left_x=576)

Vi konstaterar att denna domän är både y-enkel och kan skrivas

$$
D=\{(x, y): 0 \leq x \leq 1,0 \leq y \leq 1-x\},
$$

så vi väljer att först integrera längs y först, sedan längs $x$. Detta ger

$$
\begin{aligned}
\iint_{D} f(x, y) d x d y &=\int_{x=0}^{1} \int_{y=0}^{1-x} e^{-x-y} d y d x \\
&=\int_{x=0}^{1}\left[\frac{e^{-x-y}}{-1}\right]_{y=0}^{1-x} d x \\
&=\int_{x=0}^{1}-e^{-1}+e^{-x} d x \\
&=-e^{-1}+\left[\frac{e^{-x}}{-1}\right]_{x=0}^{1}=-e^{-1}-e^{-1}+1=1-2 e^{-1} \approx 0.26 .
\end{aligned}
$$

Vi kan utvidga båda dessa definitioner till fler än två stokastiska variabler. Om vi till exempel har tre stokastiska variabler $X, Y$ och $Z$ är de oberoende om

$$
\begin{aligned}
p_{X, Y, Z}(x, y, z) &=p_{X}(x) p_{Y}(y) p_{Z}(z) & \text { (diskreta fallet) } \\
f_{X, Y, Z}(x, y, z) &=f_{X}(x) f_{Y}(y) f_{Z}(z) & \text { (kontinuerliga fallet) }
\end{aligned}
$$

\section{Minimum och maximum}

Har vi flera oberoende stokastiska variabler kan vi kombinera dem på olika sätt. Till och börja med kan vi beräkna deras minsta och största värden.

Sats 5. Låt $X$ och $Y$ vara oberoende stokastiska variabler (diskreta eller kontinuerliga). Om $U=\min (X, Y)$ och $V=\max (X, Y)$ har vi

$$
\begin{aligned}
&F_{U}(u)=1-\left(1-F_{X}(u)\right)\left(1-F_{Y}(u)\right) \\
&F_{V}(v)=F_{X}(v) F_{Y}(v) .
\end{aligned}
$$

Bevis. Vi börjar med $V$ eftersom det är lite enklare. Fördelningsfunktionen är då

$$
\begin{aligned}
F_{v}(v) &=\mathrm{P}(V \leq v) \\
&=\mathrm{P}(\max (X, Y) \leq v) \\
&=\mathrm{P}(X \leq v, Y \leq v)=F_{X, Y}(v, v)=F_{X}(v) F_{Y}(v)
\end{aligned}
$$

eftersom $X$ och $Y$ är oberoende.

För $U$ konstaterar vi att $\min (X, Y) \leq u$ är samma sak som att inte $X$ och $Y$ båda är större än $u$. Detta ger då, med hjälp av De Morgans lagar,

$$
\begin{aligned}
F_{U}(u) &=\mathrm{P}(U \leq u) \\
&=\mathrm{P}(\min (X, Y) \leq u) \\
&=\mathrm{P}(X \leq u \text { eller } Y \leq u) \\
&=1-\mathrm{P}(X \geq u, Y \geq u) \\
&=1-\mathrm{P}(X \geq u) \mathrm{P}(Y \geq u) \\
&=1-\left(1-F_{X}(u)\right)\left(1-F_{Y}(u)\right),
\end{aligned}
$$

där näst sista raden fås eftersom händelserna $\{X \geq u\}$ och $\{Y \geq u\}$ är oberoende.

Vi kan utvidga detta till fler än två oberoende stokastiska variabler. Om vi också antar att alla har samma fördelning får vi

$$
F_{\min }\left(x_{1}, x_{2}, \ldots, X_{n}\right)(x)=1-\left(1-F_{X_{1}}(x)\right)^{n} \text { och } F_{\max \left(X_{1}, X_{2}, \ldots, X_{n}\right)}(x)=\left(F_{X_{1}}(x)\right)^{n} .
$$

Exempel 6. Låt $X \sim U([0,1])$, vilket ger

$$
F_{X}(x)=\left\{\begin{array}{cc}
x, & x \in[0,1] \\
0, & \text { annars. }
\end{array}\right.
$$

Om vi har $n$ oberoende kopior $X_{1}, X_{2}, \ldots, X_{n}$ och definierar $U=\min \left(X_{1}, X_{2}, \ldots, X_{n}\right)$ samt $V=\max \left(X_{1}, X_{2}, \ldots, X_{n}\right)$ får vi

$$
F u(x)=\left\{\begin{array}{cc}
1-(1-x)^{n}, & x \in[0,1] \\
0, & \text { annars }
\end{array}\right.
$$

vilket ger

$$
f_{\cup}(x)=\left\{\begin{array}{cc}
n(1-x)^{n-1}, & x \in[0,1] \\
0, & \text { annars }
\end{array}\right.
$$

och

$$
F_{V}(x)=\left\{\begin{array}{cc}
x^{n}, & x \in[0,1] \\
0, & \text { annars }
\end{array}\right.
$$

vilket ger

$$
f_{V}(x)=\left\{\begin{array}{cc}
n x^{n-1}, & x \in[0,1] \\
0, & \text { annars }
\end{array}\right.
$$