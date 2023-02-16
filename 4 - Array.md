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
## 4.2.1 - Principio di moltiplicazione dei pattern

# 4.3 - Array Lineare Uniforme

## 4.3.1 - Broadside Linear Array

## 4.3.2 - Endfire Linear Array

## 4.3.3 - Beam Scanning

# 4.4 - Smart Antenna Array

## 4.4.1 - Switched Beam Antennas

## 4.4.2 - Adaptive Antennas

### 4.4.2.1 - Multipath

# 4.5 - Sistemi di Antenne MIMO
