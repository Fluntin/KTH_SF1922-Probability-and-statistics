\title{
Föreläsning elva
}

\author{
Joakim Andén
}

\section{1 december 2021}

\section{Hypotesprövning}

Punktskattning och intervallskattning ger oss en uppfattning om värdet hos en eller flera parametrar givet en samling datapunkter. Ibland är vi inte intresserad av parametern i sig utan av påståenden om parametern, till exempel att den har ett visst värde eller överstiger en viss gräns. Sådana påståenden kallar vi hypoteser och vi är intresserade av att se om dessa överensstämmer med datapunkterna, dvs. om hypotesen borde förkastas eller inte. Vi vill också utföra detta på ett sätt som reducerar risken att vi felaktigt förkastar hypotesen. För att göra detta mer konkret börjar vi med ett exempel.

Exempel 1. Margit påstår att hon kan singla slant på ett sätt så att hon får krona oftare än klave. Om detta stämmer är sannolikheten $\theta$ att hon får en krona vid en given singling större än 1/2. Vi tror inte riktigt på det här utan utgår från att slanten inte kan singlas på detta sätt, vilket ger $\theta=1 / 2$, dvs. krona är lika sannolikt som klave.

För att testa vår hypotes " $\theta=1 / 2$ " mot Margits hypotes " $\theta>1 / 2$ " ber vi henne singla slant tio gånger i rad och räknar antalet gånger $x$ hon får krona. Hon lyckas få sju kronor, dvs. $x=7$. Eftersom detta är större än väntevärdet 5 givet $\theta=1 / 2$ hävdar Margit att detta utgör ett bevis för att hon verkligen kan påverka slantsinglingen, dvs. att $\theta>1 / 2$.

Låt oss studera detta från en sannolikhetssynpunkt. Vi kan tänka oss att vi repeterar experimentet ovan (dvs. att vi ber Margit singla tio gånger och räknar antalet kronor). I denna situation vill vi utforma ett test så att vi i de flesta av fallen gör rätt val (vi kan inte garantera att vi alltid gör rätt val på grund av den inbyggda slumpmässigheten i experimentet).

Vi får då att $x$ är då ett utfall av den stokastiska variabeln $X \sim \operatorname{Bin}(10,1 / 2)$ enligt vår hypotes. Tanken är nu att om Margit lyckas få ett tillräckligt stort antal kronor $x$ borde vi förkasta vår hypotes (att $\theta=1 / 2$ ) eftersom detta utfall är väldigt osannolikt under den hypotesen (dvs. det kommer inträffa mycket sällan om vi repeterar experimentet ett stort antal gånger). Ett sådant utfall skulle istället styrka Margits hypotes (att $\theta>1 / 2$ ).

Men hur stort måste $x$ vara för att vi ska anse utfallet tillräckligt osannolikt? Sanno- likheten att alla tio singlingar ger kronor är liten:

$$
P(X=10)=p_{X}(10)=\left(\begin{array}{l}
10 \\
10
\end{array}\right)\left(\frac{1}{2}\right)^{10}=1 \cdot \frac{1}{1024} \approx 0.00098 .
$$

Om vi får $x=10$ borde vi alltså definitivt förkasta hypotesen att $\theta=1 / 2$ och godta Margits hypotes att $\theta>1 / 2$. Sannolikheten att få minst nio kronor är också liten

$$
P(X \geq 9)=p_{X}(9)+p_{X}(10)=\left(\begin{array}{c}
10 \\
9
\end{array}\right)\left(\frac{1}{2}\right)^{9} \cdot \frac{1}{2}+\frac{1}{1024}=\frac{11}{1024} \approx 0.011,
$$

medan sannolikheten att få minst åtta är större

$$
P(X \geq 8)=p_{x}(8)+p_{x}(9)+p_{x}(10)=\left(\begin{array}{c}
10 \\
8
\end{array}\right)\left(\frac{1}{2}\right)^{8} \cdot\left(\frac{1}{2}\right)^{2}+\frac{11}{1024}=\frac{56}{1024} \approx 0.055 .
$$

Låt oss anta att vi vill att risken att felaktigt förkasta hypotesen ska vara mindre än 0.05. Ett rimligt test är då:

Förkasta hypotesen att $\theta=1 / 2$ om $x \geq 9$.

Som vi ser från beräkningen ovan kommer vi att felaktigt förkasta hypotesen (dvs. att $X \geq 9$ även om $\theta=1 / 2$ ) med sannolikhet $0.011<0.05$. I fallet $x=7$ ovan kan vi alltså inte förkasta hypotesen med detta test, dvs. vi godtar inte Margits påstående att hon kan påverka slantsinglingen.

Påståendet som vi prövar, dvs. som vi eventuellt vill förkasta, kallas nollhypotesen eller grundhypotesen och betecknas $H_{0}$. Ofta avser hypotesen något värde på en parameter $\theta$ som bestämmer fördelningarna hos ett antal stokastiska variabler $X_{1}, X_{2}, \ldots, X_{n}$. I de fall som vi betraktar här har nollhypotesen alltid formen $H_{0}: \theta=\theta_{0}$, dvs. påståendet att parametern $\theta$ tar värdet $\theta_{0}$. Detta kallas för en enkel hypotes (till skillnad från sammansatta hypoteser).

Som alternativ till $H_{0}: \theta=\theta_{0}$ har vi en mothypotes eller alternativhypotes $H_{1}$. Mothypotesen kan vara enkel $\left(H_{1}: \theta=\theta_{1}\right)$ eller sammansatt $\left(H_{1}: \theta<\theta_{0}, H_{1}: \theta>\right.$ $\theta_{0}$ eller $\left.H_{1}: \theta \neq \theta_{0}\right)$. Vi antar att antingen $H_{0}$ eller $H_{1}$ måste vara sann och vill bestämma vilken som gäller givet vår data.

För att pröva hypotesen $H_{0}$ utgår vi från utfallen $x_{1}, x_{2}, \ldots, x_{n}$ av $X_{1}, X_{2}, \ldots, X_{n}$. Med hjälp av dessa bildar vi en testvariabel

$$
t_{\mathrm{obs}}=t\left(x_{1}, x_{2}, \ldots, x_{n}\right)
$$

och söker ett en delmängd $C \subset \mathbb{R}$, det så kallade kritiska området. Tanken är då att vi har testet:

Om $t_{\text {obs }} \in C$, förkasta $H_{0}$ (till förmån för $H_{1}$ ).

Om $t_{\text {obs }} \notin C$ förkastar vi alltså inte $H_{0}$.

Hur väljer vi $t\left(x_{1}, x_{2}, \ldots, x_{n}\right)$ och $C$ ? Ofta är $t\left(x_{1}, x_{2}, \ldots, x_{n}\right)$ en punktskattning av $\theta$ och $C$ bestäms då av fördelningen så att $H_{0}$ förkastas om punktskattningen blir för osannolikt givet att $H_{0}$ är sann. Det viktiga är att vi kontrollerar risken att felaktigt förkasta $H_{0}$, dvs. att vi förkastar $H_{0}$ även den är sann. Vi har då en felrisk eller signifikansnivå $\alpha$ som motsvarar hur stor felsannolikhet vi tolererar. Med andra ord vill vi ha

$$
\mathrm{P}\left(t\left(X_{1}, X_{2}, \ldots, X_{n}\right) \in C\right)=\alpha \text { givet att } H_{0} \text { är sann. }
$$

Notera att med notationen $\mathrm{P}(A ; \theta)$ för sannolikheten för händelsen $A$ givet att parametern har värdet $\theta$ så kan vi skriva relationen ovan som

$$
P\left(t\left(X_{1}, X_{2}, \ldots, X_{n} ; \theta_{0}\right) \in C\right)=\alpha
$$

eftersom $H_{0}: \theta=\theta_{0}$.

![](https://cdn.mathpix.com/cropped/2022_11_17_ff4659224c300ab7f60eg-3.jpg?height=388&width=770&top_left_y=744&top_left_x=664)

Populära val för $\alpha$ är $0.05,0.01$ och $0.001$. I diskreta fall, som i exemplet ovan, kan vi inte garantera att $\mathrm{P}\left(t\left(X_{1}, X_{2}, \ldots, X_{n}\right) \in C ; \theta_{0}\right)=\alpha$ men söker då största $C$ så att $\mathrm{P}\left(t\left(X_{1}, X_{2}, \ldots, X_{n}\right) \in C ; \theta_{0}\right) \leq \alpha$. Vi hade då bara ett utfall $x$ och satte $t_{\text {obs }}=x$ med $C=\{9,10\}$, vilket gav en signifikansnivå på $\alpha=0.011<0.05$.

Om vi förkastar $H_{0}$, dvs. om $t_{\text {obs }}\left(x_{1}, x_{2}, \ldots, x_{n}\right) \in C$, sägs ibland att vi har ett signifikant resultat (dvs. en signifikant avvikelse från nollhypotesen). Omvänt om vi inte förkastar $H_{0}$ sägs det att vi har ett icke-signifikant resultat. Denna terminologi säger något om hur vi borde välja nollhypotesen $H_{0}$. Den ska på något sätt motsvara ett standardförlopp eller ett normal- eller referenstillstånd - att avvika från nollhypotesen ska betraktas som något exceptionellt. Detta ställs då i kontrast med $H_{1}$, som representerar avvikelsen från normaltillståndet. I många vetenskapliga experiment motsvarar därför $H_{1}$ ofta en ny teori som ska prövas och som jämförs med nuvarande teori $H_{0}$.

Notera att om $t_{\text {obs }}\left(x_{1}, x_{2}, \ldots, x_{n}\right) \notin C$ så förkastar vi inte $H_{0}$, men tekniskt sett betyder detta inte nödvändigtvis att $H_{0}$ är sann, dvs. att vi godtar $H_{0}$. I exemplet ovan kan det ju vara så att personen i fråga hade handen i bandage och därför inte lyckades med sitt trick. Med detta sagt, om hypotesen är väl ställd (dvs. den avser ett slags normaltillstånd) så brukar man anta att ett icke-förkastande av $H_{0}$ medför ett godkännande av hypotesen.

Detta gäller för många empiriska vetenskapliga fakta. För hundra år sedan var en rimlig nollhypotes att ljus färdas längs en rak linje i rummet. Även om den då nyutvecklade relativitetsteorin förutsade att ljuset kunde böjas av ett gravitationsfält var det inte förrän Arthur Eddingtons expedition observerade just detta i maj 1919 som nollhypotesen kunde förkastas. Om expeditionen inte hade lyckats skulle nollhypotesen fortfarande antas gälla. Att en teori eller hypotes ska kunna förkastas, dvs. att den är falsifierbar, utgör ett viktigt element av vetenskapsteorin. Ett alternativ till att bestämma det kritiska området $C$ är den så kallade direktmetoden eller p-värdesmetoden. Denna utgår ifrån att beräkna sannolikheten att testvariabeln $t(X)$ antar ett värde minst lika "extremt" som $t_{\text {obs }}(X)$. Om den sannolikheten är tillräckligt liten förkastar vi $H_{0}$. Här motsvarar "extrema" värden de värden som $t(X)$ antar givet att $H_{1}$ är sann. Ofta betyder "extremt" att $t_{\text {obs }}(X)$ är mycket stor (antingen negativt eller positivt) eller skiljer sig mycket från något referensvärde. I fallet ovan med slantsingling ses större värden på $t_{\mathrm{obs}}(x)=x$ som mer extrema eftersom de är mindre sannolika under nollhypotesen $H_{0}: \theta=1 / 2$ men är mer sannolika under mothypotesen $H_{0}: \theta>1 / 2$. Vi beräknar därför

$$
p=\mathrm{P}\left(t(X) \geq t_{\mathrm{obs}} ; 1 / 2\right)=\mathrm{P}\left(X \geq t_{\mathrm{obs}} ; 1 / 2\right)
$$

Med fallet $t_{\mathrm{obs}}=x=7$ får vi $p=\mathrm{P}(X \geq 7 ; 1 / 2) \approx 0.17$. Detta ligger långt över någon relevant signifikansnivå (vanligtvis $0.05,0.01$ eller $0.001$ ) så vi förkastar inte $H_{0}$. Direktmetoden kan vara användbar om vi på förhand inte har bestämt vilken signifikansnivå som är relevant för vårt experiment. Resultatet av hypotestestet noteras då med dess tillhörande p-värde.

Ett hypotesttest kallas ensidigt om det kritiska området är begränsat ovanifrån $(C=(-\infty, b])$ eller underifrån $(C=[a,+\infty)$ ). (I direktmetoden motsvarar dessa att vi betraktar små respektive stora värden som extrema.) Om det kritiska området består av två obegränsade intervall $C=(-\infty, b] \cup[a,+\infty)$ kallas det tvåsidigt. (I direktmetoden motsvarar detta att vi betraktar stora skillnader till ett referensvärde som extrema.) Slantsinglingstestet ovan är ett ensidigt hypotestest då det kritiska området har formen $C=[9,+\infty)$.

Låt oss betrakta ett tvåsidigt hypotestest.

Exempel 2. Antag att vi mäter den akustiska absorptionskoefficienten $\theta$ vid en viss frekvens för ett material. Vi vet att vår mätning har ett fel som följer en normalfördelning med känd standardavvikelse $\sigma$. Modellen är alltså att mätningen $x$ är ett utfall av den stokastiska variabeln $X$ med fördelning $\mathrm{N}(\theta, \sigma)$.

För ett visst material, säg ett omålat trägolv, vet vi att $\theta=0.15$ och vi vill veta om vi kan förändra $\theta$ genom en viss behandling, säg att vi målar golvet med en färg som sägs absorbera ljudet. Vår nollhypotes $H_{0}$ är då att ingen förändring sker, dvs. att $\theta=0.15$ medan mothypotesen $H_{1}$ är att det sker en förändring, dvs. att $\theta \neq 0.15$. Givet en mätning $x$ är en lämplig testvariabel då avståndet mellan $x$ och $0.15$ :

$$
u=|x-0.15| .
$$

Om u är större än ett kritiskt värde $\Delta$ förkastar vi $H_{0}$ till förmån för $H_{1}$.

![](https://cdn.mathpix.com/cropped/2022_11_17_ff4659224c300ab7f60eg-4.jpg?height=382&width=832&top_left_y=2151&top_left_x=663)

Hur väljer vi $\Delta$ ? Antag att vi nöjer oss med signifikansnivån $\alpha=0.05$. Vi söker då $\Delta$ så att

$$
P(|X-0.15| \geq \Delta ; 0.15)=\alpha
$$

förutsatt att nollhypotesen gäller, dvs. att $X \sim N(0.15, \sigma)$. Vi kan omvandla sannolikheten ovan till

$$
P(0.15-\Delta<X<0.15+\Delta ; 0.15)=1-\alpha,
$$

och ser att vi kan använda kvantilerna hos den standardiserade normalfördelningen för att få $\Delta=\sigma \lambda_{\alpha / 2} \approx 1.96 \sigma$. Vårt test blir då

$$
\text { Om }|x-0.15| \geq 1.96 \sigma, \text { förkasta } H_{0}: \theta=0.15 \text {. }
$$

Om ett test är ensidigt eller tvåsidigt beror på mothypotesen $H_{1}$. I exemplet ovan har vi mothypotesen $H_{1}: \theta \neq 0.15$. Som konsekvens får vi ett tvåsidigt test eftersom vi kan förkasta $H_{0}$ på två sätt: antingen för att $\theta$ är för litet eller för att $\theta$ är för stort. I slantsinglingsexemplet innan har vi nollhypotesen $H_{0}: \theta=1 / 2$ och mothypotesen $H_{1}: \theta>1 / 2$ eftersom vår slantsinglare Margit påstår att hon kan öka, inte minska, chansen att få krona (om hon endast påstod att hon kunde förändra chansen, men inte i en specifik riktning, skulle vi ha mothypotesen $H_{1}: \theta \neq 1 / 2$ ).

I exemplet ovan kan vi också ana en länk mellan hypotestest och konfidensintervall. Generellt sett, antag att vi har ett konfidensintervall $I_{\theta}$ med konfidensgrad $1-\alpha$ och söker ett test för nollhypotesen $H_{0}: \theta=\theta_{0}$. Testet

Om $\theta_{0} \notin I_{\theta}$, förkasta $H_{0}$

är då ett hypotesttest med felrisk $\alpha$ eftersom vi har

$$
\mathrm{P}\left(\theta_{0} \notin I_{\theta} ; \theta_{0}\right)=1-\mathrm{P}\left(\theta_{0} \in I_{\theta} ; \theta_{0}\right)=1-(1-\alpha)=\alpha .
$$

Konfidensintervallet $I_{\theta}$ kan ofta skrivas som en funktion $I_{\theta}(t)$ av testvariabeln $t$ (till exempel om $t=\bar{x}$ så har vi $I_{\theta}(t)=\left[\bar{x}-\lambda_{\alpha / 2} \sigma / \sqrt{n}, \bar{x}+\lambda_{\alpha / 2} \sigma / \sqrt{n}\right]$ för ett normalfördelat stickprov med känd standardavvikelse $\sigma$ ). Med denna notation kan vi skriva det kritiska området som

$$
C=\left\{t: \theta_{0} \notin I_{\theta}(t)\right\},
$$

dvs. vi förkastar $H_{0}$ för de värden på $t$ som gör att konfidensintervallet $I_{\theta}(t)$ inte täcker $\theta_{0}$.

Vilken typ av konfidensintervall som krävs beror på mothypotesen $H_{1}$. Om $H_{1}$ : $\theta \neq \theta_{0}$, dvs. testet är tvåsidigt, krävs ett tvåsidigt konfidensintervall $I_{\theta}=\left[a_{1}, a_{2}\right]$. Däremot om $H_{1}: \theta<\theta_{0}$ behövs ett uppåt begränsat ensidigt konfidensintervall $I_{\theta}=$ $\left(-\infty, a_{2}\right.$ ] eftersom vi vill förkasta $H_{0}$ om vårt skattade värde på $\theta$ ligger tillräckligt långt under $\theta_{0}$. På samma sätt har vi att för $H_{1}: \theta>\theta_{0}$ behövs ett nedåt begränsat ensidigt konfidensintervall $I_{\theta}=\left[a_{1},+\infty\right)$.

Denna metod för konstruktion av hypotesttest kallas konfidensmetoden. Notera att alla tre metoder (testvariabel, direktmetoden och konfidensmetoden) ger upphov till samma test i slutändan. 

\section{Styrkefunktion}

Som vi har sett är signifikansnivån eller felrisken $\alpha$ ett viktigt mått hos ett hypotestest. Ett bra test ska ha en låg signifikansnivå eftersom detta minskar sannolikheten att $H_{0}$ förkastas felaktigt. Det finns inget som hindrar oss från att göra signifikansnivån godtyckligt liten - i testvariabelmetoden räcker det att minska det kritiska området. Vi minskar då risken att felaktigt förkasta $H_{0}$ men får ett test som kan vara mindre användbart då det blir näst intill omöjligt att förkasta $H_{0}$ över huvud taget. Om vi betraktar nollhypotesen $H_{0}$ som ett normaltillstånd är ett test med låg signifikansnivå alltså ett mycket konservativt test - det krävs mycket extrema utfall för att förkasta nollhypotesen. Detta kan vara lämpligt i vissa situationer, men ofta vill vi inte vara så pass restriktiva.

För att förstå detta är det bra att kategorisera de två typer av fel vi kan göra i samband med ett hypotestest:

- Att vi förkastar $H_{0}$ trots att $H_{0}$ är sann. Detta kallas ett fel av första slaget eller ett typ I-fel. Sannolikheten att vi drabbas av ett sådant fel är $\alpha$, per definition.

- Att vi inte förkastar $H_{0}$ trots att $H_{1}$ är sann. Detta kallas ett fel av andra slaget eller ett typ II-fel.

Om vi reducerar $\alpha$ för mycket löper vi risken att få typ II-fel, dvs. att vi inte förkastar $H_{0}$ även om vi borde då $H_{1}$ är sann.

För att kvantifiera ett typ II-fel är det användbart att betrakta en mothypotes $H_{1}$. Vi kan då betrakta sannolikheten att $H_{0}$ inte förkastas givet att $H_{1}$ är sann. Mer allmänt definierar vi styrkefunktionen

$$
h(\theta)=P\left(H_{0} \text { förkastas; } \theta\right) .
$$

Vi mäter alltså sannolikheten att $H_{0}$ förkastas givet att parametern tar värdet $\theta$. Per definition har vi att $h\left(\theta_{0}\right)=\alpha$ givet nollhypotesen $H_{0}: \theta=\theta_{0}$. För en mothypotes $H_{1}: \theta=\theta_{1}$ har vi att $h\left(\theta_{1}\right)$ är sannolikheten att $H_{0}$ förkastas givet att $H_{1}$ är sann. Vi vill att detta ska vara stort. Med andra ord vill vi att $1-h\left(\theta_{1}\right)$, sannolikheten att vi inte förkastar $H_{0}$ givet att $H_{1}$ är sann (ett typ II-fel) ska vara liten. Vi kallar $h\left(\theta_{1}\right.$ ) testets styrka för mothypotesen $H_{1}: \theta=\theta_{1}$. Generellt sett kan vi säga att ett starkt test (dvs. ett test med hög styrka) är bra på att särskilja mellan $H_{0}$ och $H_{1}$ (för en given signifikansnivå).

Exempel 3. Vi återgår till slantsinglingsproblemet. Anta att Margit gör sitt påstående mer konkret. Hon hävdar att hon kan få krona sju gånger av åtta (att alltid få krona är tydligen för svårt). Vi har då en mothypotes $H_{1}: \theta=7 / 8$ att ställa emot vår nollhypotes $H_{0}: \theta=1 / 2$. Vad är styrkan för $H_{1}$ ?

Vårt test bestod $i$ att förkasta $H_{0}$ om antalet kronor $x$ är större än eller lika med 9 , så vi har

$$
h(\theta)=P(X \geq 9 ; \theta)=p_{x}(9 ; \theta)+p_{x}(10 ; \theta)=\left(\begin{array}{c}
10 \\
9
\end{array}\right) \theta^{9}(1-\theta)+\left(\begin{array}{l}
10 \\
10
\end{array}\right) \theta^{10} .
$$

Detta ger alltså $h(7 / 8) \approx 0.64$, vilket är stort men innebär ändå en risk för typ II-fel på $0.36$, vilket är för högt. Med andra ord finns det en risk att vi missar att förkasta vår nollhypotes även om vi borde (för att $H_{1}$ är sann).

![](https://cdn.mathpix.com/cropped/2022_11_17_ff4659224c300ab7f60eg-7.jpg?height=445&width=749&top_left_y=325&top_left_x=604)

Hur kan vi öka styrkan hos testet? Med andra ord, hur garderar vi oss mot denna mothypotes? Vi singlar flera slantar. Vi tar $n=20$ slantar får vi $X \sim \operatorname{Bin}(20, \theta)$ och ett rimligt test är då

Om $x \geq 15$, förkasta $H_{0}: \theta=1 / 2$.

Detta test har en signifikansnivå på $\alpha=0.02$ och styrkefunktionen

$$
h(\theta)=P(X \geq 15 ; \theta)=\sum_{k=15}^{20}\left(\begin{array}{c}
20 \\
k
\end{array}\right) \theta^{k}(1-\theta)^{20-k} .
$$

Vi får då h(7/8) $\approx 0.97$ vilket ger att sannolikheten för ett typ Il-fel med avseende på denna mothypotes är 0.03. Med detta test vet vi att vi troligen inte kommer att förkasta $\mathrm{H}_{0}$ om nollhypotesen stämmer (eftersom $\alpha$ är litet) samt att vi troligen kommer förkasta $\mathrm{H}_{0}$ om mothypotesen $\mathrm{H}_{1}$ stämmer (eftersom h(7/8) är stort).

\section{Normalfördelade stickprov}

Som innan är vi ofta intresserade av tillämpningar på normalfördelade stickprov. Låt oss anta att vi har oberoende stokastiska variabler $X_{1}, X_{2}, \ldots, X_{n}$ med fördelning $\mathrm{N}(\mu, \sigma)$. Till att börja med antar vi också att $\sigma$ är känd. Vi vill testa nollhypotesen $H_{0}$ : $\mu=\mu_{0}$ med hjälp av utfallen $x_{1}, x_{2}, \ldots, x_{n}$ på signifikansnivå $\alpha$. För att åstadkomma detta bildar vi testvariabeln

$$
u=\frac{\left(\bar{x}-\mu_{0}\right) \sqrt{n}}{\sigma} .
$$

Notera att vi kan också använda $\bar{x}$ som testvariabel, men $u$ är enklare att använda eftersom den motsvarande stokastiska variabeln $U=\left(\bar{X}-\mu_{0}\right) \sqrt{n} / \sigma$ har fördelning $N(0,1)$ när $H_{0}$ är sann. Val av kritiskt område $C$ beror nu på mothypotesen $H_{1}$ :

- Om $H_{1}: \mu \neq \mu_{0}$ förkastar vi $H_{0}$ om $|u| \geq \lambda_{\alpha / 2}$ (dvs. $C=\left(-\infty,-\lambda_{\alpha / 2}\right] \cup\left[\lambda_{\alpha / 2},+\infty\right)$ ).

■ Om $H_{1}: \mu<\mu_{0}$ förkastar vi $H_{0}$ om $u \leq-\lambda_{\alpha}$ (dvs. $\left.C=\left(-\infty,-\lambda_{\alpha}\right]\right)$.

■ Om $H_{1}: \mu>\mu_{0}$ förkastar vi $H_{0}$ om $u \geq \lambda_{\alpha}$ (dvs. $C=\left[\lambda_{\alpha},+\infty\right)$ ). Om $\sigma$ inte är känd och måste skattas från $x_{1}, x_{2}, \ldots, x_{n}$ genom s har vi testvariabeln

$$
u=\frac{\left(\bar{x}-\mu_{0}\right) \sqrt{n}}{s} \text {, }
$$

som utfall av den stokastiska variabeln $U=\left(\bar{X}-\mu_{0}\right) \sqrt{n} / s$ fördelad enligt $\mathrm{t}(n-1)$. Vi får då samma test som i fallet med känd $\sigma$ ovan men byter ut $N(0,1)$-kvantilerna $\lambda_{\alpha}$ med $\mathrm{t}(n-1)$-kvantilerna $\mathrm{t}_{\alpha}(n-1)$.

Exempel 4. Antag att en polis vid en nykterhetskontroll utför $n$ oberoende mätningar $x_{1}, x_{2}, \ldots, x_{n}$ av mängden alkohol i utandningsluften. Dessa mätningar har normalfördelade fel med standardavvikelse $\sigma=0.20$. Vi kan då se dessa som utfall av oberoende stokastiska variabler $X_{1}, X_{2}, \ldots, X_{n}$ fördelade enligt $\mathrm{N}(\mu, \sigma)$. Gränsen för rattfylla går vid $\mu=0.10$ milligram alkohol per liter (detta motsvarar ungefär $0.2$ promille $i$ blodet). Vi vill alltså testa nollhypotesen $H_{0}: \mu=0.10$ (oskyldig till rattfylleri) mot $H_{1}: \mu>0.10$ (skyldig) med signifikansnivån $\alpha=0.001$. Med denna låga nivå riskerar vi alltså att felaktigt förkasta nollhypotesen (dvs. att vi finner någon skyldig till rattfylleri som inte är skyldig) i genomsnitt en gång per tusen.

Enligt metoden ovan har vi då testvariabeln

$$
u=\frac{(\bar{x}-0.10) \sqrt{n}}{0.2}
$$

som vi använder för att förkasta nollhypotesen om $u \geq \lambda_{0.001} \approx 3.09$. Detta ger då styrkefunktionen

$$
\begin{aligned}
h(\mu) &=P(U \geq 3.09 ; \mu)=P\left(\frac{(\bar{X}-0.1) \sqrt{n}}{0.2} \geq 3.09 ; \mu\right) \\
&=P\left(\frac{(\bar{X}-\mu) \sqrt{n}}{0.2}+\frac{(\mu-0.1) \sqrt{n}}{0.2} \geq 3.09 ; \mu\right) \\
&=P\left(\frac{(\bar{X}-\mu) \sqrt{n}}{0.2} \geq 3.09-\frac{(\mu-0.1) \sqrt{n}}{0.2} ; \mu\right) \\
&=1-\Phi\left(3.09-\frac{(\mu-0.1) \sqrt{n}}{0.2}\right)
\end{aligned}
$$

eftersom $(\bar{X}-\mu) \sqrt{n} / 0.2 \sim N(0,1)$ för parametervärdet $\mu$.

![](https://cdn.mathpix.com/cropped/2022_11_17_ff4659224c300ab7f60eg-8.jpg?height=456&width=783&top_left_y=2095&top_left_x=606)

Vi ser att styrkefunktionens utseende kan kontrolleras med hjälp av $n$. Om $n$ är litet blir det en svagt växande funktion av $\mu$. Med andra ord kommer vi inte alltid att förkasta $H_{0}$ (dvs. vi kommer inte finna personen skyldig) även om vi borde (för att $\mu>0.1$ ). Genom att ta ett större $n$ (dvs. att göra fler mätningar) kan vi öka styrkan på testet genom att öka sannolikheten att fälla skyldiga personer.

Avslutningsvis noterar vi att vi kan bilda approximativa hypotesttest genom tillämpning av centrala gränsvärdessatsen. Antag att vi har en punktskattning $\theta_{\text {obbs }}^{\star}$ vars stickprovsvariabel $\theta^{\star}$ kan visas vara approximativt normalfördelad. Om vi vidare antar att standardavvikelsen $D$ är känd (dvs. beror på $\theta_{0}$ ) kan vi bilda testvariabeln

$$
u=\frac{\theta_{\mathrm{obs}}^{\star}-\theta_{0}}{D}
$$

och använda samma förfarande som ovan. Om standardavvikelsen måste skattas ifrån data ersätter vi $D$ i formeln ovan med denna skattning $d$. Låt oss tillämpa detta på opinionsundersökningsexemplet från tidigare föreläsningar.

Exempel 5. Vi har alltså $X \sim \operatorname{Bin}(1000, p)$ med utfallet $x=450$ och är intresserade av att skatta $p$. Nollhypotesen $H_{0}$ är att $p=1 / 2$, dvs. det väger jämt i den röstberättigade populationen mellan ja och nej i frågan. Mothypotesen är $H_{1}: p<1 / 2, d v s$. att färre personer stödjer ja-sidan jämfört med nej-sidan.

Vi har vår punktskattning $p_{\text {obs }}^{\star}=x / n$ med tillhörande stickprovsvariabel $p^{\star}=X / n$. Eftersom $n$ är stort har vi att $X$ är approximativt normalfördelat och $p^{\star}$ likaså. $V i$ vet att $\mathrm{E}\left[p^{\star}\right]=p$ och $\mathrm{D}\left[p^{\star}\right]=\sqrt{p(1-p) / n}$, så vi har då att $p^{\star}$ är approximativt $N(p, \sqrt{p(1-p) / n})$-fördelat.

Vi bildar då testvariabeln

$$
u=\frac{p_{\mathrm{obs}}^{\star}-1 / 2}{d},
$$

där $d=\sqrt{p_{\text {obs }}^{\star}\left(1-p_{\text {obs }}^{\star}\right) / n}$ är standardfelet för skattningen. Under antagandena ovan för stora $n$ är $U=\left(p^{\star}-1 / 2\right) / d$ approximativt $N(0,1)$-fördelat, så vi har testet

Förkasta $H_{0}: p=1 / 2$ till förmån för $H_{1}: p<1 / 2$ om $u<-\lambda_{\alpha}$, dvs. om $p_{\text {obs }}^{\star}<1 / 2-\lambda_{\alpha} d$

I vårt fall hade vi $p_{\text {obs }}^{\star}=0.45$ och $d \approx 0.016$, vilket ger att vi förkastar $H_{0}$ på signifikansnivån $\alpha=0.01$ om $0.45<0.50-2.33 \cdot 0.016=0.463$. Vi förkastar alltså $H_{0}: p=1 / 2$ till förmån för $H_{1}: p<1 / 2$ och kan dra slutsatsen att det troligtvis inte finns tillräckligt många ja-väljare för att ge majoritet vid en folkomröstning.