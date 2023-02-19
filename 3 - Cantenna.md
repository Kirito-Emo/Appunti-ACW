Una guida d'onda è una struttura lineare (metallica o dielettrica), che convoglia e confina onde elettromagnetiche all'interno di un percorso compreso fra le due estremità consentendone cioè una propagazione guidata.
Essa, dunque, è un mezzo di trasmissione di un segnale su un canale di comunicazione.

# 3.1 - Introduzione
L'antenna ‘guida d'onda’, a volte chiamata **Cantenna** (da can: barattolo/lattina), utilizza un *barattolo di latta come guida d'onda* e un *filo corto saldato su un connettore N come sonda* per transizione da cavo coassiale a guida d'onda.
Può essere facilmente costruito acquistando soltanto il connettore e riciclando barattolo di latta
È un’antenna direzionale, utile per collegamenti Point-to-Point a breve e media distanza. Potrebbe anche essere utilizzato come alimentatore per una parabola o griglia. <br>
Non tutte le lattine sono adatte a costruire un'antenna poiché sussistono alcuni vincoli dimensionali:
1. i valori accettabili per il diametro $D$ dell’apertura del barattolo sono compresi tra $0,60$ e $0,75$ volte la lunghezza d'onda nell'aria alla frequenza di lavoro. <br>A $2,44 GHz$ la lunghezza d'onda è $12,2 cm$, quindi il diametro della lattina dovrebbe essere compreso nell'intervallo di $7,3 - 9,2 cm$.
2. La lunghezza L della lattina dovrebbe preferibilmente essere almeno $0,75 λ_G$ , dove $λ_G$ è la lunghezza d'onda guida ed è data da:
	
	$$
	λ_G = \frac{λ}{\sqrt{1 - (λ / 1.706 D)^2}}
	$$
	
	Per $D = 7,3 cm$ si necessita di una lattina di almeno $56,4 cm$, mentre per $D = 9,2 cm$ si ha bisogno di una lattina di almeno $14,8 cm$.
	Generalmente più piccolo è il diametro, più la lattina dovrebbe essere lunga.
	Per l'esempio che verrà proposto, si farà uso di lattine di olio che hanno un diametro di $8,3 cm$ e un'altezza di circa $21 cm$.
	
3.  La sonda per la transizione da cavo coassiale a guida d'onda dovrebbe essere posizionata ad una distanza S dal fondo del barattolo, data da:
	
	$$
	S = 0.25 λ_G
	$$
	
	La sua lunghezza dovrebbe essere $0,25λ$, che a $2,44 \hspace{1mm} GHz$ corrisponde a $3,05 cm$.
	Il guadagno per questa antenna sarà nell'ordine da $10$ a $14 \hspace{1mm} dBi$, con un'ampiezza del fascio di circa $60°$.
	

![[cantenna - 1.png]] <br>
> Il segnale che arriva dal cavo coassiale incontra il connettore N che lo collega alla struttura; questa ha il solo scopo di convogliare il segnale (è il monopolo la vera sorgente che irradia il segnale giunto dal cavo).
> La struttura si limita a mantenere confinato il segnale che esce dal monopolo fino all’uscita del cilindro (cioè appunto a guidarlo).
> Il valore di distanza $0.25 λ_G$ consente al segnale irradiato dal monopolo di sbattere sulla struttura in maniera costruttiva: quando arriva a sbattere sul fondo, prima di uscire si combina col segnale riflesso.

# 3.2 - Come costruire una cantenna
## 3.2.1 - Lista dei materiali:
- un connettore N femmina a vite;
- $4cm$ di filo di rame o ottone di $2 mm$ di diametro;
- una lattina dell'olio di $8,3 cm$ di diametro e $21 cm$ di altezza.

## 3.2.2 - Strumenti richiesti:
- apriscatole;
- righello;
- pinze;
- lima;
- saldatore;
- set di punte per metallo (con una punta da $1,5 cm$ di diametro);
- morsa o morsetto;
- chiave inglese;
- martello

## 3.2.3 - Costruzione
1. Con l'apriscatole, rimuovere con cautela la parte superiore del barattolo; <br>
	![[cantenna - 2.1.png]]
	
2. con il righello, misurare $6,2 cm$ dal fondo del barattolo e disegnare un punto. <br>Fare attenzione a misurare dal lato interno del fondo. <br>Usare un punzone (o una piccola punta da trapano o un cacciavite a croce) e un martello per segnare il punto. Ciò semplifica la perforazione precisa del foro. Fare attenzione a non modificare la forma del barattolo durante la foratura (inserendo nel caso, un blocco di legno nel barattolo); <br>
	![[cantenna - 2.2.png]]
	
3. con una punta da trapano di piccolo diametro, praticare un foro al centro della piastra. Aumentare il diametro del foro utilizzando punte di diametro crescente. Il foro dovrebbe coincidere esattamente col connettore N. Usare una lima per levigare il bordo del foro. <br>
	![[cantenna - 2.3.png]]
	
4. lisciare con la lima un’estremità del filo. Alla stessa estremità stagnare il filo o per circa $0,5 cm$ aiutandosi con la morsa;
5. con il saldatore stagnare il pin centrale del connettore. Tenendo il filo in verticale con le pinze, saldare il suo lato stagnato nel foro del perno centrale. <br>
	![[cantenna - 2.4.png]]
	
6. inserire una rondella e avvitare delicatamente il dado sul connettore. Tagliare il filo a $3,05 cm$ misurati dalla parte inferiore del dado;
7. svitare il dado dal connettore, lasciando la rondella in posizione. Inserire il connettore nel foro della lattina. Avvitare il dado sul connettore dall'interno del barattolo;
8. utilizzare le pinze o la chiave inglese per avvitare saldamente il dado sul connettore. <br>
	![[cantenna - 2.5.png]]

9. L'antenna appena costruita avrà questo aspetto: <br>
	![[cantenna - 2.6.png]]