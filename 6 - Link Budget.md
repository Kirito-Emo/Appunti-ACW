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
- il denominatore può essere riscritto come il rapporto la potenza in uscita dall'antenna ricevente e il guadagno della ricevente nella direzione del collegamento;
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

# 6.4 - Plane Earth Loss


# 6.5 - Obstruction Loss


# 6.6 - Gli elissoidi di Fresnel


# 6.7 - Modelli empirici di propagazione


# 6.8 - Modelli fisici di propagazione
