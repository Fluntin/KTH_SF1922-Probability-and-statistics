\title{
Föreläsning fyra
}

\author{
Joakim Andén
}

8 november 2022

\section{Repetition}

En stokastisk variabel är en funktion som avbildar utfallsrummet $\Omega$ på $\mathbb{R}$

$$
X: \Omega \rightarrow \mathbb{R} .
$$

Om värdemängden $X(\Omega)=\{x(\omega): \omega \in \Omega\}$ är ändlig eller uppräkneligt oändlig sägs $X$ vara en diskret stokastisk variabel. I detta fall kan vi definiera en tillhörande sannolikhetsfunktion

$$
p_{X}(x)=P(X=x)=P(\{\omega \in \Omega: X(\omega)=x\}),
$$

vilket kan användas för att beräkna mer komplicerade sannolikheter som bland annat

$$
P(X \in A)=\sum_{x \in A} p_{X}(x) .
$$

\section{Kontinuerliga stokastiska variabler}

Vad gör vi om värdemängden $X(\Omega)$ är ouppräkneligt oändlig? Om så är fallet kan vi inte nödvändigtvis tilldela varje värde i $X(\Omega)$ en positiv sannolikhet, eftersom summan av dessa oändligt många positiva sannolikheter skulle bli oändligt stort. Med andra ord har vi $\mathrm{P}(X=x)=0$.

Istället betraktar vi sannolikheten för ett intervall $\mathrm{P}(X \in[a, b])$, dvs. sannolikheten att $X$ ligger i intervallet $[a, b]$. Denna sannolikhet behöver inte nödvändigtvis vara noll, eftersom vi kan beskriva hela $\mathbb{R}$ som en uppräknelig union av små intervall. Vad händer nu om vi tar $b=a+\Delta a$ och låter $\Delta a$ gå mot noll? Då får vi också att $\mathrm{P}(X \in[a, a+\Delta a])$ går mot noll, eftersom intervallets storlek $\Delta a$ blir oändligt litet. Men om vi delar med $\Delta a$, får vi en sorts "sannolikhetstäthet"

$$
\frac{\mathrm{P}(X \in[a, a+\Delta a])}{\Delta a}
$$

som mäter hur mycket sannolikhet vi har "runt" a per enhet. Om vi låter $\Delta a$ gå mot noll i kvoten ovan så borde vi få någon slags infinitesimal täthet som inte är noll. Mer formellt säger vi att om det existerar en funktion $f: \mathbb{R} \rightarrow[0,1]$ så att

$$
\mathrm{P}(X \in A)=\int_{A} f(x) d x
$$

så är $X$ en kontinuerlig stokastisk variabel. Funktionen $f(x)$ kallas $X$ :s täthetsfunktion och betecknas ofta $f_{X}(x)$ om den behöver särskiljas från täthetsfunktioner som tillhör andra stokastiska variabler. Om vi sätter $A=[a, b]$ ovan har vi

![](https://cdn.mathpix.com/cropped/2022_11_15_fcc724d91d7edc45cae4g-02.jpg?height=730&width=1071&top_left_y=608&top_left_x=473)

Notera att det inte spelar roll för kontinuerliga stokastiska variabler om vi inkluderar ändpunkterna $a$ och $b$ eller inte. Med andra ord har vi

$$
\mathrm{P}(a<X<b)=\mathrm{P}(a \leq X<b)=\mathrm{P}(a \leq X \leq b)=\mathrm{P}(a<X \leq B) .
$$

Detta beror på att sannolikheten att $X$ tar exakt värdet $a$ eller $b$ är noll, så att inkludera dem eller inte ger samma sannolikhet. Detta gäller dock inte för diskreta stokastiska variabler eftersom varje värde på $X$ kan ha en nollskilld sannolikhet.

Om vi nu återgår till vårt lilla intervall $[a, a+\Delta a]$ ser vi att

$$
\begin{aligned}
\frac{\mathrm{P}(X \in[a, a+\Delta a])}{\Delta a} &=\frac{1}{\Delta a} \int_{a}^{a+\Delta a} f(x) d x \\
&=\frac{1}{\Delta a} f(a+\theta \Delta a) \Delta a=f(a+\theta \Delta a)
\end{aligned}
$$

för något $\theta \in[0,1]$ enligt medelvärdessatsen. Vi ser då att

$$
\frac{\mathrm{P}(X \in[a, a+\Delta a])}{\Delta a}=f(a+\theta \Delta a) \longrightarrow f(a)
$$

då $\Delta a \longrightarrow 0$, så $f(a)$ motsvarar mycket riktigt vår intuition om sannolikhetens "täthet".

Täthetsfunktionen $f_{x}(x)$ har två viktiga egenskaper: (i) $f_{x}(x) \geq 0$ för alla $x \in \mathbb{R}$, och

(ii) $\int_{\mathbb{R}} f_{x}(x) d x=1$.

Del (i) kan anses hålla per definition eller visas genom att betrakta gränsvärdet ovan och notera att högerledet alltid är icke-negativt. Del (ii) fås genom

$$
\int_{\mathbb{R}} f_{X}(x) d x=\int_{-\infty}^{+\infty} f_{X}(x) d x=\mathrm{P}(-\infty<x<\infty)=\mathrm{P}(\Omega)=1 .
$$

Som exempel kan vi ta täthetsfunktionen

$$
f_{x}(x)= \begin{cases}e^{-x}, & x \geq 0 \\ 0, & x<0\end{cases}
$$

Denna är positiv ( $e^{-x}>0$ för alla $x \geq 0$ ) och integrerar till ett:

$$
\int_{-\infty}^{+\infty} f_{X}(x) d x=\int_{-\infty}^{0} 0 d x+\int_{0}^{+\infty} e^{-x} d x=0+1=1 .
$$

(Vi kommer att se senare att denna täthetsfunktion tillhör en exponentialfördelning.)

\section{Fördelningsfunktion}

Ett annat användbart sätt att beskriva en stokastisk variabel är att betrakta dess fördelningsfunktion

$$
F_{x}(x)=\mathrm{P}(x \leq x) .
$$

I det kontinuerliga fallet har vi då

$$
F_{x}(x)=\mathrm{P}(x \leq x)=\mathrm{P}(x \in(-\infty, x])=\int_{-\infty}^{x} f_{x}(u) d u .
$$

(Notera att vi måste använda variabeln $u$ i integralen för att $x$ används redan som övre integrationsgräns.)

Definitionen av $F_{X}(x)$ ovan gäller också om $X$ är en diskret stokastisk variabel. I detta fall har vi

$$
F_{X}(x)=\sum_{u \in X(\Omega): u \leq x} p_{X}(u) .
$$

Eftersom mängden $\{u \in X(\Omega): u \leq x\}$ är densamma för olika $x$ som ligger mellan de värden som $X$ antar så är fördelningsfunktionen styckvis konstant funktion, också kallad stegfunktion eller trappfunktion. Varje hopp (eller språng) i $F_{X}(x)$ motsvarar ett diskret värde som antas av $X(\Omega)$.

Fördelningsfunktionen existerar alltså för både kontinuerliga och stokastiska variabler och är därför en mer generell beskrivning av $X$ jämfört med sannolikhetsfunktioner och täthetsfunktioner. Man kan, till exempel, definiera blandade stokastiska variabler som har både diskreta och kontinuerliga komponenter (se Blom, m. fl., kap. 3.9). Utöver dessa går det också att definiera stokastiska variabler som inte kan beskrivas som en kombination av kontinuerliga och diskreta stokastiska variabler, men som har en fördelningsfunktion, så kallade singulära fördelningar. Ingen av dessa typer av stokastiska variabler kommer att studeras i kursen.

Som exempel på fördelningsfunktion för en diskret stokastisk variabel betraktar vi $X \sim U(\{1,2\})$. Den har sannolikhetsfunktionen

$$
p_{x}(x)= \begin{cases}1 / 2, & x=1,2 \\ 0, & \text { annars }\end{cases}
$$

medan fördelningsfunktionen är

$$
F_{x}(x)= \begin{cases}0, & x<1 \\ 1 / 2, & 1 \leq x<2 \\ 1, & 2 \leq x\end{cases}
$$
![](https://cdn.mathpix.com/cropped/2022_11_15_fcc724d91d7edc45cae4g-04.jpg?height=342&width=1092&top_left_y=1138&top_left_x=511)

Notera att fördelningsfunktionen inte nödvändigtvis är kontinuerlig, men uppfyller

$$
\lim _{x \rightarrow a^{+}} F_{x}(x)=F_{x}(a)
$$

i alla punkter a, dvs. att gränsvärdet högerifrån överensstämmer med funktionsvärdet. En sådan funktion kallas högerkontinuerlig (eller kontinuerlig till höger). Fördelningsfunktionen för en kontinuerlig stokastisk variabel är också kontinuerlig i den vanliga bemärkelsen (dvs. kontinuerlig både från höger och från vänster).

Eftersom $F_{X}(x)$ för en kontinuerlig stokastisk variabel ges av integralen av $f_{X}(x)$ kan vi vända på relationen genom integralkalkylens fundamentalsats, vilket ger

$$
f_{x}(x)=\frac{d}{d x} F_{x}(x) .
$$

Vi kan åstadkomma en liknande relation för diskreta stokastiska variabler, men formen på denna beror på värdemängden $X(\Omega)$ hos $X$. Om vi har $X(\Omega)=\mathbb{N}_{0}$ får vi

$$
p_{x}(x)= \begin{cases}F_{x}(0), & x=0 \\ F_{x}(x)-F_{x}(x-1), & x=1,2,3, \ldots\end{cases}
$$

Fördelningsfunktioner uppfyller ett par andra egenskaper: (i) $F_{x}(x) \rightarrow 0$ då $x \rightarrow-\infty$,

(ii) $F_{x}(x) \rightarrow 1$ då $x \rightarrow+\infty$, och

(iii) $F_{x}(x)$ är växande (icke-avtagande) med avseende på $x$.

Del (i) och (ii) följer från faktumet att $P(\varnothing)=0$ och $P(\Omega)=1$. Del (iii) fås eftersom givet $a \leq b$ har vi $\{X \leq a\} \subset\{X \leq b\}$, vilket ger $\mathrm{P}(X \leq a) \leq \mathrm{P}(X \leq b)$, dvs. $F_{X}(a) \leq$ $F_{x}(b)$

En annan användbar egenskap som gäller för både diskreta och kontinuerliga variabler är följande sats.

Sats 1. Om $a<b$ har vi

$$
P(a<x \leq b)=F_{x}(b)-F_{x}(a) .
$$

Bevis. Intervallet $(-\infty, b]$ kan skrivas som unionen av de disjunkta intervallen $(-\infty, a]$ och $(a, b]$. Händelserna $X \in(-\infty, a]$ och $X \in(a, b]$ är alltså oförenliga och vi får

$$
\mathrm{P}(X \in(-\infty, b]))=\mathrm{P}(X \in(-\infty, a])+\mathrm{P}(X \in(a, b])
$$

vilket, genom insättning av definitionerna av $F_{x}(a)$ och $F_{x}(b)$, ger

$$
\left.F_{x}(b)=F_{x}(a)+\mathrm{P}(X \in(a, b])\right) \text {. }
$$

Genom att subtrahera $F_{X}(a)$ från båda leden fås den önskade identiteten.

Notera att faktumet att intervallet $(a, b]$ är halvöppet spelar roll för diskreta stokastiska variabler (där sannolikheten $\mathrm{P}(X=a) \neq 0$ ), men inte för kontinuerliga stokastiska variabler. I det senare fallet kan vi ersätta med ett öppet $((a, b))$ eller stängt intervall $([a, b])$, dvs.

$$
\mathrm{P}(a \leq X \leq b)=\mathrm{P}(a<X<b)=\mathrm{P}(a \leq x<b)=\mathrm{P}(a<X \leq b)=F_{x}(b)-F_{x}(a)
$$

Vi kan också använda fördelningsfunktionen för att bestämma ett värde på $x$ som ger en viss sannolikhet att $X$ ligger under eller över $x$. Ofta är vi intresserade av $\alpha$-kvantilen, vilket är det värde på $x$ som ger att sannolikheten $\mathrm{P}(X>x)=\alpha$, dvs. att $F_{X}(x)=\mathrm{P}(X \leq x)=1-\alpha$. Vi betecknar $\alpha$-kvantilen ofta $x_{\alpha}$ och anger $\alpha$ vanligtvis i procent. Vissa kvantiler har speciella namn:

(i) $x_{0.25}$, eller $25 \%-\mathrm{kvantilen,} \mathrm{kallas} \mathrm{den} \mathrm{övre} \mathrm{kvartilen,}$

(ii) $x_{0.50}$, eller $50 \%$-kvantilen, kallas medianen, och

(iii) $x_{0.75}$, eller $75 \%-\mathrm{kvantilen}$, kallas den undre kvartilen. 
![](https://cdn.mathpix.com/cropped/2022_11_15_fcc724d91d7edc45cae4g-06.jpg?height=648&width=698&top_left_y=324&top_left_x=539)

Notera att tekniskt sätt är definitionen ovan inte entydig eftersom det kan finnas flera $x$ så att $F_{X}(x)=1-\alpha$ för något givet $\alpha$ om $F_{x}(x)$ är konstant vid dessa $x$. Man kan då tala om att $x$ är en (av flera) $\alpha$-kvantiler (eller medianer, övre kvartiler, osv.). Definitionen kommer dock vara entydig för fördelningarna som studeras i kursen.

\section{Kontinuerliga fördelningar}

Om $X$ antar ett värde i intervallet $[a, b]$ med lika stor sannolikhet för varje värde får vi

$$
f_{x}(x)= \begin{cases}\frac{1}{b-a}, & x \in[a, b] \\ 0, & \text { annars. }\end{cases}
$$

Värdet $1 /(b-a)$ för $x \in[a, b]$ får vi eftersom $f_{X}(x)$ ska integreras till ett. Mycket riktigt ser vi att

$$
\begin{aligned}
\int_{-\infty}^{\infty} f_{x}(x) d x &=\int_{-\infty}^{a} f_{x}(x) d x+\int_{a}^{b} f_{x}(x) d x+\int_{b}^{+\infty} f_{x}(x) d x \\
&=\int_{-\infty}^{a} 0 d x+\int_{a}^{b} \frac{1}{b-a} d x+\int_{b}^{+\infty} 0 d x \\
&=0+\frac{1}{b-a}(b-a)+0=1,
\end{aligned}
$$

där vi är tvungna att dela upp integralen i tre delar eftersom $f_{X}(x)$ är styckvis kontinuerlig med diskontinuiteter i $a$ och $b$. På samma sätt kan vi beräkna fördelningsfunktionen

$$
\begin{aligned}
F_{X}(x) &=\int_{-\infty}^{x} f_{x}(u) d u \\
&= \begin{cases}\int_{-\infty}^{x} 0 d u, \\
\int_{-\infty}^{a} 0 d u+\int_{a}^{x} \frac{1}{b-a} d u, & x<a \\
\int_{-\infty}^{a} 0 d u+\int_{a}^{b} \frac{1}{b-a} d u+\int_{b}^{x} 0 d u, & x>b\end{cases} \\
&= \begin{cases}0, & x<a \\
\frac{x-a}{b-a}, & a \leq x \leq b \\
1, & x>b\end{cases}
\end{aligned}
$$

Vi betecknar att $X$ är likformigt fördelat på $[a, b]$ genom $X \sim U([a, b])$ eller $X \sim$ $\mathrm{U}(a, b)$
![](https://cdn.mathpix.com/cropped/2022_11_15_fcc724d91d7edc45cae4g-07.jpg?height=450&width=1162&top_left_y=1011&top_left_x=470)

Låt oss nu återgå till Poissonmodellen som introducerades i föregående föreläsning. Vi har då en viss typ av händelser som inträffar oberoende av varandra och med en viss medelfrekvens $\lambda$ per tidsenhet. Vi är nu intresserade av tiden tills första händelsen inträffar, eller, ekvivalent formulerat, tiden mellan två händelser. (Dessa är ekvivalenta eftersom händelserna i en Poissonmodell inträffar oberoende av varandra, därför spelar det ingen roll vad för startpunkt vi tar för mätningen.)

Vi noterar nu att medelantalet händelser i tidsintervallet $[0, t]$ är $\lambda t$. Antalet händelser i det intervallet har då fördelningen $P o(\lambda t)$. Till varje tidpunkt $t$ kan vi då fästa en stokastisk variabel $X_{t}$ som har fördelningen $\operatorname{Po}(\lambda t)$. (En sådan sekvens av stokastiska variabler kallas en stokastisk process, mer specifikt en Poissonprocess, men vi kommer inte att diskutera detta djupare i kursen.) Om vi nu låter $T$ vara en stokastisk variabel som svarar mot tidpunkten för den första händelsen kan vi beräkna dess fördelningsfunktion genom att notera identiteten $\{T \leq t\}=\left\{X_{t} \geq 1\right\}$. Detta följer eftersom $T \leq t$ motsvarar att tidpunkten för den första händelsen är mindre än $t$, vilket betyder att minst en händelse har inträffat på intervallet $[0, t]$, dvs. att $X_{t} \geq 1$. Vi får då för $t \geq 0$ att

$$
F_{T}(t)=\mathrm{P}(T \leq t)=\mathrm{P}\left(X_{t} \geq 1\right)=1-\mathrm{P}\left(X_{t}=0\right)=1-p_{X_{t}}(0)=1-\frac{(\lambda t)^{0}}{0 !} e^{-\lambda t}=1-e^{-\lambda t} .
$$

Om vi deriverar med avseende på $t$ får vi

$$
f_{T}(t)=\frac{d}{d t} F_{T}(t)=\lambda e^{-\lambda t} .
$$

För $t<0$ är sannolikheten noll, vilket ger täthetsfunktionen

$$
f_{T}(t)= \begin{cases}\lambda e^{-\lambda t}, & t \geq 0 \\ 0, & t<0\end{cases}
$$

Fördelningsfunktionen såg vi en bit av ovan och är

$$
F_{T}(t)= \begin{cases}0, & t<0 \\ 1-e^{-\lambda t}, & t \geq 0 .\end{cases}
$$

Den stokastiska variabeln $T$ sägs då vara exponentialfördelad, vilket skrivs $T \sim$ $\operatorname{Exp}(\lambda)$
![](https://cdn.mathpix.com/cropped/2022_11_15_fcc724d91d7edc45cae4g-08.jpg?height=450&width=1160&top_left_y=1060&top_left_x=469)

En viktig egenskap hos exponentialfördelningen är dess minneslöshet, vilken säger att sannolikheten att vänta en viss tid $t$ utöver den tid vi redan har väntat $a$ inte beror på $a$. Vi kan beskriva detta med hjälp av den betingade sannolikheten

$$
\mathrm{P}(T>a+t \mid T>a),
$$

dvs. sannolikheten att vi väntar minst $a+t$ givet att vi redan väntat $a$. Vi har då

$$
\begin{aligned}
\mathrm{P}(T>a+t \mid T>a) &=\frac{\mathrm{P}(T>a+t, T>a)}{\mathrm{P}(T>a)} \quad \text { (definition av betingad sannolikhet) } \\
&=\frac{\mathrm{P}(T>a+t)}{\mathrm{P}(T>a)} \\
&=\frac{1-\mathrm{P}(T \leq a+t)}{1-\mathrm{P}(T \leq a)} \\
&=\frac{1-F_{T}(a+t)}{1-F_{T}(a)} \\
&=\frac{e^{-\lambda(a+t)}}{e^{-\lambda a}} \quad(T>a+t \Rightarrow T>a) \\
&=e^{-\lambda t}=1-F_{T}(t)=\mathrm{P}(T>t), \\
\text { (komplement) }
\end{aligned}
$$

där vi har använt oss av den förkortade beteckningen $\mathrm{P}(\{T>a+t\} \cap\{T>a\})=$ $\mathrm{P}(T>a+t, T>a)$ och faktumet att $\{T>a+t\} \cap\{T>a\}=\{T>a+t\}$ (om $T>a+t$ har vi garanterat att $T>a$ ). Sannolikheten är därför densamma att vi väntar $t$ utöver $a$ som att vi väntar $t$ överhuvudtaget. Detta kan verka kontraintuitivt, men stämmer väl överens med Poissonmodellen vi antagit. Närmare bestämt så inträffar händelserna oberoende av varandra, därför kan nästa inte händelse "minnas" när den senaste inträffade.

Precis som Poissonmodellen generaliserar den ändliga binomialmodellen till ett kontinuum så generaliserar exponentialfördelningen den geometriska fördelningen (eller omvänt, den geometriska fördelningen är en diskret variant av exponentialfördelningen). Den geometriska fördelningen har samma minneslöshetsegenskap: låt oss säga att vi räknar antalet tärningskast till vi observerar en etta. Denna stokastiska variabel har fördelning $G e(1 / 6)$. Om vi slår ett antal kast och inte får en etta så påverkar det inte antalet kast utöver dessa som vi måste slår till vi får en etta. Tanken är densamma för exponentialfördelningen, men i ett kontinuum.

En generalisering av exponentialfördelningen fås om vi lägger till en faktor $t^{\alpha-1} \mathrm{i}$ täthetsfunktionen, vilket ger

$$
f_{T}(t)= \begin{cases}\frac{\lambda^{\alpha}}{\Gamma(\alpha)} t^{\alpha-1} e^{-\lambda t}, & x \geq 0, \\ 0, & x<0,\end{cases}
$$

där $\Gamma(\alpha)$ syftar på gammafunktionen

$$
\Gamma(\alpha)=\int_{0}^{+\infty} u^{\alpha-1} e^{-u} d u
$$

definierad för $\alpha>0$. Denna funktion har för övrigt flera intressanta egenskaper, som att $\Gamma(1)=1, \Gamma(n)=(n-1)$ ! och att $\Gamma(1 / 2)=\sqrt{\pi}$. Om $T$ har denna fördelningen kallas den gammafördelad, vilket betecknas $X \sim \operatorname{Gamma}(c, \lambda)$. Med $c=1$ återfår vi exponentialfördelningen. Gammafördelningen för ett heltal $\alpha=n$ motsvarar tiden vi behöver vänta för att $n$ stycken händelser ska inträffa i Poissonmodellen som vi diskuterade ovan.
![](https://cdn.mathpix.com/cropped/2022_11_15_fcc724d91d7edc45cae4g-09.jpg?height=444&width=1178&top_left_y=1884&top_left_x=450)

Den sista kontinuerliga fördelningen vi diskuterar är normalfördelningen, som har täthetsfunktionen

$$
f_{X}(x)=\frac{1}{\sqrt{2 \pi \sigma^{2}}} e^{-(x-\mu)^{2} / 2 \sigma^{2}},
$$

där $\mu$ och $\sigma$ är parametrarna till fördelningen. Att $X$ har denna fördelning betecknas med $X \sim \mathrm{N}\left(\mu, \sigma^{2}\right)$. Vi kommer inte att säga något mer utöver detta eftersom vi diskuterar normalfördelningen i mer i detalj under senare föreläsningar.
![](https://cdn.mathpix.com/cropped/2022_11_15_fcc724d91d7edc45cae4g-10.jpg?height=448&width=1182&top_left_y=388&top_left_x=447)