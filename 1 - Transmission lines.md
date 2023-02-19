# 1.1 - Elementi iniziali essenziali
- *l* è la lunghezza del collegamento
- *λ* è la lunghezza dell'onda
- *ω* è la frequenza angolare pari a *2πf*
- *c* è la velocità della luce
- *l/c* è il ritardo di propagazione
# 1.2 - Modi propaganti
## 1.2.1 - Linee di trasmissione trasverso-elettromagnetiche (TEM)
Le onde che si propagano lungo queste linee sono formate da campi elettrici e magnetici completamente trasversi rispetto alla direzione di propagazione.
Una caratteristica comune delle linee TEM è quella di essere formate da due linee parallele conduttive.
Tra le linee TEM compaiono:
- Linea coassiale
- Linea bifilare
- Linea a piani paralleli
- Linea di trasmissione
- Linea Micro-strip
## 1.2.2 - Linee di trasmissione di ordine superiore
Le onde che si propagano lungo queste linee hanno almeno un componente significativo del campo rivolto nella direzione di propagazione.
Tra le linee di ordine superiore si trovano:
- Guide d'onda
- Barre dielettriche
- Fibre ottiche
# 1.3 - Modello a costanti concentrate
![[Rappresentazione TEM.png]]
Questa rappresentazione, detta ***modello circuitale a costanti concentrate***, è formata da 4 elementi fondamentali, detti ***parametri della linea di trasmissione***:
- **R'**: la *resistenza* complessiva di entrambi i conduttori per unità di lunghezza (Ω/m)
- **L'**: l'*induttanza* complessiva di entrambi i conduttori per unità di lunghezza (H/m)
- **G'**: la *conduttanza* del mezzo isolante per unità di lunghezza (S/m)
- **C'**: la *capacità* dei due conduttori per unità di lunghezza (F/m)

![[Formule parametri.png]]
![[Parametri geometrici significativi.png]]

- $μ_c$ e $σ_c$ sono la **permabilità magnetica** e la **conducibilità elettrica** dei conduttori
- $ε$, $μ$ e $σ$ sono la **permittività elettrica**, la **permabilità magnetica** e la **conducibilità elettrica** del materiale isolante che separa i conduttori
# 1.4 - Equazioni dei telegrafisti
Equazione per $\tilde{V}$:
$$
- \frac{d\tilde{V}}{dz} = (R' + jωL')\tilde{I}(z)
$$
Equazione per $\tilde{I}$
$$
-\frac{d\tilde{I}}{dz} = (G' + jωC')\tilde{V}(z)
$$
Queste sono le equazioni del telegrafo in forma fasoriale, dove $\tilde{V}$ e $\tilde{I}$ sono fasori.
## 1.4.1 - Propagazione delle onde in una linea di trasmissione
Le due equazioni precedenti possono essere disaccoppiate per ottenere un'equazione d'onda disaccoppiata del secondo ordine per ciascun fasore.
L'equazione per $\tilde{V}$ si ricava derivando entrambi i membri dell'[[equazione 1.0]] rispetto a $z$ ottenendo:
$$
-\frac{d^2 \tilde{V}(z)}{d^2z} = (R' + jωL') \frac{d\tilde{I}(z)}{dz}
$$
sostituendo poi l'[[equazione 2.0]] al posto di $\frac{d\tilde{I}(z)}{dz}$ diventa:
$$
\frac{d^2 \tilde{V}(z)}{d^2z} - (R' + jωL') (G' + jωC')\tilde{V}(z) = 0
$$
da cui:
$$
\frac{d^2 \tilde{V}(z)}{d^2z} - γ^2\tilde{V}(z) = 0
$$
dove
$$
γ = \sqrt{(R' + jωL') (G' + jωC')}
$$

Applicando lo stesso procedimento all'equazione di $\tilde{I}$, ma in ordine inverso, si ottiene:
$$
\frac{d^2\tilde{I}(z)}{d^2z} - γ^2\tilde{I}(z) = 0
$$
L'equazione [[1.1]] e la [[2.1]] sono dette *equazioni d'onda*, γ è detta *costante di propagazione complessa* della linea di trasmissione.
γ è composta da una parte reale, α, detta *costante di attenuazione* della linea (Np/m) e una parte immaginaria, β, detta *costante di fase* della linea (rad/m), pertanto:
$$
γ = α + jβ
$$
Le equazioni d'onda [[1.1]] e [[2.1]] hanno come soluzioni delle *onde progressive* che hanno la seguente forma:
$$
\begin{align*}
\tilde{V}(z) = V_0^+ e^{-γz} + V_0^- e^{γz} \tag*{V}
\\
\tilde{I}(z) = I_0^+ e^{-γz} + I_0^- e^{γz} \tag*{A}
\end{align*}
$$
dove $e^{-γz}$ rappresenta la *propagazione* dell'onda nella direzione delle z positive, mentre  $e^{γz}$ rappresenta la *propagazione* dell'onda nella direzione delle z negative.
# 1.5 - Lossless TLs
Una linea di trasmissione è caratterizzata da due proprietà fondamentali:
- la costante di propagazione $γ$
- l'impedenza caratteristica $Z_0$
definite entrambe in termini della frequenza angolare $ω$ e dei parametri della linea *R'*, *L'*, *G'*, *C'*.

In molte situazioni concrete la linea di trasmissione si può progettare in modo tale da ridurre al minimo le perdite ohmiche, di modo che *R'* e *G'* assumano valori piccoli, tali che *$R' \ll ωL'$* e *$G' \ll ωC'$*.
Queste condizioni di assenza di perdite nella linea permettono di porre $R' = G' = 0$ nell'equazione di $γ$, da cui si ottiene:
$$
γ = α + jβ = jω\sqrt{L'C'}
$$
il che significa che:
- $α = 0$ (linea senza perdite)
- $β = ω\sqrt{L'C'}$ (linea senza perdite)

Successivamente si calcola l'impedenza:
$$
\begin{align*}
Z_0 = \sqrt{\frac{L'}{C'}} \tag{Linea senza perdite}
\end{align*}
$$ 
che in questo caso è un numero reale.

![[Tabella 2.2.png]]

## 1.5.1 - Coefficiente di riflessione in tensione
Ponendo $γ = jβ$ per la linea lossless, le espressioni della tensione complessiva e corrente complessiva nella linea, date dalle equazioni [[Onde progressive]], diventano:
$$
\begin{align*}
\tilde{V}(z) = V_0^+ e^{-jβz} + V_0^- e^{jβz}
\\
\\
\\
\tilde{I}(z) = \frac{V_0^+}{Z_0} e^{-jβz} + \frac{V_0^-}{Z_0} e^{jβz}
\end{align*}
$$
Le due incognite contenute in queste espressioni sono $V_0^+$ e $V_0^-$, ovvero le ampiezze in tensione dell'onda incidente e dell'onda riflessa.
Per deeterminarle si deve considerare la TL senza perdite nel quadro del circuito completo, che si compone anche di un'impedenza arbitraria $Z_L$.
Sul carico, il fasore $\tilde{V}_L$ e $\tilde{I}_L$ sono legati tramite l'impedenza $Z_L$ come segue:
$$
Z_L = \frac{\tilde{V}_L}{\tilde{I}_L}
$$
![[Circuito completo calcolo $Z_L$.png]]
$\tilde{V}_L$ e $\tilde{I}_L$ sono calcolabili tramite le [[Equazioni tensione e corrente complessiva]] entrambe valutate in $z=0$
$$
\begin{align*}
\tilde{V}_L = \tilde{V}(z=0) = V_0^+ + V_0^-
\\
\\
\\
\tilde{I}_L = (z=0) = \frac{V_0^+}{Z_0} - \frac{V_0^-}{Z_0}
\end{align*}
$$
Sostituendo, si può calcolare quanto segue:
$$
Z_L = \frac{V_0^+ + V_0^-}{V_0^+ - V_0^-}Z_0
$$
Ricavando $V_0^-$ si ha:
$$
V_0^- = \frac{Z_L - Z_0}{Z_L + Z_0}V_0^+
$$
Il rapporto tra l'***ampiezza dell'onda di tensione riflessa*** e l'***ampiezza dell'onda di tensione incidente al carico*** è noto come ***coefficiente di riflessione in tensione Γ***.
Γ dipende solo da $Z_L$, cioè l'impedenza di carico, normalizzata all'impedenza caratteristica della linea $Z_0$.
In generale $Z_L$ è una quantità complessa, dunque anche Γ, in generale, è una quantità complessa:
$$
Γ = |Γ|e^{jθ_r}
$$
dove $|Γ|$ è il modulo di Γ e $θ_ρ$ è il suo angolo di fase. Si noti che $|Γ| \le 1$.
Un carico è detto *adattato alla linea* se $Z_L = Z_0$, perché in tal caso non si ha *riflessione* da parte del carico stesso ($Γ=0$ e $V_0^- = 0$).

## 1.5.2 - Impedenza di input
Gli andamenti delle onde stazionarie indicano che in una linea disadattata i moduli delle tensioni e delle correnti oscillano in funzione della posizione lungo la linea e sono in opposizione di fase tra di loro.
Dunque, anche il rapporto tra tensione e corrente, detto ***impedenza di ingresso $Z_{in}$*** dovrà variare in funzione della posizione.
Si otterrà:
$$
\begin{gather}
Z_in(z) = \frac{\tilde{V}(z)}{\tilde{I}(z)} \\

& = \frac{V^+_0 [e^{-jβz} + Γe^{jβz}]}{V^+_0 [e^{-jβz} - Γe^{jβz}]} Z_0 \\

& = Z_0 [\frac{1 + Γe^{j2βz}}{1 - Γe^{j2βz}}] \tag*{Ω}
\end{gather}
$$
Si noti che $Z_{in}$ è il *rapporto tra la tensione complessiva dell'onda incidente e di quella riflessa e la corrente complessiva in un arbitrario punto z della linea*, diversamente dall'impedenza caratteristica della linea $Z_0$, che dipende dalla tensione e dalla corrente di ciascuna delle due onde prese individualmente: $Z_0 = V^+_0 / I^+_0 = -V^-_0 / I^-_0$ .
In molti problemi inerenti le TL è di particolare interesse l'impedenza all'ingresso della linea in $z = -l$, che è data da:
$$
\begin{gather}

Z_{in} = 

Z_0 [\frac{e^{-jβz} + Γe^{jβz}}{e^{-jβz} - Γe^{jβz}}] \\ =

Z_0 [\frac{1 + Γe^{j2βz}}{1 - Γe^{j2βz}}] \tag*{Ω}

\end{gather}
$$
Sostituendo Γ e sfruttando le relazioni
$$
\begin{align}

e^{jβl} = cosβl + jsinβl
\\
e^{-jβl} = cosβl - jsinβl

\end{align}
$$
si può riscrivere come:
$$
\begin{gather}

Z_{in} = 

Z_0 [\frac{Z_L cosβl + j Z_0 sinβl}{Z_0 cosβl + j Z_L sinβl}] \\
\\ =

Z_0 [\frac{Z_L + j Z_0 tanβl} {Z_0 + j Z_L tanβl}] \tag*{Ω}

\end{gather}
$$
![[Formule inverse impedenza in input.png]]
## 1.5.3 - Trasferimento di potenza in una Lossless TL
### 1.5.3.1 - Potenza media
Il flusso di potenza media è uguale alla potenza istantanea mediata su un periodo temporale $T = 1/f = 2π/ω$.

Per l'onda incidente, la potenza media è:
$$
\begin{align}

P^i_{av} = \frac{1}{T} \int_0^T{P^i(t)dt} \\
= \frac{ω}{2π} \int^{2π/ω}_{0}{P^i(t)dt} \\
= \frac{1}{2} Re[V I^*] \\
= \frac{|V_0^+|^2}{2Z_0} \tag*{W}

\end{align}
$$
dove $P^i(t)$ è la potenza immediata.

>La presenza di $1/2$ è conseguenza dell'integrazione di $cos^2(ωt + φ^+)$ su un periodo.

Dall'analogo procedimento applicato all'onda riflessa si ha:
$$
P^r_{av} = - |Γ|^2 \frac{|V_0^+|^2}{2Z_0} = - |Γ|^2 P^i_{av} 
$$
Perciò il modulo della potenza media riflessa è uguale alla potenza media incidente ridotta di un fattore moltiplicativo pari a $|Γ|^2$.
La *potenza media netta* trasferita al carico è:
$$
P_{av} = P_{av}^i + P_{av}^r = \frac{|V_0^+|^2}{2Z_0} [1 - |Γ|^2] \tag{W}
$$
# 1.6 - Adattamento delle reti
![[Circuito-Quarto-d'Onda.png]]
Lo scopo dell'adattamento delle reti è quello di eliminare le riflessioni nel punto MM'. È possibile ottenere ciò, progettando la rete in modo da avere l'impedenza in ingresso $Z_{in} = Z_0$. Se la rete è senza perdite tutta la potenza sarà re-direzionata verso il carico. 

## 1.6.1 - Trasformatore a quarto d'onda
Un caso particolare è quello in cui la lunghezza della linea è pari a un quarto d'onda, oppure $λ/4 + nλ/2$, dove $n=0$ o un intero positivo, che corrisponde a $βl = (2π/λ)(λ/4) = π/2$.

> Nella pratica sto andando ad aggiungere un pezzo di cavo chiamato *trasformatore a quarto d'onda*.

Il carico è $R_L \ne Z_0$ e l'adattamento della rete è composto da una TL caratterizzata da $Z_t$ e $l$.
Utilizzando la formula di trasporto dell'impedenza, $Z_0$ diventa:
$$
\begin{multline}

Z_0 = Z_{in} = Z_t \frac{R_L + j Z_t \tan{β_t l}} {Z_t + j R_L \tan{β_t l}}
\\
\rightarrow 
\\
Z_0 [Z_t + j R_L \tan{β_t l}] = Z_t [R_L + j Z_t \tan{β_t l}]

\end{multline}
$$
L'uguaglianza finale (nella precedente formula) tra due numeri complessi esiste se le due parti e i coefficienti immaginari sono uguali, tuttavia è sbagliata poiché le due parti reali devono essere diverse.

Dunque, questa formula è utilizzabile se $\tan{β_t l} \rightarrow \infty$, ovvero eliminando la parte reale e agendo sulla tangente, in modo tale da avere:
$$
\begin{align}

β_t l = (2n+1) \frac{π}{2} \rightarrow l = (2n+1) \frac{λ_0}{4} \tag*{n = 0, 1, 2, ...}

\end{align}
$$
dove la componente $\frac{λ_0}{4}$ lascia intuire che si tratti di un quarto d'onda.
Effettuando tali operazioni, avrò:
$$
Z_t = \sqrt{R_L Z_0}
$$
> Quando il carico è complesso si dovrà scegliere la sezione della linea principale in modo tale che l'impedenza d'ingresso sia puramente resistiva.

Se, invece, il carico $Z_L \ne Z_0$, l'inserimento dell'adattamento di rete non avviene nel punto AA', ma nel punto in cui $z = -l'$, cioè quando il coefficiente di riflessione e l'impedenza in ingresso sono entrambi reali, ottenendo la seguente quantità:

$$
\begin{multline}

Z_{in}(z) = Z_0 \frac{1 + Γ(z)}{1 - Γ(z)}
\\

\rightarrow
\\

Z_{in}(z = -l') = Z_0 \frac{1 + |Γ_L| e^{j(Φ_{Γ_L} - 2βl')}}{1 - |Γ_L| e^{j(Φ_{Γ_L} - 2βl')}}

\end{multline}
$$
la quale è reale se $Φ_{Γ_L}- 2βl' = 0, \pm π$.

Solo a quel punto il trasformatore a quarto d'onda può essere applicato al carico $R_L = Z_{in}(z = -l')$.

# 1.7 - Lossy TLs
Questo è il caso con perdite, in cui la *costante di attenuazione α*, della quale si compone γ (costante di propagazione), è diversa da zero, ottenendo una γ complessa.

In questo caso $R', G' \ne 0$, per tale motivo l'equazione di γ diventa:
$$
γ = j ω_0 \sqrt{L' (1 - j \frac{R'}{ω_0 L'}) C'(1 - j \frac{G'}{ω_0 C'})} = j ω_0 \sqrt{L'_{eq} C'_{eq}} = α + jβ
$$

La linea di trasmissione viene, a questo punto, definita ***dispersiva***. Questo fa in modo che il segnale si deformi lungo la linea.

Anche l'impedenza risulterà essere complessa, difatti nel calcolo delle componenti fasoriali $\tilde{V}$ e $\tilde{I}$ compariranno i termini $e^{-αz}$ ed $e^{αz}$, i quali non sono termini di fase, ma portano ad un abbattimento del livello del segnale nel momento di trasmissione.

$$
\begin{align}

V(z) = V^+ e^{-γz} + V^- e^{γz} = V^+ e^{-αz} e^{-jβz} + V^- e^{αz} e^{jβz}

\\
\\

I(z) = \frac{1}{Z_0} [V^+ e^{-γz} + V^- e^{γz}] = I^+ e^{-αz} e^{-jβz} + I^- e^{αz} e^{jβz}

\end{align}
$$
$$
Z_0 = \sqrt{\frac{L'_{eq}} {C'_{eq}}} = |Z_0| e^{jΦ_z}
$$

## 1.7.1 - Condizione di Heaviside
Se si progetta opportunamente il cavo in utilizzo, si può ottenere anche una linea non dispersiva, in cui vi è ancora la presenza della componente α come della β, ma tornano in una condizione lossless, ottenendo una linea che presenta ancora perdita, ma non dispersione.

$$
\begin{align}

\frac{R'}{L'} = \frac{G'}{C'}

\\
\\

α = \sqrt{R'G'}
\\
β = \sqrt{L'C'}

\\
\\

Z_0 = \sqrt{\frac{L'_{eq}} {C'_{eq}}} = \sqrt{\frac{L'}{C'}}

\end{align}
$$
dove $Z_0$ è un numero reale e non più complesso.

## 1.7.2 - Perdita di potenza (dB)
Nella linea con perdita, a causa di quest'ultime, la potenza che arriva nella sezione del carico non è la stessa che immetto nella linea.

La potenza immessa nella rete è pari a:
$$
P_{av}^{in} = \frac{|V^+|^2}{2Z_0} e^{2αl} - \frac{|V^-|^2}{2Z_0} e^{-2αl} = \frac{|V^+|^2}{2Z_0} [e^{2αl} - |Γ_L|^2 e^{-2αl}]
$$
mentre quella in uscita diventa:
$$
P_{av}^{out} = \frac{|V^+|^2}{2Z_0} [1 - |Γ_L|^2]
$$

Calcolando la potenza in dB, al fine di misurare più precisamente la potenza in funzione delle perdite, si ha:
$$
P_{L_{dB}} = 10 \log{\frac{P_{av}^{in}} {P_{av}^{out}}} = 10 \log{\frac{e^{2αl} - |Γ_L|^2 e^{-2αl}} {1 - |Γ_L|^2}}
$$

dove le perdite di potenza, in condizione di adattamento (matched -> mc) del carico alla linea, sono pari a:
$$
PL_{dB}^{mc} = 10 \log{(e^{2αl})} = 8.69 αl
$$
in cui è presente la costante di attenuazione moltiplicata per la lunghezza della linea.

L'impedenza in input, soggetta anch'essa alle perdite, muterà e vedrà la comparsa nella sua formula della tangente iperbolica di gamma:
$$
Z_{in}(z = -l) = Z_0 \frac{Z_L + Z_0 \tanh{γl}} {Z_0 + Z_L \tanh{γl}}
$$

# 1.8 - Connettori
## 1.8.1 - Connettori N
I **connettori N**:
- sono versatili e possono essere utilizzati per applicazioni ad alta potenza;
- sono fisicamente abbastanza grandi e spesso utilizzati per terminare cavi a bassa perdita di grande diametro;
- **devono essere allineati e avvitati insieme**, esercitando una forza notevole;
- sono meccanicamente robusti e adatti per uso esterno (con protezione dalla pioggia);
- possono essere utilizzati a $10 GHz$.

Si noti che esistono entrambi i tipi $50 Ω$ e $75 Ω$.
I due sono visivamente quasi identici tranne che per il diametro del conduttore centrale e si accoppieranno tra loro (al punto da essere avvitati insieme), ma un maschio da $75 Ω$ farà solo un contatto intermittente con una femmina da $50 Ω$ e un maschio da $50 Ω$ farà piegare le molle di una femmina $75 Ω$.
I problemi di connessione risultanti sono frustranti per il debug. <br>
![[connettori N.png]] <br>
## 1.8.2 - Connettori BNC
I **connettori BNC** sono estremamente comuni nei lavori a bassa frequenza e i cavi così equipaggiati sono spesso noti genericamente come cavi coassiali.
I connettori utilizzano un comodo approccio di attacco *twist-on* e *twist-off* e sono meccanicamente resistenti e facili da usare, anche se la connessione al cavo a volte è fatta in modo impreciso e si guasta sul campo.
I connettori BNC sono teoricamente adatti a $4 GHz$, ma il loro utilizzo al di sopra di $1 GHz$ è sconsigliato. <br>
![[connettori BNC.png]] <br>