Nel campo delle trasmissioni, il compito di un'antenna è quello di percepire un segnale via cavo per poi trasmetterlo, un'altra antenna si occuperà poi di percepire quello stesso segnale e il ricevitore di riconoscerlo nel modo corretto.

Un'antenna è un dispositivo che permette di convertire i campi elettromagnetici guidati in campi elettromagnetici irradiati, che viaggiano nello spazio circostante (antenna trasmittente) o viceversa(antenna ricevente).

Le proprietà di radiazione e impedenza di un'antenna dipendono dalla forma, misura e proprietà del materiale di cui è composta.

Inoltre, per la maggior parte delle antenne vale il *Teorema di reciprocità*, il quale afferma che un'antenna ha le stesse caratteristiche di radiazione sia per la trasmissione che per la ricezione.

# 2.1 - La regione di campo lontano (Far-Field Region)
Se si immaginasse di dividere lo spazio circostante un'antenna in diverse regioni di spazio, si potrebbero identificare due macro-regioni: la *regione di campo vicino (Near Field)* e la *regione di campo lontano (Far Field)*.

La distanza limite che separa queste due regioni è detta ***distanza di Fraunhofer***.
$$
r > r_F = \frac{2D^2} {λ}
$$

![[Fraunhofer's region.png]]

Tale distanza dipende da alcuni parametri dell'antenna, tra cui :
- $D$, che è la dimensione massima dell'elemento radiativo (o il diametro dell'antenna) e
- $λ$, che è la lunghezza d'onda dell'onda elettromagnetica.

Le antenne infatti, sono progettate per funzionare nella regione di campo lontano.
Nella regione di spazio vicina, il campo elettrico e quello magnetico sono accoppiati, il che rende difficile operare in tale regione.
Tuttavia, nella regione Near Field è utile effettuare misurazioni utili alla progettazione delle antenne, infatti questa regione presenta un vantaggio misurativo sfruttato anche nella regione Far Field.

# 2.2 - Il sistema di riferimento sferico
Lo studio delle antenne avviene su 3 dimensioni, per tale motivo si lavorerà con un sistema di riferimento tridimensionale sferico.

![[Sistema di riferimento sferico 3D.png]]

Il campo irradiato da un'antenna nella regione Far Field è rappresentabile tramite le seguenti equazioni:
$$
\begin{multline}

\underline{E}(\underline{r}) = -j \frac{β_0 ζ_0} {4π} \frac{e^{-β_0 r}} {r} [N_θ(θ, Φ) \hat{θ} + N_Φ(θ, Φ) \hat{Φ}] = E_θ(\underline{r}) \hat{θ} + E_Φ(\underline{r}) \hat{Φ} = \underline{E}_r(\underline{r}) + j \underline{E}_i(\underline{r})

\\
\\

\underline{H}(\underline{r}) = \frac{1} {ζ_0} \hat{r} \times \underline{E}(\underline{r})

\hspace{200mm}
\end{multline}
$$

La prima equazione consente di valutare il campo elettrico in un ****punto di osservazione****, nel quale è posizionata l'antenna ricevente.
La seconda espressione invece, esprime il campo magnetico come prodotto vettoriale tra il versore radiale e il campo elettrico.

Il campo elettrico è un vettore complesso, infatti compaiono anche i fasori.

- Il vettore $r$ è il ***vettore posizione***. Esso individua la posizione di un punto in un sistema di riferimento;
- $β_0$ è la ***costante di fase*** (o ***costante di propagazione nello spazio libero***) ed è legata alla lunghezza d'onda dalla relazione $β = \frac{2π}{λ_0}$;
- $ζ_0$ è l'***impedenza intrinseca nello spazio libero***, diversa dall'impedenza caratteristica della linea, è una costante ed è pari a $377Ω = 120π$;
- $\underline{r}$ è la ***coordinata radiale***, ossia la distanza radiale del punto dall'origine. Esso compare al denominatore sia nel termine di fase che in quello di ampiezza, il campo elettrico, infatti, è inversamente proporzionale ad $\underline{r}$;
- la parte tra parentesi quadre rappresenta una componente vettoriale, contiene infatti, gli angoli $θ$ (*angolo zenitale*) e $Φ$ (*angolo azimutale*), che individuano una posizione.

Per capire l'utilità e il funzionamento di questi ultimi parametri ($θ$, $Φ$) si immagini di tagliare una sfera con un piano meridiano (verticale).
L'angolo che si forma tra l'asse $z$ è l'angolo $θ$, il quale varia tra 0°-180Capitolo ￼￼1 - Transmission lines￼°, a seconda della posizione sul *semiasse positivo* o *negativo* di $z$.

Invece, tagliando la sfera con un piano equatoriale (orizzontale), si ottiene l'angolo tra $x$ ed $y$, che è stato precedentemente denominato come Φ, il quale varia tra 0°-360° secondo le seguenti indicazioni:
- 0° semiasse positivo di $x$;
- 90° semiasse positivo di $y$;
- 180° semiasse negativo di $x$;
- 270° semiasse negativo di $y$.

I vettori $\hat{r}, \hat{Φ}, \hat{θ}$ sono scelti in base al punto di osservazione.
- $\hat{r}$ si ottiene prolungando il vettore radiale;
- $\hat{Φ}$ si ottiene dal prodotto vettoriale di $\hat{r}$ e $\hat{θ}$ ed il suo verso corrisponde al verso di crescita dell'angolo φ;
- $\hat{θ}$ si ottiene tramite la scelta della direzione tangente al vettore radiale e del verso che permette l'incremento maggiore dell'angolo θ

Questi 3 versori sono tra loro ortogonali.
> $\hat{r}$ giace sul piano ortogonale, mentre $\hat{θ}$ e $\hat{Φ}$ su quello tangente alla sfera

# 2.3 - Polarizzazione del campo elettrico
In termini fisici, la polarizzazione della radiazione elettromagnetica è una caratteristica delle onde elettromagnetiche ed indica la *direzione dell'oscillazione del vettore campo elettrico* durante la propagazione dell'onda nello spazio-tempo.
La polarizzazione del campo elettrico indica, dunque, **forma e luogo dei punti toccati dal vettore campo elettrico istantaneo**.
Quando opera in modalità ricevente, un'antenna può estrarre da un campo incidente solo la componente corrispondente alla polarizzazione.

> Campo elettrico e magnetico si muovono ***sempre** nel piano tangente*

La **differenza di fase δ** tra le funzioni complesse $E_θ$ e $E_Φ$ descrive la polarizzazione (differenza di fase delle due componenti).

Questa relazione permette di individuare la relazione tra i vettori reali $E_r$ e $E_i$ e le due funzioni complesse:
$$
\begin{align}

\underline{E}(\underline{r}) = E_θ(\underline{r}) \hat{θ} + E_Φ(\underline{r}) \hat{Φ} = \underline{E}_r(\underline{r}) + j \underline{E}_i(\underline{r})

\hspace{71mm}
\\
\\

\underline{E}(\underline{r}) = |E_θ(\underline{r})| \hat{θ} + |E_Φ(\underline{r})| e^{jδ} \hat{Φ} = [|E_θ(\underline{r})| \hat{θ} + |E_Φ(\underline{r})| \cos{δ} \hat{Φ}] + j|\underline{E}_Φ(\underline{r})| \sin{δ} \hat{Φ}

\hspace{2mm}
\\
\\

\underline{E}_r(\underline{r}) = |E_θ(\underline{r})| \hat{θ} + |E_Φ(\underline{r})| \cos{δ} \hat{Φ}

\hspace{45mm}

\underline{E}_i(\underline{r}) = |\underline{E}_Φ(\underline{r})| \sin{δ} \hat{Φ}

\end{align}
$$

La polarizzazione dipende, di fatto, da δ:
- se $δ = 0, π$ si parlerebbe di ***polarizzazione lineare*** poiché il campo elettrico istantaneo descriverebbe una linea al variare del tempo;
- se $δ = \pm \frac{π}{2}$ il campo descriverebbe una circonferenza e si parlerebbe, dunque, di ***polarizzazione circolare***. In particolar modo, si parla di:
	- **circolazione sinistrorsa (Left-Hand Circulation, LHC)** quando $δ = π/2$ (verso di rotazione orario);
	- **circolazione destrorsa (Right-Hand Circulation, RHC)** quando $δ = -π/2$ (verso di rotazione antiorario).

![[Tipi di polarizzazione.png]]

Dunque:
- se il **vettore direzione del campo magnetico ha tutte le componenti reali** allora la **radiazione si dice polarizzata linearmente** e la **direzione del vettore campo magnetico rimane costante nel tempo**;
- se, invece, consideriamo **due onde piane, di uguale ampiezza, polarizzate linearmente lungo due direzioni ortogonali e sfasate di un quarto di periodo**, *sommando i due campi elettrici* si ottiene un vettore polarizzazione risultante che ha una componente complessa. L'**onda risultante è una  radiazione elettromagnetica in cui l'intensità del campo elettrico, in un punto fissato, non varia, ma la sua direzione ruota con frequenza angolare**.
- Oltre alla polarizzazione lineare e circolare, vi è anche la ***polarizzazione ellittica*** definita quando parte reale e parte immaginaria del vettore direzione del campo elettrico non sono uguali.
> Ogni polarizzazione ellittica può essere scomposta nella somma di due polarizzazioni lineari ortogonali o di due polarizzazioni circolari inverse.

# 2.4 - Potenza irradiata
## 2.4.1 - Vettore di puntamento
Dati $\tilde{E}$ e $\tilde{H}$ in forma fasoriale, il **vettore di Poynting medio** dell'onda irradiata, anche detto **densità di potenza**, si può ottenere tramite la seguente formula:
$$
\begin{multline}

\underline{S}(\underline{r}) = \frac{1}{2} \underline{E}(\underline{r}) \times \underline{H}^*(\underline{r}) = \frac{1}{2} \underline{E}(\underline{r}) \times [\frac{1}{ζ_0} \hat{r} \times \underline{E}(\underline{r})]^* = \frac{|\underline{E}(\underline{r})|^2}{2ζ_0} \hat{r} = S(\underline{r}) \hat{r}
\tag*{Poynting's vector}

\\
\\
\end{multline}
$$
Il vettore di puntamento si determina con il prodotto vettoriale tra campo elettrico  il coniugato del campo magnetico. A sua volta il campo magnetico è dato dal prodotto vettoriale tra il vettore radiale e campo elettrico.
La relazione mette in risalto il fatto che il vettore risultante (di Poynting) è reale, cioè tutta la potenza è attiva.
Inoltre, il vettore $\underline{S}(\underline{r}) \hat{r}$ indica la direzione di propagazione del segnale elettromagnetico. L'ampiezza del vettore di Poynting è $S(r)$.
___
## 2.4.2 - Densità di potenza
Essa è pari al modulo del vettore di puntamento.
La densità di potenza diminuisce con legge ${1}/{R^2}$, cioè più in fretta del campo elettrico (che varia in base alla distanza seguendo la legge $1 / R$).

$$
\begin{multline}

S(r, θ, Φ) = \frac{|\underline{E}(r, θ, Φ)|^2} {2ζ_0} \hspace{15mm}[W/m^2] \tag*{power density}
\\
\\
\end{multline}
$$
___
## 2.4.3 - Intensità di radiazione
L'intensità di radiazione dipende soltanto da $θ$ e $Φ$ e non più dal versore $r$.

$$
\begin{multline}

U(θ, Φ) = r_0^2 S(r_0, θ, Φ) = r_0^2 |\underline{E}(r_0, θ, Φ)|^2 / 2ζ_0 \hspace{15mm} [W] \hspace{30mm}\tag*{radiation intensity}
\\
\\
\end{multline}
$$
___
## 2.4.4 - Intensità di radiazione normalizzata
Il diagramma di radiazione di una qualsiasi antenna è descritto in termini dell'**intensità di radiazione normalizzata $F(θ, Φ)$**, definita come il rapporto tra la *densità di potenza $S(R, θ, Φ)$* e $S_{max}$, il massimo valore di $S(R, θ, Φ)$ ad una data distanza $R$:
$$
\begin{multline}

F(θ, Φ) = U(θ, Φ) / U_{max} = S(r_0, θ, Φ) / S_{max} \leq 1 \tag*{normalized radiation intensity}

\\
\\
\end{multline}
$$
___
## 2.4.5 - Potenza totale irradiata
La *potenza totale* irradiata da un'antenna attraverso una superficie sferica ad una distanza fissa R si calcola considerando tutti i contributi e si valuta calcolando il flusso del vettore di Poynting attraverso la superficie sferica che circonda l'antenna.

$$
\begin{multline}

P_{rad} = \int_0^π \int_0^{2π} {S(r_0, θ, Φ) \hat{r} \hat{r} r_0^2 \sin{θ} dΦ dθ} = \int_0^π \int_0^{2π} {\frac{|\underline{E}(r_0, θ, Φ)|^2} {2ζ_0} r_0^2 \sin{θ} dΦ dθ} \tag*{total radiated power}

\\
\\
\end{multline}
$$
> La potenza si irradia in ogni direzione e, per tale motivo, in qualsiasi direzione è possibile calcolarla.

# 2.5 - Radiation pattern (Diagramma di radiazione)
L'intensità di radiazione normalizzata caratterizza il *comportamento direzionale* della potenza irradiata dall'antenna, la rappresentazione grafica della funzione

$$
F_{dB} = 10 \hspace{1mm} log{F(θ, Φ)}
$$
in funzione della direzione di osservazione costituisce il seguente pattern tridimensionale.

![[Radiation pattern.png]]
Il **solido (o diagramma) di radiazione** è la rappresentazione grafica in 3D che indica l'**intensità di radiazione normalizzata** in $dB$, la quale dipende da $θ$ e $Φ$.
> Nella figura sopra inserita si hanno $θ = 90°$ e $Φ = 0°$, trovandoci sull'asse $x$.

Tramite questo grafico si può intuire quale sia la **direzione di puntamento** (in figura è l'asse $x$).
La direzione di puntamento è, infatti, quella a cui corrisponde la massimo potenza, dunque quella dove la densità di radiazione è maggiore.

La direzione di puntamento (o di *massimo*) è contenuta nel **lobo principale** (il *centrale* in figura) dell'antenna.

Come detto nel Paragrafo [[#2.2 - Il sistema di riferimento sferico]], i piani principali si ottengono tagliando con un meridiano ed un parallelo la sfera che rappresenta il sistema di riferimento.
È possibile fissare uno dei due piani in modo tale da poter osservare in che modo uno dei due angoli di direzione varia.
Tale variazione è fruibile tramite due grafici:
- diagramma polare
- rappresentazione cartesiana

> Nell'esempio che segue l'angolo $Φ$ è fissato, mentre $θ$ varia.

![[Radiation pattern - 2.png]]
# 2.6 - Direttività
Considerando il collegamento più semplice da immaginare, *punto-punto*, appare chiaro che la direzione del collegamento è unica, e quand'essa coincide con la direzione del segnale le prestazioni sono ottimali.

Nel collegamento *multi-punto* invece, sia trasmittente che ricevente assumono diverse direzioni nello spazio.

Per capire il comportamento di un'antenna durante la trasmissione di un segnale è necessario, dunque, introdurre alcuni parametri.
Il primo di questi è la **direttività**.

> ### DEFINIZIONE GENERALE DI DIRETTIVITÀ
> La **funzione direttività** è una *misura* di quanto sia direttiva una singola antenna rispetto ad un'**antenna isotropa** (S costante in ogni direzione) che irradia la stessa potenza totale.

$$
D(θ, Φ) = \frac{S(r_0, θ, Φ)} {S_{iso}(r_0)} = \frac{S(r_0, θ, Φ)} {P_{rad} / 4πr_0^2} = \frac{|\underline{E}(r_0, θ, Φ)|^2 / 2ζ_0} {P_{rad} / 4πr_0^2}
$$
In generale, la direttività di un’antenna in una certa direzione è una funzione definita come il rapporto tra la densità di potenza irradiata (in quella direzione) ad una certa distanza dall'antenna e la densità di potenza di una particolare antenna: l’*antenna isotropa*.
Quest'ultima antenna è anche detta **antenna omnidirezionale**; essa irradia allo stesso modo in tutte le direzioni (il suo solido di radiazione è una sfera).
La densità di potenza irradiata da questa antenna può essere quindi scritta come la potenza totale irradiata divisa per la superficie della sfera (la distribuzione della potenza è infatti uniforme) → $S_{iso} = P_{rad} / 4π r_0^2$.

Mentre la **direttività è una funzione**, il **valore (in potenza) di direttività** (caratterizzato dal termine al numeratore $S_{max}$ , ossia la densità di potenza) è un **caso particolare** della funzione direttività: ossia è la direttività nel caso in cui la **direzione è quella di massima potenza**.

$$
D_{dBi} = 10 \hspace{1mm} \log{D_{max}} = 10 \hspace{1mm} \log{\frac{S_{max}} {P_{rad} / 4π r_0^2}}
$$

La $i$ del parametro $D_{dBi}$ indica che stiamo definendo tale parametro in funzione dell'antenna isotropa. (Se ci fosse stata $d$ anziché $i$, allora l'antenna di riferimento sarebbe stata il *dipolo a mezz'onda*).
Tanto più è alto il valore di $D_{dBi}$ tanto più l'antenna è capace di concentrare potenza nella direzione di massimo (il segnale riesce a raggiungere distanze più elevate) e il lobo principale è stretto.

# 2.7 - Beamwidth (Larghezza del fascio)
La larghezza del fascio di metà potenza (half-power beamwidth HPBW) o, semplicemente, la larghezza del fascio, è definita come la larghezza angolare (o intervallo angolare) del lobo principale tra i due angoli in cui l'ampiezza di $F$ è uguale alla metà del suo valore di picco (o $-3dB$ sulla scala dei decibel).

Per dirla brevemente, la larghezza del fascio (o del lobo) è l'intervallo angolare che corrisponde ad un'attenuazione di $3dB$ dell'intensità di radiazione rispetto al suo valore massimo.

![[Beamwidth & directivity.png]]

Guardando i diagrammi polari in figura e in particolare guardando il lobo principale, si può capire se un'antenna è direttiva o meno.
In particolare, i diagrammi mostrano come varia l’intensità di radiazione a 1, 3 e 8 GHz (si ricordi che il campo elettrico dipende dalla frequenza di lavoro, se si cambia frequenza di lavoro, cambierà anche il grafico di radiazione).

Nel piano H (prima figura), Per tutte e 3 le frequenze, il lobo principale è quello
che ha come asse di direzione l'asse 0.

È dimostrabile che la direttività dell'antenna aumenta tanto più il lobo principale è stretto. Più l’antenna è direttiva meglio si presta all'utilizzo in un collegamento di tipo punto-punto.

> Più salgo in frequenza più diminuisce la lunghezza d'onda. Più la lunghezza d'onda è piccola, più la perdita di potenza del segnale è alta, quando questo attraversa un ostacolo.
> Nell'esempio grafico, maggiore è la lunghezza d'onda e maggiore è la direttività (lobo più stretto) ma non è sempre così.

# 2.8 - Efficienza di radiazione e guadagno di potenza
L'**efficienza di radiazione** $η = P_{rad}P{in} \le 1$ è una misura della capacità dell'antenna di irradiare la $P_{in}$ di alimentazione fornita.
La **funzione guadagno di potenza G** tiene conto delle perdite ohmiche nei materiali dell'antenna.
___
$$
G(θ, Φ) = \frac{S(r_0, θ, Φ)} {P_{in} / 4π r_0^2} = \frac{|\underline{E}(r_0, θ, Φ)|^2 / 2ζ_0} {P_{in} / 4πr_0^2} = \frac{P_{rad}}{P_{in}} \frac{S(r_0, θ, Φ)} {P_{rad} / 4π r_0^2} = η D(θ, Φ)
$$
> Definizione generale di guadagno

___
$$
G_{dBi} = 10 \hspace{1mm} \log{G_{max}} = 10 \hspace{1mm} \log{η D(θ, Φ)}
$$
> Guadagno nella direzione di potenza massima (in decibel)

___

Il guadagno, come la direttività è una funzione che dipende dalla direzione (dagli angoli $θ$ e $Φ$).

Direttività e guadagno hanno lo stesso significato, la differenza è che **il guadagno tiene conto anche delle perdite dell'antenna**; infatti, al denominatore vi è la potenza in ingresso all'antenna isotropa (nella direttività si aveva quella irradiata).
Ovviamente, la potenza in ingresso è maggiore rispetto a quella irradiata dall'antenna.

Come per la direttività, anche qui si può osservare un legame stretto tra guadagno e larghezza del lobo principale.

> Nel caso ideale di un’antenna senza perdite η= 1, guadagno e direttività coincidono.

# 2.9 - Potenza efficace irradiata isotropa
La **potenza efficace irradiata isotropica (EIRP)** è la potenza che un'antenna isotropa dovrebbe irradiare per ottenere lo stesso valore dell'intensità della radiazione dell'antenna in una direzione fissa.

$$
EIRP(θ, Φ) = P_{rad} D(θ, Φ) \rightarrow EIRP = P_{rad} D_{max} = P_{in} G_{max}
$$
# 2.10 - Impedenza in input
È possibile rappresentare un'antenna, in modo circuitale, tramite un'impedenza $Z_a$, la quale è generalmente complessa.
Si dice che **un'antenna lavora in risonanza quando la sua parte reattiva è nulla**, ovvero sta assorbendo solo potenza attiva.

|![[Rappresentazione circuitale antenne-1.png]]   | Un'antenna collegata al terminale di uscita di una linea di trasmissione è descritta da: <br> $Z_a = R_a + jX_a$|
|---|---|
|![[Rappresentazione circuitale antenne-2.png]]   | Antenna in risonanza: $X_a = 0$ <br> Antenna in adattamento: $Z_a = Z_0 \rightarrow Γ_a = 0$  |

Se **$Z_a$ è uguale all'impedenza caratteristica della linea**, le condizioni di adattamento sono soddisfatte; se ciò non accade è necessario utilizzare una rete di adattamento.

Il valore $R_a$ è definito dalla combinazione di due termini: $R_r$ e $R_i$, dove il primo è la **resistenza di radiazione**, mentre il secondo è la **parte resistiva dell'antenna associata alle perdite**, dovute a componenti fisici dell'antenna.

La potenza in ingresso può essere espressa come quella irradiata sommata con quella persa:
$$
P_{in} = P{rad} + P{loss} = \frac{1}{2} R_r |I_a|^2 + \frac{1}{2} R_l |I_a|^2
$$
Questi tre termini permettono di esprimere il **coefficiente di efficienza di radiazione** come il rapporto tra resistenza di radiazione $R_r$ e la somma tra $R_r$ e $R_{loss}$:
$$
η = \frac{P_{rad}} {P_{in}} = \frac{P_{rad}} {P_{rad} + P{loss}} = \frac{R_r} {R_r + R_l} 
$$
# 2.11 - Bandwidth (Larghezza di banda)
La larghezza di banda esprime la capacità dell'antenna di operare su un'ampia gamma di frequenze.
Viene spesso definito come l'intervallo entro il quale il guadagno di potenza viene mantenuto entro $3 dB$ dal suo massimo valore.
La larghezza di banda è spesso indicata come percentuale della frequenza operativa nominale.

Un'antenna non lavora allo stesso modo nelle varie frequenze.
La larghezza di banda è l’intervallo di frequenza per cui si accetta un certo comportamento dell'antenna, ovvero quello per cui il guadagno o la direttività non devono scendere sotto il valore massimo del guadagno meno $3 dB$.
Sostanzialmente, la larghezza di banda ci dice in quale banda l'antenna funziona correttamente.
# 2.12 - Front to Back Ratio
È definito come il rapporto in $dB$ tra il valore di picco dell'intensità della radiazione e il suo valore nella direzione opposta.
# 2.13 - Altezza efficace
L'altezza efficace è una funzione vettoriale complessa.
L’altezza efficace fornisce informazioni sulla corrente di alimentazione dell'antenna ($I_0$), ma anche informazioni su come l'antenna irradia al variare della direzione (termine tra quadre)

$$
\underline{h}(θ, Φ) = - \frac{1}{I_0} [N_θ(θ, Φ) \hat{θ} + N_Φ(θ, Φ) \hat{Φ}]
$$
L'introduzione di tale funzione ci fornisce un nuovo modo di esprimere il campo elettrico:
$$
\underline{E}(r, θ, Φ) = -j \frac{β_0 ζ_0}{4π} \frac{e^{-j β_0 r}}{r} [N_θ(θ, Φ) \hat{θ} + N_Φ(θ, Φ) \hat{Φ}] = j \frac{β_0 ζ_0}{4π} \frac{e^{-j β_0 r}}{r} I_0 \underline{h}(θ, Φ)
$$

# 2.14 - Antenne in ricezione
![[Antenne in ricezione.png.png]]
La maggior parte delle antenne sono **dispositivi reciproci**: presentano lo **stesso diagramma di radiazione** per la trasmissione come per la ricezione.
Questa proprietà è molto comoda perché permette di calcolare la configurazione dell'antenna nella modalità di trasmissione, anche quando l'antenna è destinata a funzionare come ricevitore.
Mentre un’antenna in trasmissione può essere rappresentata, dal punto di vista circuitale, come un carico, **un'antenna funzionante in modalità ricevente può essere rappresentata dal suo circuito equivalente costituito da un generatore di tensione collegato all'impedenza dell'antenna $Z_a$**.

Il **carico $Z_L$ rappresenta non soltanto il ricevitore**, ma tutto quello che c'è a valle dei morsetti dell'uscita dell'antenna (cioè tiene conto anche dell'**impedenza della linea**, quindi dei cavi).
In un circuito alla Thevenin, dunque, l'**impedenza $Z_L$ è quella in ingresso** all'antenna.
Il **generatore del circuito equivalente** rappresenta invece la **tensione a vuoto**.

Sia $E_i$ il campo incidente nella direzione $θ$, $φ$ riferito al centro dell'antenna, risulta:
$$
V_{oc} = \underline{E}^i(θ, Φ) \cdot \underline{h}(θ, Φ)
$$
ossia: la tensione introdotta nel circuito è calcolata come il prodotto scalare tra campo elettrico incidente all'antenna (valutato nel sistema di riferimento dell'antenna ricevente) con l'altezza efficace della nostra antenna in ricezione.
Poiché l'antenna è un dispositivo reciproco, l'altezza efficace è la stessa sia in ricezione che in trasmissione.
L'antenna in ricezione risulta ora completamente caratterizzata da tale tensione e dall'impedenza in ingresso.
# 2.15 - Area efficace (Apertura)
Esistono due **condizioni ideali di ricezione**:

| Condizione di adattamento in impedenza (o in potenza)  |  Condizione di adattamento in polarizzazione |
|---|---|
| Tale condizione è verificata quando l'impedenza del carico è uguale al coniugato dell'impedenza del circuito equivalente (impedenza in ingresso), si ha, cioè, il massimo trasferimento di potenza verso $Z_L$.  | Tale condizione è verificata quando il campo elettrico incidente e il coniugato dell'altezza efficace sono legati da un coefficiente $α$. <br> La polarizzazione del segnale che arriva e quella dell'antenna in ricezione sono compatibili, ciò comporta l'assenza di perdita di potenza legata al disallineamento delle polarizzazioni. Inoltre, tale relazione ci dice che le due grandezze vettoriali sono tra loro parallele.  |
| $Z_a^* = Z_L$ | $\underline{E}^i = α \underline{h}^*$ |
Se tali condizioni sono rispettate, è possibile esprimere la **potenza consegnata al carico** come:
$$
P_L = S^i(θ, Φ) \hspace{1.5mm} A_{eff}(θ, Φ) \tag*{W}
$$
dove $**S^i$ è la densità di potenza del segnale incidente all'antenna in ricezione** (misurata in $W/m^2$) mentre $A_{eff}$ è la funzione definita come:
$$
A_{eff}(θ, Φ) = \frac{ζ_0 |\underline{h}(θ, Φ)|^2} {4 R_a} \tag*{$m^2$}
$$
dove:
- $ζ_0$ è l'impedenza intrinseca dello spazio libero
- $\underline{h}(θ, Φ)$ è l'altezza efficace
- $R_a$ è la parte resistiva dell'impedenza dell'antenna

## 2.15.1 - Caso reale
Se invece, le due condizioni ideali di ricezione non sono rispettate, si definisce un caso reale che generalizza quello ideale, in cui la potenza è influenzata da due **fattori di disadattamento**:
$$
P_L = S^i(θ, Φ) \hspace{1.5mm} A_{eff}(θ, Φ) \hspace{1.5mm} χ(θ, Φ) \hspace{1mm} ξ
$$
dove:
1. $ξ$ è il **fattore di disadattamento in potenza**, definito come:
$$
ξ = \frac{4 R_a R_L} {|Z_a + Z_L|^2} \le 1
$$
	1.1. $R_a$ è la parte resistiva dell'impedenza dell'antenna
	1.2. $R_L$ è la parte resistiva dell'impedenza in ingresso all'antenna (quella del carico)
Tale fattore è sempre compreso tra $0$ e $1$ e vale $1$ in condizioni di adattamento.

2. $χ(θ, Φ)$ è il fattore di disadattamento di polarizzazione, definito come:
$$
χ(θ, Φ) = \frac{|\underline{E}^i(θ, Φ) \cdot \underline{h}(θ, Φ)|^2} {|\underline{E}^i(θ, Φ)|^2 |\underline{h}(θ, Φ)|^2} \le 1
$$
è una funzione nella direzione d'arrivo. <br>
Al numeratore si ha il modulo quadro del prodotto scalare tra campo elettrico incidente e altezza efficace dell'antenna in questione; al denominatore si ha il prodotto dei moduli quadri delle medesime grandezze.
Anche questo fattore varia tra 0 e 1 e vale 1 in condizioni di polarizzazione soddisfatte, 0 quando campo elettrico incidente e altezza efficace sono tra loro perpendicolari. <br>
> La coppia $(θ, φ)$ rappresenta ora la direzione di arrivo rispetto al sistema di riferimento dell'antenna in ricezione; la coppia di angoli riferita al sistema in ricezione potrebbe essere completamente diversa da quella in trasmissione

È dunque sufficiente che uno solo dei due fattori sia 0, per avere una potenza consegnata al carico pari a 0.
# 2.16 - Esempio: Antenna Dipolo a Mezz'Onda
Un'**antenna lineare (o dipolo) a mezz'onda** è costituita da **cilindretti allineati, separati e alimentati al centro**. I cilindretti sono tutti *dipoli* (è un'***antenna composta***).

L'antenna più semplice vede un solo dipolo alimentato al centro; è l'antenna più semplice, nonché quella di riferimento (è ottimale scegliere un riferimento reale piuttosto che uno ideale quale l'antenna isotropa).

La **lunghezza complessiva** è data da quella dei due cilindri e dev'essere pari **alla metà della lunghezza d'onda della frequenza di lavoro** ($L = λ_0/2$).
A tale frequenza, l'antenna lavora in **risonanza** (impedenza d'ingresso puramente resistiva), è a banda stretta, ma soprattutto a polarizzazione lineare.

Lavorare a mezz'onda significa avere il raggio del cilindro molto minore sia alla lunghezza d'onda che alla lunghezza dell'antenna L.

Si consideri dunque, una distribuzione di corrente elettrica sulle antenne a dipolo, che solitamente sono caratterizzate da un raggio $a$ tale che: $a \ll L$ e $a \ll λ_0$.
Di solito funzionano in **condizioni di risonanza**, hanno una **larghezza di banda ridotta** e **polarizzazione lineare**.

## 2.16.1 - Campo elettrico del bipolo a mezz'onda
Il campo elettrico irradiato a mezz'onda ha solo componenti lungo $𝜃$ ($𝑁_𝜃$) per via della polarizzazione lineare verticale (ossia lungo $θ$), il che implica l'assenza di dipendenza da $Φ$ e una forte omnidirezionalità di irradiazione/ricezione del proprio diagramma di radiazione. 
Il solido di radiazione è di rotazione, ciò significa che quello che si osserva in un piano meridiano è valido per tutti i piani meridiani, dato che il solido è un solido di rotazione attorno all'asse $z$ (dipingendo una figura simile ad una ciambella).

## 2.16.2 - Densità di potenza irradiata
La densità di potenza irradiata, che è il modulo quadro del campo elettrico, dipende solo da $θ$.

> Per fare il modulo di un vettore complesso, il modulo quadro è il prodotto scalare tra il numero e il suo coniugato.

Si ottiene così la relazione:
$$
S(r, θ) = \frac{|E_θ(r, θ)|^2} {2 ζ_0} = \frac{ζ_0} {8 π^2 r^2} |I_0|^2 [ \cos{( \frac{π}{2} \cos{θ})} / \sin{θ}]^2 \rightarrow S_{max} = S(r, θ = \frac{π} {2}) = \frac{ζ_0} {8 π^2 r^2} |I_0|^2
$$

 > La **densità di potenza** assume valore massimo quando $θ = π/2$ dato che il $\sin{π/2} = 1$ e il $\cos{π/2} = 0$, ma $\cos{0} = 1$.

Il fatto che il valore della densità di potenza dipenda soltanto da $θ$ lascia intendere l'esistenza di **infinite direzioni di massimo**, ovvero tutte quelle per cui si ha variabilità di $Φ$ sul piano equatoriale e valore di $θ = π/2$.

Le antenne a dipolo hanno il vantaggio di irradiare allo stesso modo sul piano trasverso (si riesce a coprire la zona d'interesse ovunque ci si trovi).

## 2.16.3 - Intensità di radiazione normalizzata
$$
F(θ) = [ \cos{( \frac{π}{2} \cos{θ})} / \sin{θ} ]^2
$$
> Per ulteriori informazioni si rimanda al Sotto-Paragrafo [[#2.4.4 - Intensità di radiazione normalizzata]].

## 2.16.4 - Diagrammi di radiazione e beamwidth
![[radiation pattern dipolo mezz'onda.png]]
A $90°$ si ha la massima intensità di radiazione, ma nelle altre direzioni l'attenuamento è piccolo, questo è dovuto alla simmetria rotazionale del cilindro.
A $0°$ e $180°$ invece, il bipolo non emette alcun segnale, ciò permette di dedurre che la direzione da evitare è quella corrispondente all'asse dell'antenna (dove si ha il minimo).

Il lobo principale è presente solo sul piano verticale E, dunque, possiamo valutare l'HPBW (larghezza di banda) solo sul piano verticale.

Di quanto ci si può spostare per ottenere l'attenuazione di $3 dB$?
$$
10 \hspace{1mm} \log{(F(θ = \frac{π}{2} = - \frac{Δ_V}{2}))} = -3 \rightarrow Δ_V = 78°
$$
<br> L'intervallo angolare è di $78°$.

## 2.16.5 - Potenza totale irradiata
Per calcolare la **potenza totale irradiata** bisogna integrare la *densità di potenza* attraverso una superficie sferica, bisogna cioè, calcolarne il flusso.

Effettuando i calcoli risulta che la **potenza irradiata è legata direttamente al modulo quadro della corrente di alimentazione** da un parametro pari a $36.6$:
$$
\begin{align}

P_{rad} = \int^π_0 \int_0^{2π} {\frac{ζ_0}{8 π^2} |I_0|^2 [\cos{( \frac{π}{2} \cos{θ})} / \sin{θ}]^2} \sin{θ} \hspace{1mm} dΦ \hspace{1mm} dθ

\\
\\

= [\frac{ζ_0}{4 π} |I_0|^2] \int_0^π{[\cos^2{( \frac{π}{2} \cos{θ})} / \sin{θ}] dθ}

\\
\\

\cong 1.22 \frac{ζ_0}{4π} |I_0|^2 \cong 36.6 |I_0|^2

\end{align}
$$

Grazie alla relazione appena ricavata, è facilmente dimostrabile che la resistenza associata alle perdite $R_r$ è molto minore della resistenza di radiazione $R_l$ :
$$
\frac{1}{2} R_r |I_0|^2 = P_{rad} = 36.6 |I_0|^2 \longrightarrow R_r = 73.2 \gg R_l
$$

Ciò significa che $η$ (il rapporto tra potenza irradiata e potenza in ingresso) è vicino a 1, ovvero ci sono **poche perdite in potenza**. Ciò è dovuto al fatto che i **metalli utilizzati sono ottimi conduttori**.

## 2.16.6 - Direttività
L'antenna lavora **in risonanza** quando la sua lunghezza effettiva è circa $0.47/0.48$ volte la lunghezza d'onda; ciò è legato allo spessore del bipolo (raggio del cilindro).
$$
D_{max} = 1.64 \longrightarrow D_{dBi} = 2.15
$$
Ciò significa che, confrontato con il caso isotropo, il **caso a mezz'onda vede una direttività diminuita di $2.15 dB$**.

> Se si vuol conoscere la direttività di un'antenna in $dBd$, è sufficiente calcolare la direttività in $dBi$ e sottrarre $2.15$:

$$
D_{dBd} = 10 \hspace{1mm} \log{(\frac{D_{max}}{1.64})} \longrightarrow D_{dBd} = D_{dBi} - 2.15
$$

# 2.17 - Datasheet di un antenna
![[Datasheet antenna.png]]
- **Intervallo di Frequenza**: range dei valori delle frequenze di lavoro per le quali è garantito il non superamento della larghezza di banda (bandwidth) (in questo range di frequenze le prestazioni dell'antenna rimangono buone);
- **Impedenza**: questo parametro fornisce informazioni sull'impedenza in input all'antenna ($50Ω$ è la tipica impedenza dei cavi coassiali);
- **VSWR (Voltage Standing Wave Ratio)**: il rapporto di onda stazionaria è un parametro che indica il rapporto tra il valore massimo e il valore minimo del modulo della tensione lungo la linea. Tale parametro è *legato al coefficiente di riflessione*;
- **Polarizzazione**: indica il tipo di polarizzazione (nell'esempio lineare verticale, cioè ha le componenti nulle lungo $Φ$);
- **Guadagno**: indica il guadagno dell’antenna. Nell'esempio il guadagno è di $7.5 dBi$, un valore né troppo basso né troppo alto. Questo significa che l'antenna in esame non è né un'antenna molto direttiva (adatta quindi a collegamenti di tipo punto-punto) né un'antenna omnidirezionale (ossia caratterizzata da un guadagno basso, ma capace di trasmettere in tutte le direzioni e quindi adatta a collegamenti di tipo punto-multi-punto). In questo caso, l’antenna non copre un’unica direzione né tutte, ma solo una parte: è, per questo motivo, adatta alla copertura di un settore angolare;
- **3dB Beamwidth (lobo orizzontale)**: l’intervallo angolare per cui viene osservata un’attenuazione dell’intensità di radiazione di $3 dB$ rispetto al suo valore massimo sul piano orizzontale;
- **3dB Beamwidth (lobo verticale)**: l’intervallo angolare per cui viene osservata un’attenuazione dell’intensità di radiazione di $3 dB$ rispetto al suo valore massimo del modulo di $3 dB$ sul piano verticale;
> Per capire quanto valgono tali intervalli angolari guardando i diagrammi di radiazione, basta osservare la larghezza massima del lobo e “scendere” di poco (3 dB) per poi vedere a quale angolo corrisponde tale valore (il suo doppio sarà l’intervallo angolare);
- **Downtilt**: per downtilt e uptilt si intende l'inclinazione di un'antenna in gradi rispetto al piano orizzontale (tilt positivo al di sotto dell'orizzonte). Nell'esempio la direzione di puntamento è pari a $0°$, la quale corrisponde proprio con quella dell’orizzonte;
- **Front to Back Ratio**: il rapporto fronte/retro è la differenza, espressa in $dB$, tra la risposta dell'antenna ai segnali provenienti dalle due direzioni avanti e indietro;
- **Massima potenza**: massima potenza in ingresso tollerabile dall'antenna ad una certa temperatura specificata.

# 2.18 - Formula di trasmissione di Friis
Si considerino due antenne facenti parte di un collegamento di comunicazione nello spazio libero, con la distanza $r$ sufficientemente grande da consentire a ciascuna antenna di trovarsi nella regione di campo lontano (Far Field) dell'altra.

La densità di potenza irradiata dall'antenna trasmittente sarà:
$$
S(r, θ, Φ) = \frac{P_{in}}{4π r^2} G_T(θ, Φ)
$$
Finora le antenne sono state considerate nelle condizioni di ricezione e/o trasmissione separatamente, tuttavia, esse sono collegate tra loro attraverso collegamenti wireless. <br>
La *formula di Friis* ci fornisce informazioni sulla densità di potenza consegnata al carico a valle dell'antenna in ricezione, avendo noti: la distanza tra le due antenne, la potenza in ingresso e il guadagno dell’antenna trasmittente.
La formula ha senso in **ipotesi ideali**, o, per meglio specificare, **nell'ipotesi che il segnale non incontri ostacoli durante le trasmissioni**. <br>
Supponendo di essere in condizioni di adattamento potremmo sfruttare la relazione:
$$
\frac{G(θ, Φ)}{A_{eff}(θ, Φ)} = \frac{4π}{λ_0^2}
$$
e scrivere la potenza consegnata al carico come:
$$
\begin{multline}

P_L = S^i(r, θ_t, Φ_t) \hspace{1mm} A_{eff}(θ_r, Φ_r) = \frac{P_{in}}{4π r^2} \hspace{1mm} G_T(θ_t, Φ_t) \hspace{1mm} A_{eff}(θ_r, Φ_r)

\\
\\

= P_{in} \hspace{1mm} G_T(θ_t, Φ_t) \hspace{1mm} G_R(θ_r, Φ_r) (\frac{λ_0}{4π r})^2 = P_{in} \hspace{1mm} G_{Tmax} \hspace{1mm} F_T(θ_t, Φ_t) \hspace{1mm} G_{Rmax} \hspace{1mm} F_R(θ_r, Φ_r) (\frac{λ_0}{4π r})^2

\end{multline}
$$
dove la coppia di angoli $θ_t, Φ_t$ fa riferimento al sistema di riferimento dell'antenna in trasmissione, mentre la coppia $θ_r, Φ_r$ fa riferimento al sistema di riferimento dell'antenna in ricezione. <br>
> 1) $r$ è fissato lungo la direzione che connette le due antenne
> 2) il fattore $(\frac{λ_0}{4π r})^2$ è adimensionale

# 2.19 - Misurazioni del guadagno
Il guadagno è uno dei parametri fondamentali su cui ci si basa per caratterizzare ed eventualmente scegliere le antenne da utilizzare. <br>
Si è visto come in un collegamento punto-punto convenga utilizzare antenne altamente direttive, mentre in collegamento del tipo punto-multi-punto conviene utilizzare antenne a basso guadagno (in grado, tuttavia, di irradiare in tutte le direzioni). <br>
Si andranno ora ad analizzare tre tecniche di misura del guadagno. <br>
## 2.19.1 - Prima tecnica - Misurazioni utilizzando due antenne identiche
La prima tecnica vede due antenne identiche di cui non si conosce il guadagno, il costruttore dovrà quindi attuare delle misure per scoprirlo. <br>
Si supponga che:
- la direzione di puntamento delle due antenne coincida (la direzione di massimo della trasmittente punta alla ricevente);
- che le due antenne siano poste ad una distanza R;
- si conosca la frequenza di lavoro (la lunghezza d'onda);

Adesso andrà utilizzata la formula di Friis: si conosce $P_{TX}$ poiché è data in ingresso; si conosce anche $P_{RX}$ poiché basta misurare la potenza ricevuta, e il resto è noto.
I due termini guadagno rimangono incognite.
$$
P_{RX} = P_{TX} \hspace{1mm} G_T \hspace{1mm} G_R \hspace{1mm} (\frac{λ}{4πR})^2 \rightarrow P_{RX_{(dBW)}} = P_{TX_{(dBW)}} + G_{T_{(dBi)}} + G_{R_{(dBi)}} + 20 \hspace{1mm} \log{(\frac{λ}{4πR})}
 $$
Dal momento che le due antenne sono uguali, anche i due guadagni saranno uguali; sfruttando questa relazione si va ad isolare il termine guadagno:
$$
G_{T_{(dBi)}} = G_{R_{(dBi)}} = \frac{1}{2} [20 \hspace{1mm} \log{(\frac{4πR}{λ})} - (P_{TX_{(dBW)}} - P_{RX_{(dBW)}})] = \frac{1}{2} [A_R - (P_{TX_{(dBW)}} - P_{RX_{(dBW)}})]
$$
> Tali misure vanno effettuate IN AMBIENTI CONTROLLATI, ossia in una camera anecoica (ambiente di laboratorio strutturato in modo da ridurre il più possibile la riflessione di segnali sulle pareti).


## 2.19.2 - Seconda tecnica - Misurazioni usando antenne A, B e C
Nel secondo caso, si immagini di avere tre antenne tra loro diverse; di tutte si vuole, ancora una volta, conoscere il guadagno.
Riscrivendo la formula utilizzata nel caso precedente andranno lasciati separati i due guadagni, che ora sono ovviamente diversi.
$$
G_{TX_{(dBi)}} + G_{RX_{(dBi)}} = 20 \hspace{1mm} \log{(\frac{4πR}{λ})} - (P_{TX_{(dBW)}} - P_{RX_{(dBW)}}) = A_R - (P_{TX_{(dBW)}} - P_{RX_{(dBW)}})
$$
A questo punto si procederà con tre misurazioni:

| $T_x$ | $R_x$ |   |
|---|---|---|
| A | B | $G_A + G_B = Σ_1$ |
| A | C | G_A + G_C = Σ_2 |
| B | C | G_B + G_C = Σ_3 |

Nel primo set di misura, l'antenna A funge da trasmittente mentre B da ricevente. Dopo la prima misura si saprà che la somma dei guadagni delle due antenne è uguale ad un valore $Σ_1$. Dopo una seconda misurazione, che vede A antenna trasmittente e C antenna ricevente, si avrà la somma dei due guadagni: $Σ_2$; e così via.
Si ottiene così un sistema di tre equazioni in tre incognite, facilmente risolvibile.
<br>
## 2.19.3 - Terza tecnica - Misurazione usando un'antenna di riferimento
L'ultima tipologia prevede l'utilizzo di un'antenna di riferimento di cui si conoscono tutti i parametri (anche il guadagno), nel ruolo di antenna di ricezione.

Ora, bisognerà svolgere due misurazioni, in entrambe l'antenna trasmittente dev'essere fissa (cioè sia nella prima che nella seconda misurazione, l’antenna trasmittente è quella che si intende caratterizzare).
Come antenna ricevente verrà scelta prima l'antenna AUT (ossia l’*antenna under test*, vale a dire la *seconda antenna incognita*) e poi l'*antenna di riferimento*.

$$
\begin{multline*}

\hspace{8mm}
P_{AUT_{(dBW)}} = P_{TX_{(dBW)}} + G_{T_{(dBi)}} + G_{AUT_{(dBi)}} - A_R

\\
\\

P_{REF_{(dBW)}} = P_{TX_{(dBW)}} + G_{T_{(dBi)}} + G_{REF_{(dBi)}} - A_R
\hspace{90mm}

\\
\\

P_{AUT_{(dBW)}} - P_{REF_{(dBW)}} = G_{AUT_{(dBi)}}  G_{REF_{(dBi)}} \longrightarrow G_{AUT_{(dBi)}} = G_{REF_{(dBi)}} + (P_{AUT_{(dBW)}} - P_{REF_{(dBW)}})
\hspace{5mm}

\end{multline*}
$$
