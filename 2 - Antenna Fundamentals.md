Nel campo delle trasmissioni, il compito di un'antenna è quello di percepire un segnale via cavo per poi trasmetterlo, un'altra antenna si occuperà poi di percepire quello stesso segnale e il ricevitore di riconoscerlo nel modo corretto.

Un'antenna è un dispositivo che permette di convertire i campi elettromagnetici guidati in campi elettromagnetici irradiati, che viaggiano nello spazio circostante (antenna trasmittente) o viceversa(antenna ricevente).

Le proprietà di radiazione e impedenza di un'antenna dipendono dalla forma, misura e proprietà del materiale di cui è composta.

Inoltre, per la maggior parte delle antenne vale il *Teorema di reciprocità*, il quale afferma che un'antenna ha le stesse caratteristiche di radiazione sia per la trasmissione che per la ricezione.

# La regione di campo lontano (Far-Field Region)
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

# Il sistema di riferimento sferico
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
L'angolo che si forma tra l'asse $z$ è l'angolo $θ$, il quale varia tra 0°-180°, a seconda della posizione sul *semiasse positivo* o *negativo* di $z$.

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

# Polarizzazione del campo elettrico
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

# Potenza irradiata
Dati $\tilde{E}$ e $\tilde{H}$ in forma fasoriale, il **vettore di Poynting medio** dell'onda irradiata, anche detto **densità di potenza**, si può ottenere tramite la seguente formula:
$$
\begin{multline}

\underline{S}(\underline{r}) = \frac{1}{2} \underline{E}(\underline{r}) \times \underline{H}^*(\underline{r}) = \frac{1}{2} \underline{E}(\underline{r}) \times [\frac{1}{ζ_0} \hat{r} \times \underline{E}(\underline{r})]^* = \frac{|\underline{E}(\underline{r})|^2}{2ζ_0} \hat{r} = S(\underline{r}) \hat{r}
\tag*{Poynting's vector}

\\
\\
\end{multline}
$$
___
$$
\begin{multline}

S(r, θ, Φ) = \frac{|\underline{E}(r, θ, Φ)|^2} {2ζ_0} \hspace{15mm}[W/m^2] \tag*{power density}
\\
\\
\end{multline}
$$
___
$$
\begin{multline}

U(θ, Φ) = r_0^2 S(r_0, θ, Φ) = r_0^2 |\underline{E}(r_0, θ, Φ)|^2 / 2ζ_0 \hspace{15mm} [W] \hspace{30mm}\tag*{radiation intensity}
\\
\\
\end{multline}
$$
___
Il diagramma di radiazione di una qualsiasi antenna è descritto in termini dell'**intensità di radiazione normalizzata $F(θ, Φ)$**, definita come il rapporto tra la *densità di potenza $S(R, θ, Φ)$* e $S_{max}$, il massimo valore di $S(R, θ, Φ)$ ad una data distanza $R$:
$$
\begin{multline}

F(θ, Φ) = U(θ, Φ) / U_{max} = S(r_0, θ, Φ) / S_{max} \leq 1 \tag*{normalized radiation intensity}

\\
\\
\end{multline}
$$
___
La *potenza totale* irradiata da un'antenna attraverso una superficie sferica ad una distanza fissa R si ottiene integrando come segue:
$$
\begin{multline}

P_{rad} = \int_0^π \int_0^{2π} {S(r_0, θ, Φ) \hat{r} \hat{r} r_0^2 \sin{θ} dΦ dθ} = \int_0^π \int_0^{2π} {\frac{|\underline{E}(r_0, θ, Φ)|^2} {2ζ_0} r_0^2 \sin{θ} dΦ dθ} \tag*{total radiated power}

\\
\\
\end{multline}
$$
# Radiation pattern (Diagramma di radiazione)
![[Radiation pattern.png]]
![[Radiation pattern - 2.png]]
