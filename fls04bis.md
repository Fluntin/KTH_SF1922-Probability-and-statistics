\title{
Föreläsning fyra bis
}

\author{
Joakim Andén
}

9 november 2022

\section{Differentialkalkyl i flera variabler}

En vanlig (endimensionell funktion) $f(x)$ kan approximeras lokalt med en linjär funktion - en tangentlinje. Detta görs med hjälp av dess derivata

$$
\frac{d f}{d x} f(a)=\lim _{h \rightarrow 0} \frac{f(a+h)-f(a))}{h} .
$$

Vi har då att

$$
y=f(a)+\frac{d f}{d x}(x-a)
$$

bildar en tangentlinje för kurvan $y=f(x)$ vid punkten $x=a$.

![](https://cdn.mathpix.com/cropped/2022_11_15_350ccfc6613084262ea0g-1.jpg?height=377&width=594&top_left_y=1508&top_left_x=771)

På samma sätt kan vi betrakta en tvådimensionell funktion $f(x, y)$ som tar en punkt $(x, y) \in \mathbb{R}^{2}$ till ett värde $z=f(x, y) \in \mathbb{R}$. Istället för en kurva får vi en yta $z=f(x, y)$ i tre dimensioner och istället för en tangentlinje får vi ett tangentplan i $(x, y)=(a, b)$. Denna är given av

$$
z=f(a, b)+\frac{\partial f}{\partial x}(a, b)(x-a)+\frac{\partial f}{\partial y}(a, b)(y-b),
$$

där vi definierar partialderivatorna

$$
\frac{\partial f}{\partial x}(a, b)=\lim _{h \rightarrow 0} \frac{f(a+h, y)-f(a, b)}{h} \quad \frac{\partial f}{\partial y}(a, b)=\lim _{h \rightarrow 0} \frac{f(a, b+h)-f(a, b)}{h} .
$$



![](https://cdn.mathpix.com/cropped/2022_11_15_350ccfc6613084262ea0g-2.jpg?height=377&width=680&top_left_y=213&top_left_x=793)

För att beräkna dessa använder vi samma räkneregler som för vanliga derivator och håller den andra variabeln konstant. Till exempel, om $f(x, y)=x^{3}+x y+e^{-y}$ har vi

$$
\frac{\partial f}{\partial x}(x, y)=3 x^{2}+y \quad \frac{\partial f}{\partial y}(x, y)=x-e^{-y} .
$$

Ibland kombineras partialderivatorna i en vektor

$$
\nabla f(a, b)=\left[\begin{array}{c}
\frac{\partial f}{\partial x}(a, b) \\
\frac{\partial f}{\partial y}(a, b)
\end{array}\right]
$$

som kallas gradienten av $f(x, y)$ i punkten $(x, y)=(a, b)$. I exemplet ovan har vi då gradienten

$$
\nabla f(a, b)=\left[\begin{array}{c}
3 x^{2}+y \\
x-e^{-y}
\end{array}\right] .
$$

Om vi återkommer till envariabelfallet så ser vi att kritiska punkter kan identifieras då $d f / d x=0$, dvs. då tangentlinjen är parallell med $x$-axeln. På samma sätt identifieras kritiska punkter i två variabler då tangentplanet är parallellt med xy-planet. Detta inträffar endast då båda partialderivatorna är noll, dvs. att gradienten är noll. För funktionen $f(x, y)=1-x^{2}-y^{2}+x y$ har vi

$$
\frac{\partial f}{\partial x}(x, y)=-2 x+y \quad \frac{\partial f}{\partial y}(x, y)=-2 y+x .
$$

Om vi sätter dessa till noll och löser det resulterande ekvationssystemet får vi den kritiska punkten $(x, y)=(0,0)$.

Hur bestämmer vi om den kritiska punkten är ett lokalt maximum, lokalt minimum eller någonting annat? Ett sätt är att använda andraderivator (i det flerdimensionella fallet bildar dessa den så kallade hessianen). Ett annat är att använda algebraiska relationer för att förenkla problemet och ersätta det med ett optimeringsproblem i en dimension. 

\section{Integralkalkyl i flera variabler}

![](https://cdn.mathpix.com/cropped/2022_11_15_350ccfc6613084262ea0g-3.jpg?height=621&width=761&top_left_y=278&top_left_x=690)

Om $f(x, y)$ är positiv motsvarar dubbelintegralen

$$
\iint_{D} f(x, y) d x d y
$$

volymen mellan grafen $z=f(x, y)$ och $D \subset \mathbb{R}^{2}$.

![](https://cdn.mathpix.com/cropped/2022_11_15_350ccfc6613084262ea0g-3.jpg?height=528&width=783&top_left_y=1281&top_left_x=693)

För fallet då $D$ är en rektangel $D=R=\left\{(x, y) \in \mathbb{R}^{2}: a \leq x \leq b, c \leq y \leq d\right\}$ kan vi definiera en rektangelpartition $a=x_{0}<x_{1}<\ldots<x_{n}=b, c=y_{0}<y_{1}<\ldots<y_{n}=$ d. Om vi betraktar ett rektangelelement $\left[x_{i}, x_{i+1}\right] \times\left[y_{j}, y_{j+1}\right]$ har vi att utrymmet mellan det elementet och ytan $z=f(x, y)$ kan approximeras av ett prisma med rektangeln som bas och höjd $f\left(x^{*}, y^{*}\right)$, där $x^{*} \in\left[x_{i}, x_{i+1}\right]$ och $y^{*} \in\left[y_{j}, y_{j+1}\right]$. 

![](https://cdn.mathpix.com/cropped/2022_11_15_350ccfc6613084262ea0g-4.jpg?height=456&width=696&top_left_y=203&top_left_x=690)

För enkelhets skull tar vi $x^{*}=x_{i}$ och $y^{*}=y_{j}$, vilket ger ett prisma med volym

$$
f\left(x_{i}, y_{j}\right)\left(x_{i+1}-x_{i}\right)\left(y_{j+1}-y_{j}\right) .
$$

Vi kan förenkla ytterligare genom att anta att alla element i partitionen är lika stora. I så fall har vi $x_{i+1}-x_{i}=\Delta x=(b-a) / n$ för alla $i=0,1, \ldots, n-1$ och $y_{j+1}-y_{j}=\Delta y=$ $(d-c) / n$ för alla $j=0,1, \ldots, n-1$. Detta ger då volymen

$$
f\left(x_{i}, y_{j}\right) \Delta x \Delta y \text {. }
$$

Om vi lägger ihop alla dessa volymapproximationer får vi summan

$$
I_{n}=\sum_{i=0}^{n-1} \sum_{j=0}^{n-1} f\left(x_{i}, y_{j}\right) \Delta x \Delta y .
$$

Detta är riemannsumman för den givna rektangelpartitionen.

Om gränsvärdet för $I_{n}$ då $n \rightarrow+\infty$ existerar (vilket det gör för "snälla" funktioner) definierar vi dubbelintegralen som detta värde:

$$
\iint_{R} f(x, y) d x d y=\lim _{n \rightarrow+\infty} I_{n} .
$$

Vi kan visa att denna integral kan beräknas antingen genom att först integrera längs $x$, sedan längs $y$ eller först längs $y$, sedan längs $x$ :

$$
\iint_{R} f(x, y) d x d y=\int_{y=c}^{d}\left(\int_{x=a}^{b} f(x, y) d x\right) d y=\int_{x=a}^{b}\left(\int_{y=c}^{d} f(x, y) d y\right) d x .
$$

(Parenteserna är bara här för tydlighet och behövs egentligen inte.) Detta kallas Fubinis sats.

![](https://cdn.mathpix.com/cropped/2022_11_15_350ccfc6613084262ea0g-4.jpg?height=431&width=635&top_left_y=2094&top_left_x=772)

Om $D$ inte är en rektangel definierar vi funktionen

$$
\tilde{f}(x, y)= \begin{cases}f(x, y), & (x, y) \in D \\ 0, & \text { annars, }\end{cases}
$$

för $(x, y) \in R$ där $R$ är en rektangel som innesluter $D$. Vi utökar alltså $f(x, y)$ till en funktion $\tilde{f}(x, y)$ på $R$ genom att lägga till nollor utanför $D$.

![](https://cdn.mathpix.com/cropped/2022_11_15_350ccfc6613084262ea0g-5.jpg?height=421&width=610&top_left_y=608&top_left_x=779)

Vi kan nu definiera integralen av $f(x, y)$ över $D$ :

$$
\iint_{D} f(x, y) d x d y=\iint_{R} \tilde{f}(x, y) d x d y
$$

Vi noterar att funktionen $\tilde{f}(x, y)$ nu är diskontinuerlig på randen av $D$, men så länge randen är tillräckligt slät så är högerledet väldefinierat.
![](https://cdn.mathpix.com/cropped/2022_11_15_350ccfc6613084262ea0g-5.jpg?height=444&width=1106&top_left_y=1522&top_left_x=560)

Svårighetsgraden för beräkning av dubbelintegraler beror delvis på integranden, men också på formen på integrationsområdet $D$. Vi kallar integrationsområdet $D$ $y$-enkelt om det finns $a, b$ och funktioner $g_{1}(x), g_{2}(x)$ så att

$$
D=\left\{(x, y): a \leq x \leq b, g_{1}(x) \leq y \leq g_{2}(x)\right\} .
$$

I detta fall kan vi beräkna dubbelintegralen enligt definitionen ovan genom att först integrera längs $y$ och sedan längs $x$ :

$$
\begin{aligned}
\iint_{D} f(x, y) d x d y &=\iint_{R} \tilde{f}(x, y) d x d y \\
&=\int_{x=a}^{b} \int_{y=c}^{d} \tilde{f}(x, y) d y d x \\
&=\int_{x=a}^{b}\left(\int_{y=c}^{g_{1}(x)} \tilde{f}(x, y) d y+\int_{y=g_{1}(x)}^{g_{2}(x)} \tilde{f}(x, y) d y+\int_{y=g_{2}(x)}^{d} \tilde{f}(x, y) d y\right) d x \\
&=\int_{x=a}^{b}\left(0+\int_{y=g_{1}(x)}^{g_{2}(x)} f(x, y) d y+0\right) d x \\
&=\int_{x=a}^{b} \int_{y=g_{1}(x)}^{g_{2}(x)} f(x, y) d y,
\end{aligned}
$$

där vi har utnyttjat faktumet att för ett fixt $x$ kan vi dela upp [ $c, d]$ längs $y$ i tre intervall: $\left[c, g_{1}(x)\right],\left[g_{1}(x), g_{2}(x)\right]$ och $\left[g_{2}(x), d\right]$. På det första och sista intervallet $\underset{\tilde{f}}{\tilde{f}} \tilde{f}(x, y)=0$ per definition (eftersom $(x, y) \notin D$ ) samt i det andra intervallet har vi $\tilde{f}(x, y)=f(x, y)$ (eftersom $(x, y) \in D$ ).

![](https://cdn.mathpix.com/cropped/2022_11_15_350ccfc6613084262ea0g-6.jpg?height=242&width=653&top_left_y=1245&top_left_x=758)

Vi kan också ha ett $x$-enkelt integrationsområde $D$ om det finns $c, d$ och funktioner $h_{1}(y), h_{2}(y)$ så att

$$
D=\left\{(x, y): h_{1}(y) \leq x \leq h_{2}(y), c \leq y \leq d\right\} .
$$

Om detta håller kan vi integrera först längs $x$, sedan längs $y$, vilket ger

$$
\iint_{D} f(x, y) d x d y=\int_{y=c}^{d} \int_{x=h_{1}(y)}^{h_{2}(y)} f(x, y) d x d y .
$$

Dubbelintegralerna i denna kurs kommer vara över antingen $x$-enkla eller $y$-enkla integrationsområden eller över integrationsområden som kan delas upp i $x$-enkla eller $y$-enkla integrationsområden.

För att illustrera, låt $f(x, y)=e^{-x-y}$ och

$$
D=\{(x, y): x, y \geq 0, x+y \leq 1\} .
$$

Det visar sig att $D$ är både $x$-enkel och $y$-enkel:

$$
D=\{(x, y): 0 \leq x \leq 1,0 \leq y \leq 1-x\}=\{(x, y): 0 \leq x \leq 1-y, 0 \leq y \leq 1\} .
$$



![](https://cdn.mathpix.com/cropped/2022_11_15_350ccfc6613084262ea0g-7.jpg?height=350&width=442&top_left_y=226&top_left_x=576)

Vi väljer att först integrera längs $y$ först, sedan längs $x$. Detta ger

$$
\begin{aligned}
\iint_{D} f(x, y) d x d y &=\int_{x=0}^{1} \int_{y=0}^{1-x} e^{-x-y} d y d x \\
&=\int_{x=0}^{1}\left[\frac{e^{-x-y}}{-1}\right]_{y=0}^{1-x} d x \\
&=\int_{x=0}^{1}-e^{-1}+e^{-x} d x \\
&=-e^{-1}+\left[\frac{e^{-x}}{-1}\right]_{x=0}^{1}=-e^{-1}-e^{-1}+1=1-2 e^{-1} \approx 0.26 .
\end{aligned}
$$

Definitionerna ovan gäller för begränsade integrationsområden $D$. Om $D$ är obegränsad kan vi beräkna dubbelintegralen som ett gränsvärde

$$
\iint_{D} f(x, y) d x d y=\lim _{N \rightarrow+\infty} \iint_{D \cap[-N, N]^{2}} f(x, y) d x d y .
$$

Dessa integraler kan beräknas på samma sätt som ovan om $D$ är $x$-enkel (då $a(y), b(y), c, d$ tillåts vara oändligt stora) eller $y$-enkel (då $a, b, c(x), d(x)$ tillåts vara oändligt stora).

Som exempel, låt oss integrera

$$
f(x, y)= \begin{cases}e^{-|x+y|}, & 0 \leq x \leq 1 \\ 0, & \text { annars }\end{cases}
$$

över $\mathbb{R}^{2}$. Funktionen är nollskild över $[0,1] \times \mathbb{R}$, så det räcker att integrera över denna domän. Den är både $x$-enkel och $y$-enkel så vi integrerar först med avseende på $y$ och sedan $x$. Vi får då

$$
\begin{aligned}
\iint_{\mathbb{R}^{2}} f(x, y) d x d y &=\int_{x=0}^{1} \int_{y=-\infty}^{+\infty} e^{-|x+y|} d y d x \\
&=\int_{x=0}^{1}\left(\int_{y=-\infty}^{-x} e^{-|x+y|} d y+\int_{y=-x}^{+\infty} e^{-|x+y|} d y\right) d x \\
&=\int_{x=0}^{1}\left(\int_{y=-\infty}^{-x} e^{x+y} d y+\int_{y=-x}^{+\infty} e^{-x-y} d y\right) d x \\
&=\int_{x=0}^{1}\left(\left[e^{x+y}\right]_{y=-\infty}^{-x}+\left[-e^{-x-y}\right]_{y=-x}^{+\infty}\right) d x \\
&=\int_{x=0}^{1}(1+1) d x=2,
\end{aligned}
$$

där vi har utnyttjat att $|x+y|=-x-y$ för $y<-x$ och $|x+y|=x+y$ för $y>-x$.