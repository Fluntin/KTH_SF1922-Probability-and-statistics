\title{
Föreläsning tre
}

\author{
Joakim Andén
}

3 november 2022

\section{Oberoende händelser}

I vissa situationer kan vi konstatera att sannolikheten för $A$ givet $B$ är densamma som den obetingade sannolikheten för $A$. Med andra ord, händelsen $A$ inträffar oberoende av $B$ (och vice versa) och vi har $\mathrm{P}(A \mid B)=\mathrm{P}(A)$. Om vi nu använder identiteten $\mathrm{P}(A \cap B)=\mathrm{P}(A \mid B) \mathrm{P}(B)$ får vi

$$
\mathrm{P}(A \cap B)=\mathrm{P}(A) \mathrm{P}(B) .
$$

När detta gäller säger vi att $A$ och $B$ är oberoende händelser.

![](https://cdn.mathpix.com/cropped/2022_11_15_8e1c4c407cf4d559b3a7g-01.jpg?height=545&width=794&top_left_y=1294&top_left_x=468)

Notera att oberoende och oförenlighet är två vitt skilda relationer. Den enda situationen då två händelser kan vara oberoende och oförenliga är om en av dem har sannolikhet noll. I detta fall har vi att $\mathrm{P}(A \cap B)=\mathrm{P}(\varnothing)=0$ (eftersom $A$ och $B$ är oförenliga) vilket kräver att $\mathrm{P}(A) \mathrm{P}(B)=0$ (om $A$ och $B$ är oberoende). En annan viktig distinktion är att egenskapen oförenlig är något som beror på händelserna i sig och har inget att göra med sannolikhetsmåttet.

Oberoende händelser är väldigt användbara eftersom de förenklar många beräkningar. Lyckligtvis förekommer de också ofta i verkligheten (mer eller mindre). Olika tärningskast kan anses oberoende, till exempel, eller olika mätvärden av en fysisk parameter.

Om vi har fler än två händelser kräver vi att sannolikheten för alla möjliga snitt mellan händelserna kan skrivas som en produkt av händelsernas sannolikheter. Låt oss anta att vi har en samling händelser $A_{1}, A_{2}, \ldots, A_{n}$. För varje $2 \leq k \leq n$ kräver vi då att varje sekvens $1 \leq i_{1}<i_{2}<\cdots<i_{k} \leq n$ uppfyller

$$
\mathrm{P}\left(A_{i_{1}} \cap A_{i_{2}} \cap \cdots \cap A_{i_{k}}\right)=\mathrm{P}\left(A_{i_{1}}\right) \mathrm{P}\left(A_{i_{2}}\right) \cdots \mathrm{P}\left(A_{i_{k}}\right) .
$$

Händelserna är då oberoende. Notera att det räcker inte med parvis oberoende, dvs. att kravet bara uppfylls för $k=2$.

Ett kontraexempel är om vi har ett utfallsrum $\Omega$ bestående av fyra utfall $\omega_{1}, \omega_{2}, \omega_{3}, \omega_{4}$ med ett likformigt sannolikhetsmått (dvs. $P\left(\omega_{i}\right)=1 / 4$ för $i=1,2,3,4$ ). Om vi då tar $A=\left\{\omega_{1}, \omega_{2}\right\}, B=\left\{\omega_{1}, \omega_{3}\right\}$ och $C=\left\{\omega_{1}, \omega_{4}\right\}$ så har vi att $A \cap B=B \cap C=C \cap A=$ $\left\{\omega_{1}\right\}$. Vidare har vi $\mathrm{P}(A)=\mathrm{P}(B)=\mathrm{P}(C)=1 / 2$ samt att $\mathrm{P}(A \cap B)=\mathrm{P}(B \cap C)=\mathrm{P}(C \cap A)=$ $1 / 4$ vilket ger att $A, B$ och $C$ är parvis oberoende. Däremot har vi att $A \cap B \cap C=\left\{\omega_{1}\right\}$, men $\mathrm{P}(A) \mathrm{P}(B) \mathrm{P}(C)=1 / 8 \neq \mathrm{P}(A \cap B \cap C)=1 / 4$.

Sats 1. Om A och B är oberoende har vi att

(i) $A^{*}$ och $B$ är oberoende,

(ii) $A$ och $B^{*}$ är oberoende, och

(iii) $A^{*}$ och $B^{*}$ är oberoende.

![](https://cdn.mathpix.com/cropped/2022_11_15_8e1c4c407cf4d559b3a7g-02.jpg?height=613&width=805&top_left_y=1179&top_left_x=454)

Bevis. Med mängdlärans räkneregler, additivitetsaxiomet och $\mathrm{P}(A \cap B)=\mathrm{P}(A) \mathrm{P}(B)$ får vi

$$
\begin{aligned}
\mathrm{P}(B) &=P(\Omega \cap B) \\
&=\mathrm{P}\left(\left(A^{*} \cup A\right) \cap B\right) \\
&=\mathrm{P}\left(\left(A^{*} \cap B\right) \cup(A \cap B)\right) \\
&=\mathrm{P}\left(A^{*} \cap B\right)+\mathrm{P}(A \cap B) \\
&=\mathrm{P}\left(A^{*} \cap B\right)+\mathrm{P}(A) \mathrm{P}(B)
\end{aligned}
$$

$$
\begin{array}{r}
(B=\Omega \cap B) \\
\left(\Omega=A^{*} \cup A\right) \\
\text { (distributivitet) } \\
\text { (additivitet) } \\
\text { (oberoende) }
\end{array}
$$

Om vi subtraherar $\mathrm{P}(A) \mathrm{P}(B)$ från båda led får vi

$$
\mathrm{P}\left(A^{*} \cap B\right)=(1-\mathrm{P}(A)) \mathrm{P}(B)=\mathrm{P}\left(A^{*}\right) \mathrm{P}(B),
$$

vilket skulle visas för (i). Del (ii) visas genom att byta plats på $A$ och $B$ i del (i). Del (iii) visas genom att tillämpa del (i) följt av del (ii).

Detta resultat kan generaliseras till en godtycklig sekvens av oberoende händelser och deras komplement.

Låt $A_{1}, A_{2}, \ldots, A_{n}$ vara oberoende händelser. Eftersom de är oberoende kan vi enkelt beräkna sannolikheten att minst en av dem inträffar, dvs. att $A_{1} \cup A_{2} \cup \cdots \cup A_{n}$ inträffar. Enligt De Morgans lag har vi att den komplementära händelsen är $A_{1}^{*} \cap$ $A_{2}^{*} \cap \cdots \cap A_{n}^{*}$. Komplementen $A_{1}^{*}, A_{2}^{*}, \ldots, A_{n}^{*}$ är också oberoende som vi sett ovan. Vi har då

$$
\begin{aligned}
\mathrm{P}\left(A_{1} \cup A_{2} \cup \cdots A_{n}\right) &=1-\mathrm{P}\left(A_{1}^{*} \cap A_{2}^{*} \cap \cdots \cap A_{n}^{*}\right) \\
&=1-\mathrm{P}\left(A_{1}^{*}\right) \mathrm{P}\left(A_{2}^{*}\right) \cdots \mathrm{P}\left(A_{n}^{*}\right) \\
&=1-\left(1-\mathrm{P}\left(A_{1}\right)\right)\left(1-\mathrm{P}\left(A_{2}\right)\right) \cdots\left(1-\mathrm{P}\left(A_{n}\right)\right) .
\end{aligned}
$$

Om händelserna alla har samma sannolikhet $p$ får vi sannolikheten

$$
1-(1-p)^{n} \text {. }
$$

Exempel 2. Antag att en tärning kastas tre gånger. Vad är sannolikheten att vi får en sexa exakt ett av kasten?

I stället för att beräkna detta med hjälp av kombinatoriken kan vi utnyttja faktumet att varje tärningskast är oberoende av varandra. Sannolikheten att vi får en sexa först och sedan två icke-sexor är då

$$
\frac{1}{6} \cdot \frac{5}{6} \cdot \frac{5}{6}=\frac{25}{216} .
$$

På samma sätt har vi sannolikheten att få en icke-sexa, följt av en sexa och sedan en icke-sexa blir

$$
\frac{5}{6} \cdot \frac{1}{6} \cdot \frac{5}{6}=\frac{25}{216} .
$$

Till slut, två icke-sexor följt av en sexa har sannolikheten

$$
\frac{5}{6} \cdot \frac{5}{6} \cdot \frac{1}{6}=\frac{25}{216} .
$$

Dessa tre händelser är oförenliga (första tärningen kan inte vara en sexa och en icke-sexa, till exempel) så den totala sannolikheten blir

$$
\frac{25}{216}+\frac{25}{216}+\frac{25}{216}=\frac{25}{72} \text {. }
$$

Vad är sannolikheten att vi får exakt två sexor? 

\section{Stokastiska variabler}

Ofta är vi intresserade av att associera vissa värden, dvs. reella tal, med olika utfall i ett slumpmässigt försök. Detta kan vara ett mätvärde, en vinst, en tidpunkt, osv. som beror på resultatet av ett slumpmässigt förlopp. Vi kan säga att värdet i sig är slumpmässigt, eller stokastiskt. Därför kallas sådana värden för stokastiska variabler (s.v.) eller slumpvariabler.

Konkret så tilldelar vi ett visst värde $x$ till varje utfall $\omega \in \Omega$. En enkel stokastisk variabel är antalet ögon vid ett tärningskast. I detta fall motsvarar varje utfall ett heltal mellan ett och sex, vilket kan beskrivas som en stokastisk variabel. Vi kanske har slagit vad om tärningskastet och vinner sex kronor om vi slår en etta eller två och måste betala två kronor annars. I så fall kan vi tilldela ett vinstvärde till varje utfall: sex kronor om vi slår en etta eller tvåa och minus två kronor annars.

![](https://cdn.mathpix.com/cropped/2022_11_15_8e1c4c407cf4d559b3a7g-04.jpg?height=401&width=640&top_left_y=873&top_left_x=447)

Om vi har två tärningskast är ögonsumman en stokastisk variabel. Här tilldelar vi då kastet etta-etta värdet två, kasten etta-tvåa och tvåa-etta värdet tre, osv. En annan stokastisk variabel är antalet ettor i tre tärningskast. Kastet etta-etta-etta ger då värdet tre, etta-etta-tvåa värdet två, tvåa-trea-sexa värdet noll, osv. Vi kan också utföra ett oändligt antal kast och räkna antalet kast tills vi får en etta.

En stokastisk variabel behöver inte ta heltal som värde. Vi kan, till exempel, släppa två tandpetare på bordet och mäta vinkeln mellan de två linjerna som bildas. Vinkeln är en stokastisk variabel med värden i $[0, \pi]$. Om vi släpper tre tandpetare kan vi mäta den area som innesluts av de tre linjerna som bildas. Detta är också en stokastisk variabel med värden i de positiva reella talen.
![](https://cdn.mathpix.com/cropped/2022_11_15_8e1c4c407cf4d559b3a7g-04.jpg?height=372&width=1172&top_left_y=1938&top_left_x=516)

Formellt definierar vi en stokastisk variabel som en funktion $X$ från utfallsrummet $\Omega$ till de reella talen $\mathbb{R}$, dvs. $X: \Omega \rightarrow \mathbb{R}$. För ett givet utfall $\omega$ tar då $X$ värdet $X(\omega) \in \mathbb{R}$. Låt nu $A$ vara en delmängd av $\mathbb{R}$. Vi kan nu betrakta händelsen $X \in A$, vilket är en kortform för $\{\omega \in \Omega: X(\omega) \in A\}$, dvs. alla utfall vars värde $X(\omega)$ på $X$ ligger i $A$. Denna händelse har en sannolikhet som skrivs

$$
P(X \in A)=P(\{\omega \in \Omega: X(\omega) \in A\}),
$$

dvs. sannolikheten för utfallen $\omega$ inträffar som ger att $X(\omega) \in A$. På ett sätt så "inducerar" $X$ ett sannolikhetsmått på $\mathbb{R}$ genom att överföra sannolikhetsmåttet $P$ från $\Omega$ till ett sannolikhetsmått på $\mathbb{R}$. Detta sannolikhetsmått (som tilldelar en sannolikhet till varje delmängd av $\mathbb{R}$ ) kallas sannolikhetsfördelningen eller helt enkelt fördelningen av den stokastiska variabeln $X$. Notera att vi kan definiera stokastiska variabler på olika sätt men ändå erhålla samma fördelning.

Om värdemängden $X(\Omega)=\{X(\omega)$ för $\omega \in \Omega\}$ är ändlig eller uppräkneligt oändlig (dvs. om vi kan "räkna" elementen i $X(\Omega)$ ) kallas $X$ för en diskret stokastisk variabel. Annars är det en kontinuerlig stokastisk variabel. (Notera att $X$ kontinuerlig $\Rightarrow \Omega$ kontinuerligt, dvs. $\Omega$ diskret $\Rightarrow X$ diskret.)

\section{Diskreta stokastiska variabler}

För diskreta stokastiska variabler kan vi betrakta ett specialfall av $\mathrm{P}(X \in A)$, nämligen fallet då $A=\{x\}$ för någon $x \in \mathbb{R}$, vilket skrivs $P(X=x)$ och är lika med $P(\{\omega \in \Omega: X(\omega)=x\}$ ). Notera skillnaden mellan $X$ (en stokastisk variabel, dvs. en funktion från $\Omega$ till $\mathbb{R}$ ) och $x$ (ett konkret utfall av en stokastisk variabel, dvs. ett reellt tal - ett element av $\mathbb{R})$.

En användbar beskrivning av $X$ ges av dess sannolikhetsfunktion

$$
p_{x}(x)=P(x=x) .
$$

Vanligtvis är $p_{x}(x)$ endast definierad för de $x$ som ingår i värdemängden $X(\Omega)$, men den kan också definieras för alla $x \in \mathbb{R}$, i vilket fall de $x$ som inte ingår i $X(\Omega)$ har sannolikhet noll.

Det är vanligt att $X$ tar värden inom de icke-negativa heltalen $\mathbb{N}_{0}=\{0,1,2, \ldots\}$ (eller de positiva heltalen $\mathbb{N}_{1}=\{1,2,3, \ldots\}$ ). Ett par egenskaper hos sannolikhetsfunktionen kan då skrivas ned. Först kan vi skriva om sannolikheten att $X \in A$ med hjälp av sannolikhetsfunktionen

$$
\begin{aligned}
\mathrm{P}(X \in A) &=\mathrm{P}(\{\omega \in \Omega: X(\omega) \in A\}) \\
&=\mathrm{P}\left(\bigcup_{x \in A}\{\omega \in \Omega: X(\omega)=x\}\right) \quad \text { (gruppera utfallen som ger samma värde på } x \text { ) } \\
&=\sum_{x \in A} \mathrm{P}(\{\omega \in \Omega: X(\omega)=x\}) \quad \text { (union av oförenliga händelser) } \\
&=\sum_{x \in A} \mathrm{P}(X=x)=\sum_{x \in A} p_{x}(x)
\end{aligned}
$$

Ett specialfall av detta är om $A=(a, b]$, vilket ger

$$
\mathrm{P}(a<x \leq b)=\sum_{x=a+1}^{b} p_{x}(x) .
$$

Ett annat specialfall ges av $A=\mathbb{R}$,

$$
\sum_{x=0}^{\infty} p_{x}(x)=\mathrm{P}\left(X \in \mathbb{N}_{0}\right)=\mathrm{P}(\Omega)=1 .
$$

Dessa håller även om $X$ tar andra värden än $\mathbb{N}_{0}$, men notationen blir lite otymplig.

\section{Diskreta fördelningar}

Låt oss nu betrakta ett par grundläggande diskreta fördelningar.

Här har vi att ett värde $a$ antas med sannolikhet ett:

$$
p_{x}(x)= \begin{cases}1, & x=a, \\ 0, & \text { annars }\end{cases}
$$

Med andra ord är $X$ deterministisk. Detta kallas en enpunktsfördelning eller helt enkelt en konstant (dvs. den varierar inte slumpmässigt).

Här har värdet $a$ sannolikheten $p$ och ett annat värde $b$ sannolikheten $1-p$ :

$$
p_{x}(x)= \begin{cases}p, & x=a \\ 1-p, & k=b \\ 0, & \text { annars }\end{cases}
$$

Detta är en tvåpunktsfördelning. Ett viktigt specialfall är $a=1, b=0$, vilket kallas bernoullifördelningen med sannolikhet $p$. Om $X$ har denna fördelning så skriver vi $X \sim \operatorname{Ber}(p)$

Givet en ändlig mängd $A$ har vi en fördelning som ger samma sannolikhet åt varje värde i $A$ :

$$
p_{x}(x)= \begin{cases}1 /|A|, & x \in A, \\ 0, & \text { annars }\end{cases}
$$

där $|A|$ är antalet element i $A$. Detta är en likformig fördelning över $A$. Specialfallet $A=\{1,2, \ldots, m\}$ ger sannolikhetsfunktionen

$$
p_{x}(x)= \begin{cases}1 / m, & x=1,2, \ldots, m \\ 0, & \text { annars }\end{cases}
$$

Denna fördelning förkortas ofta $U(A)$. Att $X$ har fördelningen $U(A)$ skrivs då $X \sim U(A)$.

Ett sätt att visualisera en diskret fördelning är att plotta dess värden i ett stapeldiagram: 

![](https://cdn.mathpix.com/cropped/2022_11_15_8e1c4c407cf4d559b3a7g-07.jpg?height=553&width=789&top_left_y=214&top_left_x=625)

Antag nu att en viss händelse inträffar med sannolikhet $p$. Vi utför nu flera oberoende försök och fortsätter tills händelsen inträffar. Låt $X$ vara antalet misslyckade försök innan vi lyckas. Hur ser $p_{x}(k)$ ut?

Om $A_{i}$ betecknar händelsen att vi lyckas i det $i$ :te försöket har vi

$$
\begin{aligned}
p_{x}(x) &=\mathrm{P}\left(A_{1}^{*} \cap A_{2}^{*} \cap \cdots \cap A_{x}^{*} \cap A_{x+1}\right) \\
&=\mathrm{P}\left(A_{1}^{*}\right) \cdot \mathrm{P}\left(A_{2}^{*}\right) \cdots \cdots \mathrm{P}\left(A_{x}^{*}\right) \cdot \mathrm{P}\left(A_{x+1}\right) \\
&=(1-p)^{x} p,
\end{aligned}
$$

eftersom händelserna är oberoende. Vi får då sannolikhetsfunktionen

$$
p_{x}(x)= \begin{cases}(1-p)^{x} p, & x=0,1,2, \ldots \\ 0, & \text { annars. }\end{cases}
$$

Detta är en geometriska fördelningen och betecknas $\mathrm{Ge}(p)$. Vi skriver $X \sim \operatorname{Ge}(p)$. En variant av den geometriska fördelningen räknar det totala antalet försök inklusive det lyckade försöket och motsvarar då den geometriska fördelningen plus ett. Detta kalla för-första-gången-fördelningen.

![](https://cdn.mathpix.com/cropped/2022_11_15_8e1c4c407cf4d559b3a7g-07.jpg?height=544&width=802&top_left_y=1815&top_left_x=626)

Om vi istället antar att vi fixerar antalet försök $n$ och låter $X$ beteckna antalet lyckade försök. För att beräkna $p_{x}(x)$ antar vi först att det är de $x$ första försöken som lyckas och de resterande $n-x$ misslyckas. Sannolikheten för detta är $p^{x}(1-p)^{n-x}$. Det finns så klart andra sätt vi kan erhålla $x$ lyckade försök, mer exakt $\left(\begin{array}{l}n \\ x\end{array}\right)$ sätt. Detta ger då, enligt multiplikationsprincipen,

$$
p_{x}(x)= \begin{cases}\left(\begin{array}{l}
n \\
x
\end{array}\right) p^{x}(1-p)^{n-x}, & x=0,1,2, \ldots, n \\
0, & \text { annars. }\end{cases}
$$

Detta kallas för en binomialfördelning och betecknas $\operatorname{Bin}(n, p)$. Vi skriver $X \sim \operatorname{Bin}(n, p)$.

![](https://cdn.mathpix.com/cropped/2022_11_15_8e1c4c407cf4d559b3a7g-08.jpg?height=556&width=789&top_left_y=611&top_left_x=625)

Exempel 3. Låt $X$ vara antalet ettor i tre tärningskast. I så fall har vi $X \sim \operatorname{Bin}(3,1 / 6)$ och

$$
\begin{aligned}
&p_{x}(0)=\left(\begin{array}{l}
3 \\
0
\end{array}\right)\left(\frac{5}{6}\right)^{3}=\frac{125}{216} \\
&p_{x}(1)=\left(\begin{array}{l}
3 \\
1
\end{array}\right)\left(\frac{1}{6}\right)^{1}\left(\frac{5}{6}\right)^{2}=3 \cdot \frac{1}{6} \cdot \frac{25}{36}=\frac{25}{72} \\
&p_{x}(2)=\left(\begin{array}{l}
3 \\
2
\end{array}\right)\left(\frac{1}{6}\right)^{2}\left(\frac{5}{6}\right)^{1}=3 \cdot \frac{1}{36} \cdot \frac{5}{6}=\frac{5}{72} \\
&p_{x}(3)=\left(\begin{array}{l}
3 \\
3
\end{array}\right)\left(\frac{1}{6}\right)^{3}=\frac{1}{216}
\end{aligned}
$$

Låt oss nu istället för ett ändligt antal försök anta att vi har händelser som inträffar på ett kontinuum. De inträffar i medel med en viss frekvens $\mu$ per tidsenhet (t.ex. radioaktiva sönderfall per sekund, samtal per timme, osv.) och händelserna inträffar oberoende av varandra. Eftersom frekvensen är $\mu$ antar vi att för ett litet tidsintervall $[a, a+h]$ med storlek $h$ så har vi att sannolikheten för att exakt en händelse inträffar i [ $a, a+h]$ är $\mu h$ men att sannolikheten att två eller mer händelse inträffar i intervallet är praktiskt taget noll.

Vi vill nu räkna antalet händelser på intervallet $[0,1]$. För att tillämpa modellen ovan delar vi upp intervallet i $n$ lika stora intervall (dvs. med storlek $1 / n$ ). Om $n$ är tillräckligt stort får vi då att sannolikheten att exakt en händelse inträffar i ett av interfallen är $\mu / n$. Händelserna inträffar oberoende av varandra, så det det totala antalet händelser per tidsenhet har då fördelningen $\operatorname{Bin}(n, \mu / n)$. Sannolikhetsfunk- tionen kan skrivas om enligt

$$
\begin{aligned}
p_{x}(k) &=\left(\begin{array}{c}
n \\
x
\end{array}\right)\left(\frac{\mu}{n}\right)^{x}\left(1-\frac{\mu}{n}\right)^{n-x} \\
&=\frac{n \cdot(n-1) \cdots \cdots(n-x+1) \frac{\mu^{x}}{n^{x}}\left(1-\frac{\mu}{n}\right)^{n}\left(1-\frac{\mu}{n}\right)^{-x}}{x !} \underbrace{n^{x}}_{\rightarrow 1 \text { då } n \rightarrow \infty} \\
&=\frac{\mu^{x}}{x !} \underbrace{\left(1-\frac{\mu}{n}\right)^{n}}_{\rightarrow e^{-\mu} \text { då } n \rightarrow \infty} \underbrace{\left.\frac{n \cdot(n-1) \cdots(n-x+1)}{n}\right)^{-x}}_{\rightarrow 1 \text { dà } n \rightarrow \infty} .
\end{aligned}
$$

Med andra ord, om vi låter $n \rightarrow \infty$, dvs. vi delar upp tidsenheten i mindre och mindre intervall, så får vi sannolikhetsfunktionen

$$
p_{x}(x)= \begin{cases}\frac{\mu^{x}}{x !} e^{-\mu}, & x=0,1,2, \ldots, \\ 0, & \text { annars. }\end{cases}
$$

Detta kallas för en poissonfördelning och betecknas Po $(\mu)$.

![](https://cdn.mathpix.com/cropped/2022_11_15_8e1c4c407cf4d559b3a7g-09.jpg?height=558&width=802&top_left_y=1141&top_left_x=626)

Till slut återkommer vi till urnmodellen (utan återläggning). Om vi har $N$ kulor totalt, varav Np är blåa (dvs. de blåas relativa frekvens är p) har antalet blåa kulor $X$ vid dragning av $n$ kulor från urnan sannolikhetsfunktionen

$$
p_{X}(x)= \begin{cases}\frac{\left(\begin{array}{l}
N p \\
x
\end{array}\right)\left(\begin{array}{c}
N(1-p) \\
n-x
\end{array}\right)}{\left(\begin{array}{l}
N \\
n
\end{array}\right)}, & x=\max (0, n-N(1-p)), \ldots, \min (N p, n) \\
0, & \text { annars. }\end{cases}
$$

Detta är den hypergeometriska fördelningen som betecknas Hyp $(N, n, p)$. 

![](https://cdn.mathpix.com/cropped/2022_11_15_8e1c4c407cf4d559b3a7g-10.jpg?height=553&width=789&top_left_y=214&top_left_x=625)