# Caratteristiche di una LAN
---
Local Area Network hanno una piccola estensione geografica,e hanno la principale caratteristica di avere un **traffico impulsivo**, ovvero che non trasmettono sempre ma quando lo fanno desideriamo alta velocità.

Utilizza un mezzo radio condiviso, dunque trasmette un solo nodo alla volta, altrimenti spreco banda.

Topologie utilizzate: bus (vecchia), stella (oggi)

Il problema che sorge da ciò è quello dell'accesso multiplo al canale.
- Multiplazione: problema concentrato, tutti i flussi convergono in un punto (tipo switch)
- Accesso multiplo: flussi in punti diversi della rete
Quindi come affrontare il problema?

Esistono 3 principali famiglie di protocolli per la gestione di una rete locale:
- **Accesso casuale o contesa**, come Ethernet e WiFi
- Accesso ordinato, ad esempio Token Ring e FDDI
- a slot con prenotazione, es DQDB


# Protocolli ad accesso casuale
---
Quando un nodo trasmetto lo fa **alla massima velocità** e senza coordinarsi con nessuno!
Se due o più nodi trasmettono contemporaneamte si ha una **Collisione**.
Successivamente analisi della collisione:
- come evitarla
- come riconoscerla
- gestirla, ovvero ritrasmettere

## Aloha
Primo esempio di protocollo ad accesso casuale
Ogni antenna trasmette al master e il master manda a tutte in broadcast.
La vera destinataria del pacchetto lo riceve, e l'antenna che ha trasmesso per prima, riceve il proprio pacchetto e lo usa da ACK.
Semplice, non richiede sincronizzazione, ma la probabilità di collisione è alta.
Utilizza una strategia i stop&wiat (dopo timeout scade e ritrasmette).

![[Pasted image 20221028164925.png]]

Problema: se ritrasmetto dopo un tempo casuale e si è verificata una collisione continuerà a verificarsi la stessa collisione.
Per risolvere uso la tecnica deel **BACKOFF** ovvero ritrasmettere dopo un tempo casuale, e in caso di ulteriore collisione si raddoppia il massimo tempo di attesa casuale (backoff esponenziale).


## Slotted Aloha
Versione di Aloha ma con tempo diviso in slot (egual dimensione).
I nodi trasmettono all'inizio di ogni slot (le trame hanno durata equivalente allo slot).
Se ho una collisione ritrasmetto in un altro slot con probabilità p fino al successo.

![[Pasted image 20221028165455.png]]

Tuttavia questi protocolli sono instabili e limitati per valori bassi, serve qualcosa di più efficiente.

![[Pasted image 20221028165625.png]]


## CSMA Carrier Sense Multiple Access
Variante moderna dell'aloha in cui prima di trasmettere si ascolta il canale (carrier sense) per vedere una portante. Se è dunque **occupato** ho alcuni comportamenti possibili:
- CSMA 1-persistente: ascolto sempre e aspetto che si liberi il canale, poi trasmetto subito
- CSMA non persistente: riprovo a sentire il canale dopo un tempo casuale, e vedrò se trasmettere

Nonostante ciò le collisioni sono inevitabili e sono dovute ai ritardi di propagazione. C'è dunque uno spreco di tempo per la trasmissione della trama.
- la distanza fisica è determinante per le collisioni, se due stazioni sono più lontane e trasmettono c'è più possibilità di collisioni.
- a parità di traffico, trame lunghe nel tempo diminusicono la probabilità di collisione.


Ne esitono due varianti di CSMA:
- CSMA/CD **Collisione Detection** adatti a mezzi cablati
- CSMA/CA **Collision Avoidance**, adatti a mezzi radio

## CSMA/CD
In sostanza mentre trasmetto ascolto il canale, se sento solo la propria trasmissione allora proseguo.
Altrimenti se sente altri segnali smette immediatamente.
In caso di successo nel primo caso per tutta la trasmissione allora non è nemmeno necessario un ACK purchè valga:
- la durata minima della trama sia superiore al doppio del tempo massimo di propagazione nella rete

**Dominio di collisione**: Porzione di rete in cui, se due stazioni CSMA trasmettono simultaneamente, le trame collidono.

![[Pasted image 20221028180219.png]]

Vantaggi su CSMA classico:
- Se mi accorgo della collisione e interrompo non spreco risorse e tempo
- Facile da implementare su reti cablate, confronto potenza segnale inviato e ricevuto
- Non possibili in wireless perchè canale half duplex (quando trasmetto non posso ascoltare contemporaneamente).

Prestazioni del CD migliori:
- su reti piccoli (la distanza influenza)
- se $a=\frac{t_{P}}{T_{TX}}$ è piccolo
- quando la velocità di trasmissione è bassa, almeno spreco pochi bit se mi accorgo della collisione
- qunado uso 1-persistente
- in reti ethernet

## CSMA/CA
Non potendo ascoltare mentre si trasmette si usa un approccio conservativo.
Le stazioni usano CSMA non persistente, e il ricevitore deve inviare un ACK. 

Il trasmettitore se nota il canale libero libero per un tempo DIFS, allora trasmette.
Se è occupato (o diventa occupato durante DIFS) allora rimanda la trasmissione per il tempo di backoff.
Quando il canale è libero la stazione decrementa il backoff, qunado torna a 0 la trasmissione riparte.

In ricezione si verifica la correttezza della trama, se lo è si manda l'ACK dopo un tempo SIFS.
Se dopo un countdown il trasmettitore non riceve l'ack fa partire il backoff

In caso di inizio trasmissione simultaneo si possono comunque avere collisioni.

![[Pasted image 20221028183543.png]]

Si hanno ottime prestazioni nelle reti piccole

E' il protocollo usato nella reti WiFi 802.11

