# 4.1 - Array di Antenne
Quando due o più antenne vengono utilizzate insieme, la combinazione viene chiamata **array di antenne**.
Sebbene un array non debba essere necessariamente costituito da elementi radianti simili, la maggior parte degli array di solito sono formati da **elementi identici eccitati dallo stesso tipo di distribuzione di corrente o di campo**. Gli elementi di antenna comprendenti una matrice possono essere disposti in *varie configurazioni*, ma le più comuni sono la configurazione **lineare unidimensionale**, in cui gli elementi sono disposti lungo una linea retta, e la configurazione a **reticolo bidimensionale**, in cui gli elementi formano una griglia rettangolare. <br>
> Avere più antenne a disposizione consente di modificare le caratteristiche di radiazione senza modificare il sistema di antenne stesso.
> Su questo principio si basa il funzionamento delle **smart antennas**, capaci di variare la loro direzione di puntamento in real-time (particolarità che la singola antenna non può effettuare) ed è ciò che accade nei sistemi di telecomunicazioni moderni, come quelli di telefonia.
> Nella copertura wi-fi domestica, ad esempio, il modem è in grado di seguire l'utente, al fine di offrirgli sempre la massima direttività possibile.

##### Come è possibile gestire i parametri della schiera attraverso la sola alimentazione?
Sia supposto di trovarsi in una situazione di **non accoppiamento tra antenne**, cioè il campo irradiato da un'antenna non risente di quello delle altre.

Si rievoca dunque, l'espressione del campo elettrico nella Far Field region:
$$
\underline{E}(r, θ, Φ) = -j \frac{β_0 ζ_0}{4π} \frac{e^{-j β_0 r}}{r} [N_θ(θ, Φ) \hat{θ} + N_Φ(θ, Φ) \hat{Φ}] = \frac{e^{-j β_0 r}} {r} A \underline{C}(θ, Φ)
$$
dove sono state isolate le seguenti componenti:
- $A$: è il **coefficiente di alimentazione** che rappresenta l'ampiezza e la fase dell'eccitazione che dà origine al campo irradiato;
- $C(θ, Φ)$: è la **funzione caratteristica** dell'antenna, che rappresenta la dipendenza direzionale del campo elettrico dell'elemento.

# 4.2 - Array Lineare
![[Linear Array.png]]
Si consideri una **matrice lineare di N elementi radianti identici**. La distanza tra elementi adiacenti è **d**.
Si sceglie, come asse di posizionamento, l'asse $z$, allo scopo di utilizzare nuovamente i formalismi del Capitolo [[2 - Antenna Fundamentals#2.2 - Il sistema di riferimento sferico]]. <br>
I **radiatori**, cioè le antenne che formano la schiera, sono alimentati da un **oscillatore comune** attraverso una *rete ramificata*. <br>
In ogni ramo sono inseriti in serie:
- un **attenuatore (o amplificatore)**, in grado di modificare la potenza del segnale in ingresso;
- uno **sfasatore**, in grado di introdurre una variazione di fase

per controllare rispettivamente l'ampiezza e la fase del segnale che alimenta l'elemento di antenna in quel ramo. <br>
Per ciascun radiatore risulta:
$$
\underline{E}(r, θ, Φ) = A_n \frac{e^{-j β_0 R_n}} {R_n} \underline{C}(θ, Φ) = a_n e^{j ψ_n} \frac{e^{-j β_0 R_n}} {R_n} \underline{C}(θ, Φ)
$$
> $R_n$ è la distanza tra l'antenna n-esima e il punto di osservazione

Il *coefficiente di alimentazione* è in genere complesso (si pensi ad esempio alla corrente alternata) ed avrà quindi un termine modulo ed un termine fase. <br> 
*Per ipotesi le antenne irradiano in maniera indipendente*.
Sotto tale ipotesi, il campo elettrico totale può essere calcolato come la somma dei campi irradiati da tutti gli N componenti della schiera; inoltre, poiché le antenne sono tutte uguali, a parità di direzione di osservazione, la funzione caratteristica (che fornisce informazioni su come l'antenna irradia) è uguale per tutti i componenti ed è pari a:
$$
\underline{E}(r, θ, Φ) = \sum_{n=0}^{N-1}{\underline{E}_n(r, θ, Φ)} = \underline{C}(θ, Φ) A_r \sum_{n=0}^{N-1}{\frac{A_n}{A_r} \frac{e^{-j β_0 R_n}}{R_n}}
$$
> $A_r$ è un'alimentazione di riferimento utilizzata per la moltiplicazione e la divisione nel calcolo del campo elettrico. Tale componente si rivelerà essere proprio il coefficiente di alimentazione.

Per soddisfare la condizione di campo lontano per un array di lunghezza $l = (N-1) d$, la distanza del punto di osservazione $r$ dovrebbe essere sufficientemente grande, a tal punto che:
$$
r_F = \frac{2D^2}{λ_0} = \frac{(N-1)^2 d^2}{λ_0/2}
$$
Si sta così definendo una nuova distanza di Fraunhofer per un array di antenne.

## 4.2.1 - Regione di Fraunhofer di un array situato locato sull'asse $z$
Ora che si conosce la distanza tale per cui si può considerare un'antenna come interna alla regione di campo lontano, è necessario approssimare, ad un valore identico, le $R_n$ distanze di ogni antenna, facente parte dell'array, dal punto di osservazione. <br>
![[Linear array- Fraunhofer region.png]] <br>
Per calcolare l'approssimazione necessaria si prendono in conto delle considerazioni.
Se si immaginasse di portare P (punto di osservazione) ad una distanza sempre maggiore dall'array, le $R_n$ distanze diverrebbero uguali e parallele tra loro.
$R_n$ appare, nella [[Formula campo elettrico totale array]] al *denominatore della sommatoria* e all'*esponente di fase*. Per quanto concerne la sua presenza nel *termine di ampiezza*, si può approssimare $R_n$ a $r$, commettendo un errore fisso accettabile. <br>
**Prima approssimazione: $R_n = r$** <br>

Poiché quest'approssimazione non è applicabile al termine di fase, per sviluppare la seconda approssimazione si andrà dunque a considerare la distanza di indice $0$, cioè $r$, alla quale verrà sottratto l'errore commesso nel considerare la distanza n-esima $R_n = r$, ottenendo:
$$
R_n = r - \text{errore}_n
$$
Per calcolare l'errore è sufficiente applicare le formule dei triangoli rettangoli. <br>
Per l'antenna di indice $1$ vale la seguente equazione:
$$
\text{errore}_1 = d \hspace{1.2mm} \text* \cos{θ}
$$
dunque, per l'errore n-esimo varrà:
$$
\text{errore}_n = dn \hspace{1mm} \text* \cos{θ}
$$
Considerando che $\cos{θ} = \hat{z} \cdot \underline{\hat{r}}$, si può riscrivere l'errore come:
$$
\text{errore}_n = dn \hspace{1.2mm} \text* \hspace{1mm} \hat{z} \cdot \underline{\hat{r}}
$$
dove $dn \hat{z} = \underline{r_n}$ ossia il vettore posizione dell'n-esima antenna, perciò l'errore diverrà:
$$
\text{errore}_n = \underline{r_n} \cdot \hat{r} 
$$
**Seconda approssimazione: $R_n = r - \underline{r_n} \cdot \hat{r}$** <br>
È ora possibile calcolare il campo elettrico sfruttando le due approssimazioni individuate in precedenza:
$$
\begin{gather}

\underline{E}(r, θ, Φ) = \frac{e^{-j β_0 r}}{r} \underline{C}(θ, Φ) A_r \sum_{n=0}^{N-1} {\frac{A_n}{A_r} e^{j β_0 \underline{r}_n \cdot \hat{r}}} =

\\
\\

= \frac{e^{-j β_0 r}}{r} \underline{C}(θ, Φ) A_r \sum_{n=0}^{N-1}{\frac{A_n}{A_r} e^{j β_0(z_n \hat{z}) \cdot (\sin{θ} \cos{Φ} \hat{x} + \sin{θ} \cos{Φ} \hat{y} + \cos{θ} \hat{z})}} =

\\
\\

= \frac{e^{-j β_0 r}}{r} \underline{C}(θ, Φ) A_r \sum_{n=0}^{N-1}{\frac{A_n}{A_r} e^{j β_0 nd \cos{θ}}}

\end{gather}
$$

Si noti come:
- il primo termine (gli elementi antecedenti la sommatoria) dipende solo dall'elemento di indice $0$;
- il secondo elemento (l'intera sommatoria) dipende, invece, anche dalle alimentazioni dei singoli elementi e da $θ$.

## 4.2.2 - Principio di moltiplicazione dei pattern
$$
S(r, θ, Φ) = \frac{|A_r|^2 |\underline{C}(θ, Φ)|^2}{2 ζ_0 r^2} |\sum_{n=0}^{N-1}{\frac{A_n}{A_r} e^{j β_0 nd \cos{θ}}}|^2  = S_e(r, θ, Φ) F_a
$$
La densità di potenza dell'array è il prodotto di due fattori. Il primo fattore $S_e$ è la densità di potenza irradiata da un singolo elemento assunto come riferimento, il secondo è il fattore di array:
$$
F_a = |\sum_{n=0}^{N-1} {\frac{A_n}{A_r} e^{j β_0 nd \cos{θ}}}|^2 = |\sum_{n=0}^{N-1} {\frac{a_n}{a_r} e^{j(ψ_n - ψ_r)} e^{j β_0 nd \cos{θ}}}|^2
$$

Il **fattore di array** è *funzione delle posizioni dei singoli elementi* e dei *loro coefficienti di alimentazione*, ma non della specifica tipologia di radiatori utilizzati. <br>
**Il principio della moltiplicazione dei modelli consente la valutazione della densità di potenza dell'array calcolando prima il modello di potenza con gli elementi dell'array sostituiti con radiatori isotropi, che produce il fattore dell'array, e quindi moltiplicando il risultato per la densità di potenza per un singolo elemento**. <br>
Il fattore di array è governato dalla **distribuzione di ampiezza dell'array** $a_n$, che serve a controllare la *forma del diagramma* di radiazione dell'array, e dalla **distribuzione di fase dell'array** $ψ_n$, che può essere utilizzata per *orientare la sua direzione*. <br>
Questo è importantissimo poiché sta a significare che è possibile far variare:
- forma e ampiezza del lobo principale, variando l'ampiezza del coefficiente di alimentazione dei singoli elementi.
- direzione di puntamento variando la fase del coeff. di alimentazione dei singoli elementi.

# 4.3 - Array Lineare Uniforme
Si consideri un array lineare avente una **distribuzione di ampiezza uniforme** ($\frac{a_n}{a_0} = 1$, l'ampiezza del coefficiente di alimentazione è uguale per tutti gli elementi) e un **ritardo di fase da elemento a elemento linearmente progressivo** ($ψ_n - ψ_0 = nδ$, la differenza di fase tra due elementi vicini tra loro è sempre la stessa). <br>
Si noti che l'elemento con indice $0$ è preso come riferimento:
$$
F_a = |\sum_{n=0}^{N-1} {e^{jn(β_0 d \cos{θ + δ)}}}|^2 = |\sum_{n=0}^{N-1} {e^{jnφ}}|^2 = |\frac{\sin{(Nφ/2)}}{\sin{(φ/2)}}|^2
$$
Da tale espressione di $F_a$ si può dedurre che il fattore di array assume valore massimo quando è verificata la seguente uguaglianza:
$$
F_{a_{max}}(φ) = N^2 \hspace{5mm} \text{con} \hspace{5mm} φ = β_0 d \cos{θ + δ} = 0
$$
ed è proprio grazie a quest'ultima che si comprende che la densità di potenza dipende direttamente dal fattore di array, dunque la densità di potenza massima (e quindi anche la direzione di puntamento dell'array) dipende dal valore massimo del fattore di array.

## 4.3.1 - Broadside Linear Array
Questo array ha il fascio principale del diagramma di radiazione sempre nella direzione ortogonale all’asse dell’array. Per tale motivo, questo tipo di array ha $F$ massimo per $θ=\frac{π}{2}$.
Imponiamo quindi che $θ$ sia pari a $π/2$ nella [[Formula di F massimo (fattore di array)]] e otteniamo:
$$
θ_{max} = \cos^{-1}{\frac{-δ}{β_0d}} = \frac{π}{2} \hspace{10mm} \rightarrow \hspace{10mm} δ = 0
$$
ovvero, che $θ = π/2$ quando $δ = 0$. Ciò significa che non vi è differenza di fase nell'alimentazione dei singoli elementi dell'array, perciò tutti gli elementi hanno la stessa ampiezza e la stessa fase in alimentazione. <br>
Si dirà, quindi, che: **un array lineare broadside è costituito da elementi in fase**. <br>
### 4.3.1.1 - Guadagno di un array lineare broadside
![[Guagano array broadside-1.png]] <br>
Per capire come si comporta il guadagno per questo tipo di array, basta considerare una schiera di array di dipoli a mezz'onda. Tale array sarà più direttivo di un singolo dipolo a mezz'onda.
Per calcolare quanto detto sopra bisogna effettuare i seguenti passaggi:

<br>
![[Guadagno array broadside-2.png]] <br>


## 4.3.2 - Endfire Linear Array
Questo array ha il lobo principale del diagramma di radiazione lungo l'asse dell'array

$$
θ_{max} = \cos^{-1}{\frac{-δ}{β_0 d}} = 0,π \hspace{10mm} \rightarrow \hspace{10mm} δ = \mp β_0d
$$

## 4.3.3 - Beam Scanning


# 4.4 - Smart Antenna Array


## 4.4.1 - Switched Beam Antennas


## 4.4.2 - Adaptive Antennas


### 4.4.2.1 - Multipath


# 4.5 - Sistemi di Antenne MIMO
