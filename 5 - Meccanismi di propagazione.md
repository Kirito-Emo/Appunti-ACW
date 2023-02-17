Finora è stato osservato il comportamento, nella regione di campo lontano, del campo elettrico e magnetico irradiati dalle antenne <br>
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

# 5.1 - Onde piane uniformi
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

## 5.1.1 - Campo elettrico e magnetico di onde piane uniformi
Un’onda piana si dice quindi uniforme quando $\underline{α} = α \hat{β}$. Potremo quindi scrivere il campo elettrico come:
$$
\underline{E}(\underline{r}) = \underline{E}_0 e^{-j (β - jα) \hat{β} \cdot \underline{r}} = \underline{E}_0 e^{-j k \hat{β} \cdot \underline{r}} = \underline{E}_0 e^{-α \hat{β} \cdot \underline{r}} e^{-j β \hat{β} \cdot \underline{r}}
$$
<br> dove
- $k$ è la **costante di propagazione** o numero d'onda:
	$$
	k = β -j α = ω_0 \sqrt{μ ε_{eq}}
	$$
<br> Il campo elettrico potrà essere riscritto come:
$$
\underline{H}(\underline{r}) = \underline{H}_0 e^{-j k \hat{β} \cdot \underline{r}} = \frac{1}{ζ} \hat{β} \times \underline{E}_0 e^{-j k \hat{β} \cdot \underline{r}} \equiv \frac{1}{\sqrt{μ/ε_{eq}}} \hat{β} \times \underline{E}_0 e^{-j k \hat{β} \cdot \underline{r}}
$$
Il campo magnetico ha una struttura identica a quella dell'elettrico. Il vettore $H_0$, che dipende dal punto di osservazione, può essere scritto in funzione del vettore $E_0$, dove $ζ$ è l'impedenza intrinseca del mezzo di propagazione.
In generale, dunque anche nel caso di trasmissione con perdite, l'impedenza può essere riscritta come in formula, dove $μ$ e $ε$ sono rispettivamente la *permeabilità dello spazio libero* e *costante dielettrica complessa*.
Mentre, nel caso di propagazione senza perdite (σ = 0) risulta: <br>
$$
α = 0 \hspace{10mm} \text{e} \hspace{10mm} k = β = ω_0 \sqrt{με}
$$
<br>
Il prodotto vettoriale ci dice che campo elettrico, magnetico e versore $β$ sono tra loro perpendicolari, questa terna ha nello spazio sempre la stessa configurazione.
Il **prodotto tra campo elettrico e magnetico fornisce sempre la direzione di fase** (che si scoprirà essere proprio la direzione di propagazione).

## 5.1.2 - Vettore di Poynting di onde piane uniformi

$$
\underline{S}(\underline{r}) = \frac{1}{2} \underline{E}(\underline{r}) \times \underline{H}^*(\underline{r}) = \frac{1}{2} [\underline{E}_0 e^{-j k \hat{β} \cdot \underline{r}}] \times [\frac{1}{ζ} \hat{β} \times \underline{E}_0 e^{-j k \hat{β} \cdot \underline{r}}]^* = \frac{|\underline{E}_0|^2}{2 ζ^*} e^{-2 α \hat{β} \cdot \underline{r}} - \hat{β} = S(\underline{r})\hat{β}
$$
<br>
Si noti che il vettore di Poynting è diretto nella direzione di $\hatβ$, dunque si può affermare che **in una propagazione piana uniforme $\hatβ$ identifica la direzione di Poynting**.
In assenza di perdite, la costante di attenuazione è uguale a quella di fase, per cui il termine esponenziale diventa 1  ($e^{-2 α \hat{β} \cdot \underline{r}} = 1$) e l'impedenza intrinseca risulta puramente reale.

# 5.2 - Riflessione e Trasmissione delle onde piane


# 5.3 - Confine tra i due mezzi (senza perdite) e Leggi di Snell


## 5.3.1 - Legge della riflessione di Snell


## 5.3.2 - Legge della rifrazione di Snell


# 5.4 - Polarizzazione parallela e perpendicolare


## 5.4.1 - Polarizzazione parallela


## 5.4.2 - Polarizzazione perpendicolare


# 5.5 - Angolo di Brewster


# 5.6 - Angolo critico


## 5.6.1 - Caso A


## 5.6.2 - Caso B


## 5.6.3 - Caso C


# 5.7 - Riflettività e Trasmittività


# 5.8 - Esempio di due mezzi non magnetici


# 5.9 - Confine tra mezzo senza perdite e conduttore


## 5.9.1 - Campo elettrico e magnetico se il mezzo 2 è un conduttore


### 5.9.1.1 - Campo elettrico e magnetico nel mezzo 1


### 5.9.1.2 - Campo elettrico e magnetico nel mezzo 2


### 5.9.1.3 - Differenza tra onde piane uniformi e non uniformi


## 5.9.2 - Leggi di Snell se il mezzo 2 è un conduttore


### 5.9.2.1 - Legge di riflessione di Snell


### 5.9.2.2 - Legge di rifrazione di Snell


## 5.9.3 - Coefficienti di Fresnel se il mezzo 2 è un conduttore


## 5.9.4 - Riflettività e Trasmittività


# 5.10 - Confine tra conduttore e PEC


## 5.10.1 - Coefficienti di riflessione e trasmittività di Fresnel 


# 5.11 - Lastra lossless


# 5.12 - Ottica geometrica


## 5.12.1 - I limiti della GO


# 5.13 - Diffrazione


## 5.13.1 - Principio di Huygens


# 5.14 - Teoria geometrica della diffrazione


## 5.14.1 - Il cono di Keller


## 5.14.2 - Caso bidimensionale


# 5.15 - Uniform GTD


# 5.16 - Confronto tra i campi previsti dalla GO e i campi reali che tengono conto del contributo del campo UTD
