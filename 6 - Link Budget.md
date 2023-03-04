Questa sezione si occuperà dello studio relativo alla valutazione di effettiva fattibilità (o meno) di un collegamento wireless.

# 6.1 - Fading
Nel percorso tra antenna trasmittente e quella ricevente, ogni volta che il segnale interagisce con un ostacolo perde potenza; inoltre, anche senza ostacoli, la densità di potenza diminuisce all'aumentare della distanza. <br>
![[Fading - 1.png]] <br>
Esistono 3 diverse modalità di attenuazione del segnale. <br>
![[Fading - 2.png]] <br>
Oltre al **path loss**, è convenzione considerare altri due tipi di fading:
- **shadowing**
- **fast fading**

Lo **shadowing (o fading lento)** è dovuto alla diversa natura dei particolari ostacoli tra le antenne, come particolari edifici alti o fitti boschi. <br>
Il **fast fading (o multipath fading)** comporta variazioni sulla scala di una mezza lunghezza d'onda ($50 cm$ a $300 \hspace{1.5mm} MHz$, $6 cm$ a $2,4 \hspace{1.5mm} GHz$); questo tipo di fading è il risultato dato dall'interferenza costruttiva e distruttiva tra onde multiple che raggiungono il ricevitore dal trasmettitore. <br>
==La **stima del link budget** dipende in particolar modo dal **path loss**, dal momento che per attenuazioni relativamente rilevanti, il ricevitore non sarà in grado di riconoscere il segnale==.

# 6.2 - Path Loss
Il **path loss** dipende soltanto dall’**ambiente propagativo**. <br>
![[Path Loss.png]] <br>
La sua definizione fa infatti riferimento alla potenza ricevuta da un’antenna isotropa:

$$
L = \frac{EIRP_T}{EIRP_R} \hspace{15mm} L = \frac{P_{TI}}{P_{RI}} = \frac{P_{in_T} G_T G_R}{P_{out_R}} = \frac{P_{in_T} G_T G_R}{A_{eff_R} S^i_R}
$$

Il pathloss 𝐿 è il rapporto tra:
- potenza trasmessa da un'antenna isotropa ($P_{TI}$);
- potenza ricevuta dall'antenna Isotropa ($P_{RI}$).

Per ottenere questa stessa potenza non dall'antenna isotropa ma dall'antenna che si sta utilizzando come trasmittente bisogna prendere la potenza in ingresso all'antenna in questione e moltiplicarla per il guadagno dell'antenna stessa. <br>
Quindi, a parità di potenza trasmessa da un'antenna isotropa e un’antenna di test che si sta usando come trasmittente, è possibile scrivere:
- il numeratore come il prodotto tra potenza in ingresso e guadagno dell'antenna di test;
- il denominatore può essere riscritto come il rapporto tra la potenza in uscita dall'antenna ricevente e il guadagno della ricevente nella direzione del collegamento;
- la potenza in uscita all’antenna ricevente può infine essere riscritta in funzione della densità di potenza incidente su antenna ricevente ($S_R^i$).

$$
L_{(dB)} = 10 \hspace{1mm} \log{(L)} = 10 \hspace{1mm} \log{(\frac{P_{in_T} G_T  G_R}{P_{out_R}})} = P_{in_T (dBW)} + G_{T (dBi)} + G_{R (dBi)} - P_{out_R (dBW)}
$$

Le potenze a cui bisogna far riferimento sono quelle in uscita dal trasmettitore e quella in ingresso al ricevitore; ciò perché la potenza in ingresso al ricevitore deve essere superiore ad una certa soglia affinché l'informazione sia correttamente riconosciuta.

$$
\begin{align}

L_{(dB)} = P_{in_T (dBW)} + G_{T (dBi)} + G_{R (dBi)} - P_{out_R (dBW)} =

\\
\\

= P_{T (dBW)} - L_{T (dB)} + G_{T (dBi)} + G_{R (dBi)} - L_{R (dB)} - P_{R (dBW)}

\end{align}
$$

La potenza in ingresso alla trasmittente può essere riscritta come la potenza in uscita dal trasmettitore meno le perdite associate al cavo ($L_T$).
Analogamente la potenza in uscita dall' antenna ricevente può essere calcolata come la somma di potenza all'ingresso del ricevitore e perdita associata ai cavi ($L_R$). <br>
==Per determinare il link budget, quindi, bisogna conoscere:==
- ==la potenza in uscita dal trasmettitore==;
- ==le perdite lungo il cavo==;
- ==guadagno della trasmittente e della ricevente nella direzione del collegamento==;
- ==potenza in ingresso all'antenna ricevente==.

## 6.2.1 - Il valore massimo accettabile di path loss
Il ricevitore avrà ovviamente determinati parametri che lo caratterizzano.
Esiste un **valore di soglia in potenza ($P_{R \hspace{0.5mm} min}$) in ingresso al ricevitore**, sotto il quale il segnale non è correttamente riconoscibile dal ricevitore.
In corrispondenza di tale valore in potenza si ha il **massimo pathloss accettabile** (ossia il valore massimo di perdite accettabile perché il segnale venga correttamente riconosciuto).
Questo livello di soglia è noto come **sensibilità del ricevitore**.
Il massimo valore accettabile di pathloss sarà:

$$
L_{(dB) max} = P_{T (dBW)} - L_{T (dB)} + G_{T (dBi)} + G_{R (dBi)} - L_{R (dB)} - P_{R (dBW) min}
$$

dove:
- $P_{R (dBW) min} = SNR_{(dB)} + NF_{R (dB)} + 10 \log{(kT \hspace{1mm} BW)}$, dove:
	- $SNR_{(dB)}$ è il rapporto segnale-rumore;
	- $NF_{R (dB)}$ è la figura di rumore del ricevitore;
	- $k = 1,38 \cdot 10^{-23} \hspace{2mm} [W/(Hz \hspace{1mm} K)]$;
	- $T \hspace{2mm} [K]$  e $BW \hspace{2mm} [Hz]$ rappresentano il terzo termine che coinvolge la **costante di Boltzman**, la temperatura assoluta e la larghezza di banda del ricevitore.

Tale valore, come si evince dalla seguente tabella, dipende anche dal protocollo in utilizzo.
Sembrerebbe che il *D-Link* funzioni meglio, in realtà più è basso il valore di soglia, più è garantita la corretta ricezione del segnale. <br>
![[sensibilità path loss - 1.png]]
![[sensibilità path loss - 2.png]] <br>
Il valore massimo di pathloss accettabile è quello in cui $P_R$ è pari al valore di soglia. <br>
Per rendere il collegamento attuabile, avendo $P_T$  fissato dalle normative di norma e di sicurezza, si potrebbe agire sui cavi (se la distanza del cavo è piccola si potrebbe utilizzare anche un cavo in oro che permette di avere meno perdite).
Si può inoltre agire sul guadagno della trasmittente, utilizzando un’antenna realizzata con materiali capaci di fornire maggiore guadagno.
Per modificare il livello di pathloss si potrebbe diminuire anche la distanza di collegamento.

## 6.2.2 - Fade margin
Il pathloss va in realtà regolato tenendo conto anche degli altri 2 fenomeni di attenuazione (slowfading e fastfading).
Ciò viene fatto introducendo un margine d'errore $FM$.

$$
L_{(dB)} = L_{(dB) max} - FM_{(dB)}
$$

Il pathloss che si sceglie di avere verrà dunque calcolato come la differenza tra il massimo pathloss accettabile e un margine di errore, che dipende da slowfading e fastfading, e che consente di assicurare la corretta ricezione del segnale. <br>
Al fine di analizzare in dettaglio il fenomeno del pathloss si considereranno 3 situazioni:
- pathloss associato allo spazio libero (assenza di ostacoli);
- presenza della terra;
- presenza di suolo e di ostacolo.

# 6.3 - Free-Space Loss
La formula di Friis metteva in relazione la potenza in ingresso alla $T_X$ con la potenza in uscita dalla $R_X$, nonché i rispettivi guadagni delle antenne nella direzione di collegamento.
Oltre che dalle due antenne, quindi, dipende anche dalla distanza e dalla frequenza.
Introducendo la definizione di pathloss, la formula di Friis diventa:

$$
P_{out_R} = P_{in_T} G_T G_R (\frac{λ}{4 π r})^2 \implies \frac{P_{in_T} G_T  G_R}{P_{out_R}} = (\frac{4 π r}{λ})^2
$$

Isolando il termine al quadrato si ottiene:

$$
L_{fs} = (\frac{4 π r}{λ})^2 = (\frac{4 π r f}{c_0})^2 = (\frac{40}{3} π r_{(km)} f_{(MHz)})^2
$$
___
$$
L_{fs (dB)} = 20 \hspace{1mm} \log{f_{(MHz)}} + 20 \hspace{1mm} \log{r_{(km)}} + 32.44
$$

<br>

> Dalla formula si noti come il pathloss di spazio libero aumenta di $6 dB$ per ogni raddoppio in frequenza o distanza (o $20 dB$ per decade di entrambi).

Il valore del pathloss nello spazio libero rappresenta una soglia inferiore per il pathloss; rappresenta il valore di partenza del pathloss, ovvero quello presente già nelle sole condizioni ideali di spazio libero. <br>
Per quanto detto, il pathloss, in generale, può essere considerato come la somma di pathloss free-space e un pathloss *in eccesso*.

$$
L_{(dB)} = L_{fs (dB)} + L_{ex (dB)}
$$

# 6.4 - Plane-Earth Loss
Verrà ora preso in considerazione il modello comprendente due raggi per terra piatta.
Fissata la posizione delle due antenne il **contributo in prossimità della ricevente è dato da due termini**:
- uno diretto (detto **LOS**, cioè **Line of side**) e
- uno per **riflessione dal suolo**.

Si supponga che la distanza in pianta tra le due antenne (distanza tra le loro proiezioni a terra tra due punti) sia molto maggiore delle rispettive altezze delle due antenne. <br>
![[plane earth loss - 1.png]] <br>
Il pathloss varrà:

$$
L_{pe} = \frac{P_{in_T} G_T G_R}{P_{out_R}} = \frac{P_{in_T} G_T G_R}{A_{eff_R} S_R^i} = \frac{P_{in_T} G_T G_R}{A_{eff_R} |E_{tot}^i|^2 / 2 ζ_0}
$$

Il coefficiente di riflessione, sia per polarizzazione perpendicolare che parallela, può 
essere approssimato a $-1$ ($Γ \cong -1$). <br>
Ciò accade perché a grande distanza il raggio $r_2$ viaggia molto vicino al suolo, questo significa che l'angolo di incidenza (l'angolo che forma con la normale alla superficie) rispetto alla normale forma un angolo di $90°$. <br>
In entrambe le formule della polarizzazione si ottengono coefficienti di riflessione pari a $-1$. <br>
È dimostrabile che:

$$
|E_{tot}^i|^2 \cong |E_{dir}^i|^2 4 (\frac{β_0 h_T h_R}{d})^2
$$

Il collegamento diretto, quindi, dipende dalla distanza tra le due antenne, dalla frequenza e dall'altezza delle due antenne.
Tale reazione vale per entrambe le polarizzazioni, e ci permette di riscrivere, attraverso una banale sostituzione, il pathloss come:

$$
L_{pe} = \frac{P_{in_T} G_T G_R}{P_{out_R}} = \frac{P_{in_T} G_T G_R}{A_{eff_R} S_R^i} = \frac{P_{in_T} G_T G_R}{A_{eff_R} \frac{|E_{dir}^i|^2}{2 ζ_0} [4 (\frac{β_0 h_T h_R}{d})^2]} = \frac{L_{fs}}{4 (\frac{β_0 h_T h_R}{d})^2} \cong \frac{(\frac{4 π d}{λ})^2}{4 (\frac{2 π h_T h_R}{λd})^2}
$$

con:

$$
L_{pe} = (\frac{d^2}{h_T h_R})^2
$$

> La $d$ al numeratore sarebbe dovuta essere $r_1$, tuttavia si sta approssimando ulteriormente sfruttando le ipotesi iniziali di grandi distanze.

$$
L_{pe(dB)} = 40 \log{d} - 20 \log{h_T} - 20 \log{h_R}
$$

![[plane earth loss - 2.png]] <br>
Si noti come il plane earth path loss aumenti molto più rapidamente rispetto al path loss free-space, e che risulta essere indipendente dalla frequenza di lavoro.
La perdita aumenta di $12 dB$ duplicando la distanza, o di $40 dB$ per decade.

Come anticipato alla fine del Paragrafo [[#6.3 - Free-Space Loss]], il pathloss di ambienti complessi può essere scritto come il pathloss nello spazio libero sommato ad un pathloss in eccesso. <br>
Nel caso del modello a due raggi terra piatta, tale pathloss è molto semplice da trovare se si lavora utilizzando la rappresentazione in decibel:

$$
\begin{gather}

L_{pe(dB)} = L_{fs(dB)} + L_{ex(dB)} = L_{fs(dB)} - 20 \log{(\frac{4 π h_T h_R}{λd})}

\\
\\

L_{ex(dB)} = -20 \log{(\frac{4 π h_T h_R}{λd})}

\end{gather}
$$

# 6.5 - Obstruction Loss
In questa casistica il collegamento diretto tra le due antenne è bloccato dall'ostacolo.
Nella valutazione del pathloss l'ostacolo viene modellato come una lama di coltello, ossia un triangolo puntato verso l'alto che impedisce il passaggio del segnale. <br>
![[obstruction loss - 1.png]]
![[obstruction loss - 2.png]]
> La distanza in pianta dell'ostacolo è molto grande rispetto alle altezze. L'ostacolo dista $d_{TX}$ dalla trasmittente e $d_{RX}$ dalla ricevente.

Il pathloss consta di due contributi, il primo è relativo allo spazio libero mentre il secondo è dovuto alla diffrazione dalla sommità dell'ostacolo:

$$
L_{(dB)} = L_{fs(dB)} + L_{ke(dB)}
$$

Il contributo $L_{ke}$ dipende da alcuni parametri geometrici.
Vengono definiti:
- $r_1$: distanza tra la trasmittente e la sommità dell'ostacolo;
- $r_2$: distanza tra la ricevente e la sommità dell'ostacolo;
- $h$: l'altezza dell'ostacolo rispetto alla retta che congiunge le due antenne;
- $d_1$ e $d_2$: i due pezzi in cui è divisa la congiungente per via di $h$. In ampiezza $d_1$ è circa uguale a $d_{TX}$ e $d_2$ è circa uguale a $d_{RX}$.

È dimostrabile che il termine 𝐿𝑘𝑒 può essere calcolato tramite l'integrale di Fresnel:

$$
L_{ke(dB)} = -20 \log{|F(v)|}
$$

dove:

$$
\begin{flalign}

F(v) &= \frac{1 + j}{2} \int_v^{\infty}{e^{-j π x^2/2} dx}&&
\hspace{50mm}
\tag*{Integrale di Fresnel}

\\
\\

v &= h \sqrt{\frac{2 (d_1 + d_2)}{λd_1 λd_2}} \cong h \sqrt{\frac{2d}{λ d_{TX} d_{RX}}}&&
\hspace{50mm}
\tag*{Parametro di diffrazione di Fresnel}

\end{flalign}
$$

Il parametro di Fresnel può assumere sia valori positivi che negativi, questo perché $h$ può essere per convenzione sia positiva che negativa (ad esempio se si ha l'ostacolo più basso rispetto al collegamento diretto, quindi il vertice del triangolo sta verso il basso).
Se $h=0$ l'altezza dell'ostacolo è nulla, cioè la punta dell'ostacolo si trova esattamente sulla congiungente.

$$
\begin{align}

L_{ke(dB)} \cong -20 \log{(\frac{1}{π ν \sqrt{2}})} = -20 \log{(\frac{0.225}{ν})}

\hspace{20mm}

\text{if} \hspace{5mm} ν>1

\end{align}
$$

Analizzando i vari scenari di posizione dell’ostacolo rispetto alla congiungente, si otterranno i seguenti risultati:
1. $ν < 0$: il vertice dell’ostacolo è al disotto della congiungente, dunque l’altezza è negativa. A partire da$ν = -0.8$ a scendere, il pathloss $L_{ke}$ assume comportamento oscillatorio fino a un punto in cui l'ostacolo non aggiunge contributo e lo studio del pathloss si riduce al caso di sola presenza del suolo (modello a 2 raggi terra piana);
2. $ν = 0$: caso particolare di radenza della congiungente rispetto all’ostacolo, cioè quando la sommità dell'ostacolo sta sulla congiungente, il pathloss $L_{ke}$ vale, in questo caso, $6dB$;
3. $ν > 0$: l'ostacolo ha attraversato la congiungente, la ricevente cioè è in ombra. Dal grafico sottostante vediamo che all'aumentare di $ν$ (cioè di $h$) la perdita aumenta (il grafico va verso il basso solo perché la rappresentazione è in $-dB$). Per valori positivi del parametro di diffrazione l'andamento è regolare e regolato (cioè approssimabile) alla formula in figura.

![[obstruction loss - 3.png]] <br>

# 6.6 - Gli elissoidi di Fresnel
Un altro modo utile per considerare la diffrazione a lama di coltello è in termini di ostruzione delle **zone di Fresnel** attorno al raggio diretto come illustrato in figura. <br>
![[elissoidi Fresnel - 1.png]] <br>
L'n-esima zona di Fresnel è la regione all'interno di un **ellissoide** definito dal luogo dei punti in cui la distanza $a + b$ è maggiore del percorso diretto $d_1 + d_2$ tra trasmettitore e ricevitore di n semilunghezze d'onda. <br>
![[elissoidi Fresnel - 2.png]] <br>
Si può pensare che le zone di Fresnel contengano la principale energia di propagazione nell'onda.
I contributi all'interno della prima zona sono tutti in fase, quindi, **eventuali ostacoli assorbenti che non entrano in questa zona avranno scarso effetto sul segnale ricevuto**.
Quando l'ostruzione occupa $0,6$ volte la prima zona di Fresnel, il parametro $ν$ è quindi approssimativamente $-0,8$ e la perdita di ostruzione è quindi $0 dB$. <br>
Questa distanza è spesso utilizzata come criterio per decidere se un oggetto deve essere trattato come un'ostruzione significativa.
Pertanto, la regione ombreggiata in figura può essere considerata una **regione "proibita" ("forbidden" region)**; se questa regione è tenuta libera allora l'attenuazione del percorso totale sarà praticamente la stessa del caso non ostruito. <br>
![[elissoidi Fresnel - 3.png]] <br>
Relativamente alla figura soprastante, si analizzano le zone numerate definendo le seguenti asserzioni:
1. se l'ostacolo non entra nella zona spaziale proibita, la presenza dell'ostacolo non viene considerata poiché il pathloss che esso causa è trascurabile;
2. quando l'altezza dell'ostacolo tocca la zona proibita, vuol dire che $h$ vale esattamente $−0.6 \cdot r_1$; da quel punto in poi l'ostacolo dev'essere considerato e il valore di pathloss può essere calcolato con la curva vista nel grafico del paragrafo [[#6.5 - Obstruction Loss]];
3. se l'ostacolo attraversa la congiungente, $h$ è positiva;
4. se la punta dell'ostacolo esce dalla zona grigia la perdita continua a crescere.

# 6.7 - Modelli empirici di propagazione
Se esiste più di un'ostruzione del terreno all'interno dell'ellissoide di Fresnel, deve essere risolto un problema di **diffrazione multipla**.
Non è corretto sommare semplicemente le perdite per ostruzione di ciascun bordo individualmente, poiché ogni bordo disturba il campo, producendo **fronti d'onda incidenti sul bordo successivo non piani**, contravvenendo alle assunzioni della teoria del bordo singolo. <br>
==L'approccio più utilizzato per prevedere la diffrazione multipla a coltello consiste nell'utilizzare un **metodo approssimato** utilizzando semplici costruzioni geometriche per calcolare una perdita di diffrazione totale in termini di **combinazioni di diffrazioni** a spigolo singolo tra spigoli adiacenti==. <br>
Per creare un tale modello, viene effettuata un'**ampia serie di misurazioni effettive** della perdita di percorso, e alle misurazioni viene adattata una funzione appropriata, con parametri derivati per il particolare ambiente, frequenza e altezza delle antenne in modo da ridurre al minimo l'errore tra il modello e le misurazioni.
Ogni misurazione rappresenta una media di un insieme di campioni, la media locale, rilevata su una piccola area (circa $10-50 m$), al fine di rimuovere gli effetti della dissolvenza rapida.
**==Il modello può quindi essere utilizzato per progettare sistemi operanti in ambienti simili alle misurazioni originali==**. <br>
![[modello empirico propagazione.png]] <br>
Ci sono vari modelli per la valutazione del pathloss, i modelli che possono essere utilizzati sia per ambienti outdoor che indoor sono:
- **Modelli Empirici**, i quali non hanno una formulazione fisica, ma sono composti da una semplice formula matematica che rappresenta il risultato finale di una campagna di misura fatta precedentemente;
- **Modelli Deterministici**, dei quali la formulazione finale tiene conto di quello che è fisicamente la propagazione del segnale.

Questa è la differenza fondamentale tra i due modelli.

|   | Modello Empirico  | Modello Deterministico  |
|---|---|---|
| PRO  | Consta di una sola formula ed è semplice da implementare.  | È una procedura molto complessa ma il risultato che si ottiene è più attendibile di quello associato a un modello empirico.  |
| CONTRO  | Poiché deriva da una campagna di misura è stato ricavato da un particolare ambiente | Per poter definire il livello di campo e di potenza devo avere la conoscenza dei meccanismi fisici che regolano la propagazione. <br><br> Per poter dire che c'è diffrazione, trasmissione e riflessione devo avere anche la conoscenza dell'ambiente (presenza di materiale schermante ecc). <br><br> Più complesso è l'ambiente e più complicata risulterà l'analisi. |


# 6.8 - Modelli fisici di propagazione
Sebbene i modelli empirici siano stati ampiamente applicati con buoni risultati, presentano una serie di svantaggi:
1. possono essere utilizzati **solo su intervalli di parametri inclusi nel set di misurazioni originali**;
2. gli ambienti devono essere classificati soggettivamente secondo categorie come “urbano”, che hanno significati diversi nei diversi paesi;
3. non forniscono alcuna comprensione fisica dei meccanismi attraverso i quali avviene la propagazione.

L'ultimo punto è particolarmente significativo, poiché i modelli empirici non sono in grado di tenere conto di fattori come un edificio o una collina insolitamente grandi, che possono modificare notevolmente la propagazione in luoghi particolari. <br>
![[modello fisico propagazione.png]] <br>
Sebbene il modello piano-terra (plane-earth) abbia un esponente di perdita di percorso vicino a quello osservato nelle misurazioni effettive, la semplice situazione fisica che descrive è raramente applicabile nella pratica.
==Il mobile opera quasi sempre (almeno nelle macrocelle) in situazioni in cui non ha un percorso in linea di vista (**LOS**, Line Of Sight) né verso la stazione base né verso il punto di riflessione a terra, quindi la situazione a due raggi non è quasi mai applicabile.== <br>
I modelli fisici cercano di superare gli svantaggi dei modelli empirici introducendo il **calcolo deterministico dei meccanismi di propagazione delle onde** per ottenere una maggiore accuratezza. <br>
I **modelli fisici** (o **deterministici**) tengono conto di *tutti i contributi dei raggi* (riflessi, diffratti in base all'ambiente propagativo, ecc.). 
Il **modello empirico** tiene conto delle *misure strumentali* e unendo tutti i punti di misura si stima il pathloss.