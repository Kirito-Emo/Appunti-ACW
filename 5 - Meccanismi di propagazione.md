# 5.1 - Onde piane
Finora è stato osservato il comportamento, nella regione di campo lontano, del campo elettrico e magnetico irradiati dalle antenne

$$
\begin{gather}

\underline{E}(r, θ, Φ) = -j \frac{β_0 ζ_0}{4π} \frac{e^{-j β_0 r}}{r} [N_θ(θ, Φ) \hat{θ} + N_Φ(θ, Φ) \hat{Φ}]
\tag*{Campo elettrico}

\\
\\

\underline{H}(r, θ, Φ) = \frac{1}{ζ_0} \hat{r} \times \underline{E}(r, θ, Φ)
\tag*{Campo magnetico}

\\
\\

\underline{S}(r, θ, Φ) = \frac{|\underline{E}(r, θ, Φ)|^2}{2 ζ_0} \hat{r}
\tag*{Vettore di Poynting}

\end{gather}
$$

Dall'antenna trasmittente partono infiniti raggi irradiati.
Si consideri un punto di osservazione (il punto rosso nella figura sottostante), situato nella Far Field region, dove sarà posta l'antenna ricevente o un ostacolo.
Tutti i raggi che collegano la trasmittente e il punto, che cadono nell'intorno (zona blu in figura) del punto di osservazione, possono essere considerati tra loro paralleli. <br>
![[Onde piane.png]] <br>
Il caso in analisi riguarda la **propagazione di onde sferiche**, particolarmente difficile da trattare analiticamente. Si sfrutteranno quindi alcune approssimazioni, passando dal problema reale ad uno equivalente, ma ideale, che coinvolge la **propagazione per onde piane**. <br>
Le onde piane, infatti, non esistono dato che presupporrebbero distanze infinite tra sorgente e ricevente, tuttavia il loro studio è utile poiché si propagano per raggi paralleli.
Si parlerà, nello specifico, di onde piane uniformi.

# 5.2 - Onde piane uniformi
Il campo elettrico nella zona di campo lontana può essere espresso come:

$$
\underline{E}(\underline{r}) = \underline{E_0} e^{-j \underline{kr}}
$$

dove
- il termine $\underline{E_0}$ racchiude le informazioni sulla polarizzazione del campo elettrico;
- $\underline{r}$ è il vettore posizione del campo elettrico;
- $\underline{k}$ è il **vettore di propagazione**, un vettore complesso esprimibile come combinazione di due vettori:
	
	$$
	\underline{k} = \underline{β} -j \underline{α}
	$$
	
	dove:
	- $\underline{β}$ è il **vettore di fase**: $\underline{β} = β \hat{β}$, con $β$ *costante di fase (reale)* e $\hat{β}$ *direzione della variazione di fase*;
	- $α$ è il **vettore di attenuazione**: $\underline{α} = α \hat{α}$, con $α$ *costante di attenuazione* e $\hat{α}$ *direzione dell'attenuazione*.
Un'onda piana si dice **uniforme** quando $\underline{α}$ e $\underline{β}$ sono tra loro paralleli e si dirà che $\underline{α}$ è diretto lungo $\hat{β}$.

## 5.2.1 - Campo elettrico e magnetico di onde piane uniformi
Un’onda piana si dice quindi uniforme quando $\underline{α} = α \hat{β}$. Potremo quindi scrivere il campo elettrico come:

$$
\underline{E}(\underline{r}) = \underline{E}_0 e^{-j (β - jα) \hat{β} \cdot \underline{r}} = \underline{E}_0 e^{-j k \hat{β} \cdot \underline{r}} = \underline{E}_0 e^{-α \hat{β} \cdot \underline{r}} e^{-j β \hat{β} \cdot \underline{r}}
$$
<br> dove
- $k$ è la **costante di propagazione** o numero d'onda:
	
	$$
	k = β -j α = ω_0 \sqrt{μ ε_{eq}}
	$$

Il campo elettrico potrà essere riscritto come:
$$
\underline{H}(\underline{r}) = \underline{H}_0 e^{-j k \hat{β} \cdot \underline{r}} = \frac{1}{ζ} \hat{β} \times \underline{E}_0 e^{-j k \hat{β} \cdot \underline{r}} \equiv \frac{1}{\sqrt{μ/ε_{eq}}} \hat{β} \times \underline{E}_0 e^{-j k \hat{β} \cdot \underline{r}}
$$

Il campo magnetico ha una struttura identica a quella dell'elettrico. Il vettore $H_0$, che dipende dal punto di osservazione, può essere scritto in funzione del vettore $E_0$, dove $ζ$ è l'impedenza intrinseca del mezzo di propagazione.
In generale, dunque anche nel caso di trasmissione con perdite, l'impedenza può essere riscritta come in formula, dove $μ$ e $ε$ sono rispettivamente la *permeabilità dello spazio libero* e *costante dielettrica complessa*.
Mentre, nel caso di propagazione senza perdite (σ = 0) risulta:

$$
α = 0 \hspace{10mm} \text{e} \hspace{10mm} k = β = ω_0 \sqrt{με}
$$

Il prodotto vettoriale ci dice che campo elettrico, magnetico e versore $β$ sono tra loro perpendicolari, questa terna ha nello spazio sempre la stessa configurazione.
Il **prodotto tra campo elettrico e magnetico fornisce sempre la direzione di fase** (che si scoprirà essere proprio la direzione di propagazione).

## 5.2.2 - Vettore di Poynting di onde piane uniformi

$$
\underline{S}(\underline{r}) = \frac{1}{2} \underline{E}(\underline{r}) \times \underline{H}^*(\underline{r}) = \frac{1}{2} [\underline{E}_0 e^{-j k \hat{β} \cdot \underline{r}}] \times [\frac{1}{ζ} \hat{β} \times \underline{E}_0 e^{-j k \hat{β} \cdot \underline{r}}]^* = \frac{|\underline{E}_0|^2}{2 ζ^*} e^{-2 α \hat{β} \cdot \underline{r}} - \hat{β} = S(\underline{r})\hat{β}
$$

Si noti che il vettore di Poynting è diretto nella direzione di $\hatβ$, dunque si può affermare che **in una propagazione piana uniforme $\hatβ$ identifica la direzione di Poynting**.
In assenza di perdite, la costante di attenuazione è uguale a quella di fase, per cui il termine esponenziale diventa 1  ($e^{-2 α \hat{β} \cdot \underline{r}} = 1$) e l'impedenza intrinseca risulta puramente reale.

# 5.3 - Riflessione e Trasmissione delle onde piane
A differenza del caso trattato nel Paragrafo [[#5.1 - Onde piane]], in cui i raggi sono paralleli solo localmente (ovvero solo nell'intorno del punto di osservazione) **nel caso di onde piane uniformi i vettori sono sempre paralleli**, indipendentemente dalla distanza rispetto al punto di osservazione.
Il formalismo delle onde piane consente di  risolvere localmente il caso di incontro con un ostacolo durante la propagazione del segnale. L'ostacolo, nel mondo reale, può avere le forme più disparate.
Si lavorerà con ipotesi per le quali l'**ostacolo ha larghezza, lunghezza e spessore infiniti**. Ciò significa che esso occupa un semispazio e la superficie di separazione tra i **due semispazi** sarà una superfice piana: in un semispazio viaggerà l'onda che si propaga, mentre l’altro semispazio è interamente un ostacolo). Quando il segnale incontra l'ostacolo si verificano i fenomeni di **riflessione e trasmissione**.
La riflessione avviene nello stesso spazio in cui l'onda incidente sta viaggiando, mentre l'onda trasversa viaggia all'interno dell'ostacolo, dunque, la propagazione non avviene in un solo mezzo, come ipotizzato nella formula di Friis, ma in più mezzi. <br>
Quando un'onda piana uniforme è incidente su un confine piano tra due mezzi con permeabilità e permittività diverse,  vengono prodotte due nuove onde, le quali hanno i loro vettori di Poynting nel piano di incidenza contenente sia il vettore di propagazione dell'onda incidente che la normale alla superficie. <br>
![[Riflessione e trasmissione onde piane uniformi.png]] <br>
- Caso a: l'onda piana incide perpendicolarmente sulla superficie dell'ostacolo;
- Caso b: rappresentazione a raggi con incidenza obliqua;
- Caso c: rappresentazione a fronti d'onda con incidenza obliqua.
	> Si ricordi che un fronte d'onda coincide con la direzione piana ed è, pertanto, sempre perpendicolare alla direzione di propagazione.

Per definire il coincide con la direzione piano **piano d'incidenza** nello spazio è necessario conoscere due vettori:
- il **versore $β$** associato all'onda incidente;
- il **versore normale** alla superficie dell'ostacolo.

Come si vedrà, il campo elettrico ha una componente parallela e una perpendicolare al piano d’incidenza:

$$
\underline{E^i}(\underline{r}) = E_{\parallel}^i \widehat{u_{\parallel}} + E_{\perp}^i(\underline{r}) \widehat{u_{\perp}}
$$

In problema tridimensionale sarà quindi scomposto in due problemi bidimensionali, di cui le soluzioni verranno infine unite per ottenere quella finale.

# 5.4 - Confine tra due mezzi lossless e Leggi di Snell
Nel mezzo $1$ dove l’onda si propaga, si hanno i campi elettrico e magnetico incidenti e riflessi, mentre nel mezzo di cui è composto l’ostacolo (mezzo $2$), si avranno soltanto campi elettrico e magnetico trasmesso.

$$
\begin{multline}

\underline{E}_1 = \underline{E}^i + \underline{E}^r = \underline{E}^i_0 e^{-j \underline{β}^i \cdot \underline{r}} + \underline{E}_0^r e^{-j \underline{β}^r \cdot \underline{r}}

\hspace{20mm}

\underline{H}_1 = \underline{H}^i + \underline{H}^r = \underline{H}^i_0 e^{-j \underline{β}^i \cdot \underline{r}} + \underline{H}_0^r e^{-j \underline{β}^r \cdot \underline{r}}

\\
\\

\underline{E}_2 = \underline{E}^t = \underline{E}_0^t e^{-j \underline{β}^t \cdot \underline{r}}

\hspace{50mm}

\underline{H}_2 = \underline{H}^t = \underline{H}_0^t e^{-j \underline{β}^t \cdot \underline{r}}

\hspace{40mm}

\end{multline}
$$

Si supponga che **entrambi i mezzi siano senza perdite** (dunque che $𝛽 = 𝜔_0 \sqrt{𝜇𝜀}$, con $ε$ reale) e che nell'ostacolo non ci siano cariche libere né altre componenti elettriche (quest’ultima ipotesi permette di imporre la continuità delle componenti tangenziali dei due campi), in tali ipotesi valgono le **leggi di Snell**.

## 5.4.1 - Legge della riflessione di Snell
La **legge di Snell per la riflazione (o riflessione)** nasce dall'uguaglianza:

$$
β_1 \sin{θ}^i = β_1 \sin{θ}^r \hspace{10mm} \rightarrow \hspace{10mm} θ^r = θ^i
$$

dove:
- $θ^i$ è l'angolo formato tra la direzione di incidenza $β^i$ e la normale alla superficie. $θ^i$ ha una variabilità compresa tra $0°$ e $90°$. Quando $θ^i = 0°$ si verifica una condizione di incidenza normale dove il segnale arriva in modo perpendicolare all'ostacolo; quando, invece, $θ^i = 90°$ il segnale arriva all'ostacolo in *radenza*;
- $θ^r$ è l'angolo che il versore $β_r$ forma con la normale alla superficie;
- $β_1$ è la costante di fase del mezzo $1$ da cui arriva il segnale.

L'uguaglianza dei due seni impone che l'angolo di riflessione $θ^r$ deve essere uguale all'angolo di incidenza $θ^i$.
Scrivere $θ^r = θ^i$ significa che il segnale incidente viene riflesso nel mezzo $1$ in maniera speculare.

## 5.4.2 - Legge della rifrazione di Snell
La **legge di Snell per la rifrazione (o trasmissione)** afferma:

$$
β_1 \sin{θ}^i = β_2 \sin{θ}^t \hspace{10mm} \rightarrow \hspace{10mm} \sin{θ^t} = \frac{\sqrt{μ_1 ε_1}}{\sqrt{μ_2 ε_2}} \sin{θ^i} = \frac{n_1}{n_2} \sin{θ^i}
$$

dove
- $θ^t$ è determinato analogamente ai due angoli della formula precedente;
- $β_2$ è la costante di fase del mezzo $2$;
- $n_1$ e $n_2$ sono gli **indici di rifrazione**.

Il coefficiente di rifrazione di ogni mezzo è calcolato in relazione al vuoto:

$$
n = \frac{\sqrt{με}}{\sqrt{μ_0 ε_0}} = \sqrt{μ_r ε_r}
$$

Poiché il mezzo $2$ è un mezzo senza perdite (lossless) si può riscrivere $β$ come:

$$
β = ω_0 \sqrt{με}
$$


# 5.5 - Polarizzazione parallela e perpendicolare
Nella trattazione del problema tridimensionale, si ha la possibilità di semplificarlo dividendolo in due sotto-problemi bidimensionali:
- uno associato alla componente parallela del campo elettrico rispetto al piano di incidenza (**polarizzazione parallela**) e
- uno associato alla componente perpendicolare del campo elettrico rispetto al piano di incidenza (**polarizzazione perpendicolare**).

## 5.5.1 - Polarizzazione parallela
La polarizzazione parallela si ha quando il campo elettrico ha solo la componente $E_{\parallel}^i$, quindi **giace sul piano di incidenza**.
Dopo aver definito il piano di incidenza si può scegliere un sistema di riferimento, in cui:
- l’asse $x$ è parallelo alla superficie dell’ostacolo;
- l’asse $z$ è lungo la direttrice normale alla superficie dell’ostacolo e punta all’interno dell’ostacolo stesso;
- l’asse $y$ è uscente dal piano di incidenza.

L’intero sistema di riferimento è centrato nel punto di impatto del raggio incidente. <br>
![[Polarizzazione parallela.png]] <br>
In questo particolare tipo di polarizzazione assumiamo che tutti e tre i **vettori di campo magnetico** (incidente, riflesso e trasmesso) **siano uscenti dal piano di incidenza**. <br>
In questo modo la direzione e il verso dei vettori di campo elettrico sono univocamente determinati, poiché dipendenti dalla scelta effettuata per il campo magnetico. <br>
Considerando l’espressione dei vettori campo elettrico incidente, trasmesso e riflesso;, si può notare che questi sono caratterizzati dall’ampiezza (ovviamente scalare) e dalle componenti vettoriali lungo x e z:

$$
\begin{gather}

\underline{E}_0^i = E_0^i (\cos{θ^i} \hat{x} - \sin{θ^i} \hat{z})

\\
\\

\underline{E}_0^r = - E_0^r (\cos{θ^i} \hat{x} - \sin{θ^i} \hat{z})

\\
\\

\underline{E}_0^t = E_0^t (\cos{θ^t} \hat{x} - \sin{θ^t} \hat{z})

\end{gather}
$$

### 5.5.1.1 - Coefficienti di Fresnel
In particolare, possiamo determinare $E_0^r$ rispetto a $E_0^i$ attraverso il **coefficiente di riflessione parallelo** $Γ_{\parallel}$, così come possiamo determinare $E_0^t$ in relazione a $E_0^i$ tramite il **coefficiente di trasmissione parallelo** $τ_{\parallel}$.

$$
Γ_{\parallel} = \frac{E_0^r}{E_0^i} \hspace{50mm} τ_{\parallel} = \frac{E_0^t}{E_0^i}
$$

Questi due coefficienti, per la polarizzazione parallela, vengono valutati secondo le due **relazioni di Fresnel**.
___
#### Coefficiente di riflessione di Fresnel

$$
Γ_{\parallel} = \frac{ζ_1 \cos{θ^i} - ζ_2 \cos{θ^t}} {ζ_1 \cos{θ^i} + ζ_2 \cos{θ^t}}
$$
___
#### Coefficiente di trasmissione di Fresnel

$$
τ_{\parallel} = \frac{2 ζ_2 \cos{θ^i}} {ζ_1 \cos{θ^i} + ζ_2 \cos{θ^t}}
$$
___
Dove $ζ_1$ e $ζ_2$ rappresentano l'impedenza intrinseca dei due mezzi.
Poiché entrambi sono senza perdite, sia $ζ_1$ che $ζ_2$ sono reali, dunque anche i coefficienti di riflessione e trasmissione risultano reali.

> ATTENZIONE!
> Se si cambia la configurazione dei vettori, le suddette formule non saranno più utilizzabili

## 5.5.2 - Polarizzazione perpendicolare
La polarizzazione perpendicolare si ha quando il campo elettrico ha solo la componente $E_{\perp}^i$, cioè quando è perpendicolare al piano di incidenza. <br>
![[Polarizzazione perpendicolare.png]] <br>
In questo caso si sceglie il verso uscente per i vettori campo elettrico incidente, riflesso e trasmesso. In questo modo saranno direzione e verso del campo magnetico ad essere determinate di conseguenza. <br>
In questa particolare polarizzazione il campo elettrico ha solo componenti lungo y.

$$
\begin{gather}

\underline{E}_0^i = E_0^i \hat{y}

\\
\\

\underline{E}_0^r = - E_0^r \hat{y}

\\
\\

\underline{E}_0^t = E_0^t \hat{y}

\end{gather}
$$

Anche qui, analogamente con quanto effettuato nel caso parallelo, per legare $E_0^r$ a $E_0^i$ e $E_0^t$ a $E_0^i$:

$$
Γ_{\perp} = \frac{E_0^r}{E_0^i} \hspace{50mm} τ_{\perp} = \frac{E_0^t}{E_0^i}
$$

### 5.5.2.1 - Coefficienti di Fresnel
___
#### Coefficiente di riflessione di Fresnel

$$
Γ_{\perp} = \frac{ζ_2 \cos{θ^i} - ζ_1 \cos{θ^t}} {ζ_2 \cos{θ^i} + ζ_1 \cos{θ^t}}
$$
___
#### Coefficiente di trasmissione di Fresnel

$$
τ_{\perp} = \frac{2 ζ_2 \cos{θ^i}} {ζ_2 \cos{θ^i} + ζ_1 \cos{θ^t}}
$$
___

# 5.6 - Angolo di Brewster
L'angolo di incidenza è detto angolo di Brewster $θ_B$ quando il **coefficiente di riflessione è uguale a $0$**.
L'angolo di Brewster esiste solo per la **polarizzazione parallela** nel caso di mezzi **non magnetici**, cioè mezzi la cui permeabilità $𝜇$ è uguale a quella del vuoto. <br>
![[Angolo di Brewster.png]] <br>
In figura sono rappresentati tre possibili andamenti del coefficiente di riflessione. <br>
Sia $mezzo \hspace{2mm} 1$ il mezzo di provenienza del segnale, e $mezzo \hspace{2mm} 2$ il mezzo in cui il segnale si trasmette.
Nei tre casi in esame il primo mezzo è sempre l’aria, mentre il secondo mezzo è acqua, terreno bagnato e terreno secco, rispettivamente per il primo, secondo e terzo caso.
I tre mezzi sono non magnetici, infatti la loro permeabilità magnetica è uguale a quella del vuoto e si differenziano soltanto per il valore della loro costante dielettrica.

- Nel primo caso (aria-acqua) il coefficiente di riflessione parte da un valore di $0.8$ per $θ^i = 0$, per poi diminuire all’aumentare di $θ^i$ fino a raggiungere il valore $0$ per $θ^i = 84°$ (angolo di Brewster) e successivamente aumentare per $θ^i > 84°$.

- Per il secondo caso (aria-terreno bagnato) ed il terzo (aria-terreno secco) si ha un angolo di Brewster rispettivamente a $θ^i = 79°$ e $θ^i = 60°$.

Si noti come a valori inferiori di epsilon corrispondano apparizioni dell’angolo di Brewster per angoli minori.

# 5.7 - Angolo critico
L’angolo d’incidenza è detto **angolo critico $θ^c$** quando per $θ^t = π/2$ si ha $Γ_{\parallel} = Γ_{\perp} = 1$. L’angolo critico è, per meglio specificare, quello per il quale si verifica il fenomeno di riflessione totale (e trasmissione nulla). <br>
Per capire cosa accade per $θ^t =π/2$ analizziamo tre casistiche. <br>
![[Angolo critico.png]] <br>

## 5.7.1 - Caso A

$$
β_1 < β_2 \hspace{5mm} \rightarrow \hspace{5mm} n_1 < n_2 \hspace{5mm} \rightarrow \hspace{5mm} \sqrt{μ_1 ε_1} < \sqrt{μ_2 ε_2}
$$

La seconda legge di Snell afferma che:

$$
β_1 \sin{θ^i} = β_2 \sin{θ^t}
$$

Per cui, se $β_1 < β_2 \hspace{3mm} \rightarrow \hspace{3mm} θ^i > θ^t$:
- $θ^i$ può variare fino a $90°$;
- $θ^t$, che è sempre inferiore, non potrà mai arrivare a $90°$.

Dunque, **nel caso a non esiste angolo critico**, tutto funziona ordinariamente, ovvero si propagano onde piane uniformi.

## 5.7.2 - Caso B
Si ha una situazione opposta al caso A, cioè:

$$
n_1 > n_2
$$

Applicando la **seconda legge di Snell** la disuguaglianza sugli angoli diventa:

$$
θ^i < θ^t
$$

ovvero, al crescere di $θ^i$, $θ^t$ cresce ancor più velocemente. <br>
In questo caso esiste l'angolo critico.
Quando l’angolo $θ^i$ raggiunge il valore che porta $θ^t$ a $90°$ (caso C), $θ^i$ è proprio uguale all’angolo critico $θ^c$.

## 5.7.3 - Caso C

$$
θ^i = θ^c
$$

Si propaga un'onda piana uniforme parallela alla linea che separa le due superfici.
Poiché $θ^t = π/2$, si avrà $Γ_{\parallel} = Γ_{\perp} = 1$.

# 5.8 - Riflettività e Trasmittività
Sia considerata una zona limitata di superficie dell'ostacolo e si indichi con $A$ la sua area. Si considerino, poi, i vettori di Poynting dell'onda trasmessa, riflessa e incidente. <br>
![[Riflettività e trasmittività.png]] <br>
La potenza del segnale incidente si calcola integrando il flusso del vettore di Poynting associato all'onda incidente:

$$
P^i = \int{\int{\frac{|\underline{E}_0^i|^2}{2ζ_1} \hat{β}^i \cdot \hat{z} \hspace{2mm} dS}}
$$

con $ζ$ impedenza intrinseca del mezzo. <br>
Coerentemente alla sua propagazione, il versore normale, attraverso 
cui valutare il flusso, è il versore $z$, il quale è perpendicolare alla superficie ed entrante nell'ostacolo. <br>
Si supponga ora, che la superficie sia così piccola che per ogni suo punto si ha uguale densità di potenza, in tal caso si può portare la *densità* fuori dall'integrale. <br>
L'integrale di $S$ su $dS$ è proprio uguale all'area della superficie, per cui si ha:

$$
P^i = \int{\int{\frac{|\underline{E}_0^i|^2}{2ζ_1} \hat{β}^i \cdot \hat{z} \hspace{2mm} dS}} = \frac{|\underline{E}_0^i|^2}{2ζ_1} A \cos{θ^i}
$$

Per quanto riguarda l'onda riflessa, la sua potenza si calcolerà allo stesso identico modo (per la **prima legge di Snell** $θ^i = θ^r$):

$$
P^r = \frac{|\underline{E}_0^r|^2}{2 ζ_1} A \cos{θ^r}
$$

Mentre per la potenza trasmessa si avrà:

$$
P^t = \frac{|\underline{E}_0^t|^2}{2 ζ_2} A \cos{θ^t}
$$

Rapportando potenza riflessa e incidente si ottiene:

$$
\begin{multline}

R = \frac{P^r}{P^i} = \frac{|\underline{E}_0^r|^2}{|\underline{E}_0^i|^2} = |Γ|^2

\\
\\

\tag*{Coefficiente di riflessione per la potenza: Riflettività}

\end{multline}
$$
___
Rapportando potenza trasmessa e incidente si ottiene:

$$
\begin{multline}

T = \frac{P^t}{P^i} = \frac{|\underline{E}_0^t|^2}{|\underline{E}_0^i|^2} \frac{ζ_1}{ζ_2} \frac{\cos{θ^t}}{\cos{θ^i}} = |τ|^2 (\frac{ζ_1 \cos{θ^t}}{ζ_2 \cos{θ^i}})

\\
\\

\tag*{Coefficiente di trasmissione per la potenza: Trasmittività}

\end{multline}
$$

che è pari al modulo quadro del coefficiente di trasmissione per la polarizzazione perpendicolare in caso di polarizzazione perpendicolare (rispettivamente per la polarizzazione parallela in caso di polarizzazione parallela). <br>
Inoltre, per il principio di conservazione della potenza, tutta la potenza incidente diviene potenza riflessa e/o potenza trasmessa:

$$
P^i = P^r + P^t \hspace{10mm} \rightarrow \hspace{10mm} R + T = 1
$$

# 5.9 - Esempio di due mezzi non magnetici
Nel caso con due mezzi non magnetici (*aria e vetro* con *indici di rifrazione 0.5*) sono riportate le curve di trasmissività e riflettività nel caso di polarizzazione parallela. <br>
![[Due mezzi non magnetici (aria-vetro).png]] <br>
La riflettività parte da un valore $0.05$ decresce fino all'angolo di Brewster e poi risale. L’opposto accade per la trasmissività.
Si noti che, poiché $n_1 < n_2$, non esiste angolo critico.

# 5.10 - Confine tra mezzo senza perdite e conduttore


## 5.10.1 - Campo elettrico e magnetico se il mezzo 2 è un conduttore
Verrà ora analizzato il caso in cui il mezzo $2$ ha delle perdite di tipo elettrico (costante dielettrica complessa):
- nel mezzo 1 non cambia nulla (continua ad essere un mezzo senza perdite);
- nel mezzo 2 le espressioni di campo elettrico e magnetico cambiano (le onde piane non sono più uniformi).

$$
\begin{multline}

\underline{E}_1 = \underline{E}_0^i e^{-j \underline{β}^i \cdot \underline{r}} + \underline{E}_0^r e^{-j \underline{β}^r \cdot \underline{r}}

\hspace{50mm}

\underline{H}_1 = \underline{H}_0^i e^{-j \underline{β}^i \cdot \underline{r}} + \underline{H}_0^r e^{-j \underline{β}^r \cdot \underline{r}}

\\
\\

\underline{E}_2 = \underline{E}_0^t e^{-j \underline{k}^t \cdot \underline{r}}

\hspace{80mm}

\underline{H}_2 = \underline{H}_0^t e^{-j \underline{k}^t \cdot \underline{r}}

\hspace{60mm}

\\
\\

\underline{k}^t = \underline{β}^t - j \underline{α}^t

\hspace{120mm}

\end{multline}
$$

### 5.10.1.1 - Campo elettrico e magnetico nel mezzo 1
I termini $E_0^i$, $E_0^r$, $H_0^i$, $H_0^r$ forniscono informazioni sulla ampiezza del segnale e sulla sua polarizzazione (rispettivamente del segnale incidente e del segnale riflesso).

### 5.10.1.2 - Campo elettrico e magnetico nel mezzo 2
Il vettore di propagazione $k$ è ora non uguale a $β$, ma ad una combinazione lineare di $α$ 𝑒 $β$, ossia subisce un'attenuazione. <br>
Nel mezzo 2 si avrà quindi un vettore di propagazione $k$ caratterizzato da un vettore di fase e uno di attenuazione non allineati, ossia l'onda piana che si propaga è non uniforme.

### 5.10.1.3 - Differenza tra onde piane uniformi e non uniformi
L'onda piana uniforme, pur ammettendo perdite (cioè anche se si propaga in un mezzo con perdite) mantiene allineati i vettori di fase e attenuazione; in un'onda piana non uniforme il segnale si propaga in una direzione e si attenua in un'altra.

## 5.10.2 - Leggi di Snell se il mezzo 2 è un conduttore
**Le leggi di Snell continuano a valere**:
- la legge di riflessione è invariata dato che interessa il mezzo 1;
- la legge per la rifrazione vede:
	- un primo termine invariato (quello che riguarda il primo mezzo) e
	- un termine $k_2$ variato, perché ora influenzato dalle costanti $β_2$ e $α_2$.

### 5.10.2.1 - Legge di riflessione di Snell

$$
θ^r = θ^i
$$

### 5.10.2.2 - Legge di rifrazione di Snell

$$
β_1 \sin{θ^i} = k_2 \sin{θ^t} = ω_0 \sqrt{μ_2 ε_{2_{eq}}} \sin{θ^t} = (β_2 - j α_2) \sin{θ^t}
$$

Il primo membro della seconda legge di Snell è quindi ==reale==, mentre il secondo membro vede due termini:
- $k_2$ che, come si è già detto, è complesso;
- $\sin{θ^t}$ che deve essere anch’esso complesso affinché $k_2 \sin{θ^t}$ risulti reale.

Questo fa sì che $θ^t$ risulti essere un angolo complesso, quindi non geometricamente individuabile. Ossia $θ^t$ perde il suo significato geometrico di angolo di rifrazione.
È dimostrabile che $α$ risulta essere diretto, come l'asse $z$, perpendicolarmente alla superficie dell'ostacolo, dunque l'angolo tra il vettore di fase e quello di attenuazione prende il posto di $θ^t$, divenendo il nuovo angolo di rifrazione.

## 5.10.3 - Coefficienti di Fresnel se il mezzo 2 è un conduttore
Le formule dei coefficienti di Fresnel rimangono le stesse, seppur con una precisazione necessaria:

$$
\begin{multline}

Γ_{\parallel} = \frac{ζ_1 \cos{θ^i} - ζ_2 \cos{θ^t}} {ζ_1 \cos{θ^i} + ζ_2 \cos{θ^t}}

\hspace{50mm}

τ_{\parallel} = \frac{2 ζ_2 \cos{θ^i}} {ζ_1 \cos{θ^i} + ζ_2 \cos{θ^t}}

\\
\\

Γ_{\perp} = \frac{ζ_2 \cos{θ^i} - ζ_1 \cos{θ^t}} {ζ_2 \cos{θ^i} + ζ_1 \cos{θ^t}}

\hspace{50mm}

τ_{\perp} = \frac{2 ζ_2 \cos{θ^i}} {ζ_2 \cos{θ^i} + ζ_1 \cos{θ^t}}

\hspace{60mm}

\end{multline}
$$

Mentre i termini contenenti $θ^i$ e $ζ_1$ non cambiano ($ζ_1$ continua ad essere reale e $θ^i$ è invariata), $ζ_2$ e $θ^t$ divengono complessi.
$ζ_2$ si calcola, in caso di perdite, nel seguente modo:

$$
\sqrt{μ / ε_{eq}}
$$

con epsilon complessa.
Cioè: le formule dei coefficienti di riflessione e trasmissione continuano a valere, ma $ζ_2$ è ora complessa e $θ^t$ dà luogo ad un coseno complesso.

## 5.10.4 - Riflettività e Trasmittività
Per semplificare il calcolo di $T$, si calcolerà prima $R$ e poi $T$ in sua funzione, attraverso la legge di conservazione della potenza:

$$
R = |Γ|^2 \hspace{80mm} T = 1 - R = 1 - |Γ|^2
$$

# 5.11 - Confine tra conduttore e PEC
La situazione limite si ha quando la **conducibilità ($σ$) del mezzo con perdite magnetiche tende ad infinito**. Questa situazione richiama la condizione detta **PEC (conduttore elettrico perfetto)**.
> Dal punto di vista applicativo, i metalli, ad alte frequenze, si comportano come PEC.

Se lo spessore del conduttore è rilevante, questo può essere in grado addirittura di bloccare completamente la propagazione del segnale (nel caso ideale di una struttura PEC infinita). <br>
Il caso limite vede anche un'impedenza caratteristica tendente a $0$: $ζ_2 \rightarrow 0$. <br>
Per cui i coefficienti di Fresnel saranno:

## 5.11.1 - Coefficienti di riflessione e trasmittività di Fresnel 

$$
\begin{gather}

Γ_{\parallel} = 1 \hspace{50mm} τ_{\parallel} = 0

\\
\\

Γ_{\perp} = -1 \hspace{50mm} τ_{\perp} = 0

\end{gather}
$$

Ciò significa che **non c'è raggio trasmesso** ma soltanto **riflesso**: **un mezzo PEC funge perfettamente da specchio** (proprio per questo risulta essere un conduttore elettrico perfetto, al suo interno non c'è alcun campo elettro-magnetico).

La differenza rispetto al caso di riflessione totale è che:
- con la riflessione totale: $Γ_{\parallel} = Γ_{\perp} = 1$
- nel caso PEC: $Γ_{\parallel} = Γ_{\perp} = -1$.

# 5.12 - Lastra lossless
Si consideri ora il caso in cui si elimina l'ipotesi di spessore infinito dell'ostacolo mantenendo, però, lunghezza e larghezza infinite. <br>
Adesso si possono quindi considerare **due superfici dell'ostacolo**:
- quella toccata dall'onda incidente (dove l'onda "entra");
- quella dove l'onda si trasmette (dove l'onda "esce").

Si analizzerà il caso di un ostacolo senza perdite di spessore $d$. <br>
![[Lastra lossless - 1.png]] <br>
Nella figura sopra adiacente è rappresentata la situazione del piano di incidenza. <br>
Mentre per i mezzi $1$ e $3$ si assumono le stesse caratteristiche del vuoto, il mezzo $2$ sarà caratterizzato da una permeabilità magnetica e una costante dielettrica diverse. <br>
Il raggio incidente tocca la prima superficie e viene riflesso nella direzione speculare con angolo $θ^r$.
Allo stesso tempo viene trasmesso all’interno dello strato con l’angolo $θ^t$ che obbedisce alla seconda legge di Snell applicata alla superficie.
Il segnale che passa nello strato, pesato per un coefficiente di trasmissione, viaggia all’interno dell’ostacolo e incontra la seconda superficie. A questo punto subisce una riflessione all’interno dell’ostacolo stesso con angolo $θ^t$ e una trasmissione nel mezzo $3$ con angolo $θ^i$, ottenuto applicando nuovamente la seconda legge di Snell. <br>
Poiché mezzo $1$ e $3$ hanno le stesse caratteristiche, ==l’angolo di uscita nel mezzo $3$ sarà uguale all’angolo di incidenza nel mezzo $1$.== <br>
La parte del segnale che era stata a sua volta riflessa sulla seconda superficie, viaggia all’interno dell’ostacolo pesato per un coefficiente di riflessione e uno di trasmissione, e viene trasmesso nel mezzo $1$ con angolazione nuovamente $θ^i$ (= $θ^r$). Ciò significa che il segnale riflesso dopo la prima incidenza e il segnale trasmesso dopo la terza incidenza (quella del segnale interno all’ostacolo) hanno la stessa identica angolazione (si sommano). <br>
Questo meccanismo può andare avanti finché la struttura si estende, quindi all’infinito.
Dunque, parleremo di **coefficienti di riflessione e di trasmissione totali, che comprendono tutti gli infiniti contributi**, ottenuti tramite serie geometriche che convergono ad un valore finito.
Il coefficiente di riflessione totale è dato dal rapporto:

$$
Γ_T = \frac{Γ(1 - P_d^2 P_a)}{1 - Γ^2 P_d^2 P_a}
$$

che coinvolge i seguenti termini:
- $Γ$ **coefficiente di prima riflessione**, ovvero il coefficiente che valutiamo alla prima riflessione;
- $P_d$ è un **termine di fase che tiene conto dell’attraversamento dello strato**. Siccome l’ostacolo è un mezzo senza perdite, non c’è attenuazione del segnale, ma solo variazione di fase, rappresentata proprio da questo termine. $P_d$ è a sua volta indicato come:
	
	$$
	P_d = e^{-j β_S d'} = e^{-j β_S d / \cos{θ^t}}
	$$

	dove:
	- $β_S$ è il **coefficiente di fase dello strato** e $d'$ è la **distanza percorsa nell’attraversamento**.

![[Lastra lossless - 2.png]] <br>
- Il termine di fase $P_a$ tiene conto della **differenza di fase tra i due punti in cui segnale impatta con la prima superficie dell’ostacolo** (punto blu e rosso).
	Per semplificarne il calcolo, invece che lavorare col punto in blu, si fa riferimento al punto in verde, che giace sulla direzione di propagazione e ha la stessa fase del punto in blu, poiché entrambi giacciono sul piano perpendicolare alla direzione di propagazione (poiché tutti i punti che si trovano su uno stesso piano (perpendicolare alla direzione di propagazione) sono equi-fase).
	A questo punto si può individuare la differenza di fase considerandola come il cateto di un triangolo rettangolo la cui ipotenusa vale $2d' \sin{θ^t}$ (poiché è il doppio del segmento in verde), ottenendo come risultato finale $2d' \sin{θ^i} \tan{θ^t}$. 
	Per cui si ha:
	
	$$
	P_a = e^{j β_0 2d' \sin{θ^t} \sin{θ^i}} = e^{j β_0 2d \tan{θ^t} \sin{θ^i}}
	$$

- Il termine di fase $P_t$ tiene conto della **differenza di fase tra il punto di primo impatto del segnale e il punto in cui quest’ultimo tocca la seconda superficie dell’ostacolo**. <br>
	![[Lastra lossless - 3.png]] <br>
	Calcolare questa differenza di fase, è esattamente equivalente a calcolare quella in arancione, siccome i punti sul limite destro dei segmenti arancio e rosa giacciono sullo stesso piano perpendicolare alla direzione di propagazione.
	Dunque, calcoleremo la differenza di fase rispetto al segmento arancione, più semplice poiché è il prolungamento del raggio di incidenza.
	Per calcolare tale termine, si osserva che il triangolo di vertici rossi è rettangolo e il suo angolo tra ipotenusa e cateto maggiore è proprio pari a $θ^i - θ^t$.
	Per calcolare il cateto maggiore, che è proprio la differenza di fase che ci interessa, scriveremo: $d' \cos{θ^i - θ^t}$.
	Si ha:
	
	$$
	P_t = e^{j β_0 d' \cos{(θ^i - θ^t)}} = e^{j β_0 d \cos{(θ^i - θ^t)} / \cos{θ^t}}
	$$

Mentre i primi due coefficienti descrivono il passaggio del segnale attraverso i mezzi, l’ultimo tiene conto del fatto che il centro di fase fissato dal punto di primo impatto non ha la stessa fase degli altri punti di impatto

# 5.13 - Ottica geometrica
Tutto quello che abbiamo visto riguardo la propagazione di onde piane risulta essere un’approssimazione, siccome queste ultime non esistono. I risultati ottenuti vengono utilizzati nell’Ottica Geometrica. <br>
L'**Ottica Geometrica (GO)** è un modo semplice per trovare un valore approssimativo del campo del ricevitore utilizzando i meccanismi di propagazione relativi alle onde piane.
**Per poterla applicare è richiesta l'applicazione di una serie di assunzioni**, tutte in riferimento alla lunghezza d’onda del segnale che si sta propagando. <br>
La lunghezza d'onda dev’essere corta rispetto a tutte le seguenti lunghezze: 
1. distanza tra la sorgente e le prime interazioni lungo ciascun raggio;
2. distanza tra le interazioni individuali;
3. dimensioni dei singoli ostacoli;
4. curvature dei confini;

In particolare, l’ottica geometrica sfrutta i risultati delle onde piane in 4 differenti processi:
1. innanzitutto calcola tutti i possibili percorsi dei raggi tra il trasmettitore e i punti di campo coerenti con le leggi di riflessione e rifrazione di Snell (**ray-tracing**);
2. poi **calcola i coefficienti di riflessione e trasmissione di Fresnel** in ciascuno dei punti coinvolti come se le onde incidenti fossero piane e i confini fossero piani e infiniti;
3. in seguito, per ciascun percorso del raggio, **corregge l'ampiezza** per tenere conto della **curvatura del fronte d'onda e della curvatura di eventuali contorni** (cioè s'introduce un fattore correttivo che tiene conto della curvatura del segnale, poiché le onde reali sono sferiche, e degli ostacoli);
4. infine **somma tutti i contributi** del percorso dei raggi, tenendo debitamente conto sia dell'ampiezza che della fase.

## 5.13.1 - I limiti della GO
L'approccio GO porta a previsioni del tutto errate quando si considerano i campi nella **regione d'ombra (shadow region)** dietro un ostacolo, poiché prevede che in tale regione non esista nessun campo. <br>
![[limiti GO.png]] <br>
La presenza del campo elettromagnetico nella regione d'ombra è giustificata da un altro fenomeno ondulatorio: la **diffrazione**.

# 5.14 - Diffrazione
==La **diffrazione** è la *deviazione della propagazione dell'onda* dalla rappresentazione in linea retta usata in ottica geometrica==. La diffrazione ==spiega la curvatura delle onde attorno ai bordi di ostacoli== e può essere compresa più facilmente usando il **principio di Huygen**. <br>
![[Diffrazione - 1.png]] <br>

## 5.14.1 - Principio di Huygens
1. **Ogni elemento di un fronte d'onda** in un determinato momento può essere considerato il **centro di un disturbo secondario**, che dà origine a onde sferiche;
2. la posizione del fronte d'onda in qualsiasi momento successivo è l'**inviluppo di tutte queste onde**.

Si supponga di avere un ostacolo opaco, dove i raggi che lo colpiscono vengono bloccati e il raggio che passa sfiorando il bordo definisce un confine luce-ombra.
Applicando il principio di Huygens: quando il segnale tocca il bordo, il contributo dà luogo a un segnale nella regione d’ombra. <br>
![[Huygen's principle.png]] <br>

# 5.15 - Teoria geometrica della diffrazione
Un approccio che tiene conto dei bordi degli ostacoli estende l’ottica geometrica per includere la diffrazione, ottenendo così la **teoria geometrica della diffrazione (GTD)**, ideata per la prima volta da Keller negli anni '50. <br>
L'idea centrale della GTD è che una versione estesa del **principio di Fermat** (cioè: il collegamento effettivo tra due punti attraversati da un raggio è quello che viene percorso nel minor tempo) può essere utilizzata per prevedere l'esistenza di raggi diffratti, i quali possono quindi essere trattati con la facilità di qualsiasi altro raggio in GO.
Il principio di Fermat per la diffrazione dei bordi prevede che, sul bordo di un ostacolo, un raggio che incide obliquamente generi un cono di raggi diffratti.
In caso di incidenza normale il cono si riduce a disco. <br>
![[GTD.png]] <br>
La formulazione originale di GTD di Keller presentava lo svantaggio di non prevedere correttamente il campo per i punti di campo nella regione di transizione vicino al confine d'ombra. GTD è stato quindi esteso da *Kouyoumjian* e *Pathak* alla **Uniform GTD(UTD)** che si applica in tutti i punti.

## 5.15.1 - Il cono di Keller
Keller notò che nel caso di raggio incidente obliquo sullo spigolo, i raggi diffratti si propagavano lungo coni aventi lo spigolo come asse.
>Il **cono di raggi diffratti** ha preso il nome di **cono di Keller**.

Tale cono è stato determinato sperimentalmente.
Per ogni raggio incidente su un punto dello spigolo, ve ne sono infiniti diffratti lungo le direttrici del cono di Keller.
Tra il raggio incidente proveniente da un punto $S$ e il corrispondente diffratto passante per il punto di osservazione $P$, definendo in corrispondenza del punto di diffrazione un versore tangente allo spigolo ($\hat{e}$), in accordo alla legge della diffrazione, esiste la relazione:

$$
\sin{β_0} = |\hat{s}' \times \hat{e}| = |\hat{s} \times \hat{e}|
$$

### 5.15.1.1 - Caso bidimensionale
Se $β= 90°$ il raggio incidente è ortogonale allo spigolo e il cono di diffrazione degenera in un disco. Per definizione, nel caso 2D tutti i raggi sono ortogonali allo spigolo.

# 5.16 - Uniform GTD
Il problema nella GTD sviluppata da Keller è legato a non aver considerato il raggio di curvatura della superficie che genera il campo diffratto. Questo fa sì che un semipiano completamente piatto ed uno con un assegnato raggio di curvatura finito vengano ad avere lo stesso coefficiente di diffrazione pur comportandosi in modo diverso dal punto di vista del campo elettromagnetico.
La teoria di Keller sicuramente migliora la predizione del campo rispetto all’ottica geometrica, ma rimane singolare in particolare in corrispondenza dei confini di transizione tra le regioni ombra. <br>
![[Uniform GTD.png]] <br>
Nel 1974 *Kouyoumjian* e *Pathak* presentano la teoria uniforme della diffrazione.
Essi mostrarono come, moltiplicando il coefficiente di diffrazione di Keller per un’apposita funzione di transizione, si ottenie un campo di valore finito anche in corrispondenza degli **shadow boundaries**.
Nei punti di singolarità della GTD, la funzione di transizione deve tendere a $0$ con un ordine pari a quello con cui il coefficiente di diffrazione tende ad infinito.
Inoltre, i due studiosi svilupparono un coefficiente di diffrazione in grado di considerare superfici curve.

# 5.17 - Confronto tra i campi previsti dalla GO e i campi reali che tengono conto del contributo del campo UTD
![[GO vs Real Fields - 1.png]] <br>
![[GO vs Real Fields - 2.png]] <br>
Si noti come fino a $150$ gradi (prima della *soglia RSB*), le previsioni della *GO* siano esatte.
Tra i $150$ e i $210$ gradi invece (ZONA_2) la *GO* tiene conto soltanto del contributo del campo incidente.
La *teoria del campo UTD* invece tiene conto anche del contributo di quest’ultimo e fornisce una previsione corretta del campo totale.