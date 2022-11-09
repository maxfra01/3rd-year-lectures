# Indirizzo MAC
---
E' un identificativo che permette di individuare un determinato dispositivo (scheda di rete) tra i nodi della rete locale [[Protocolli di accesso per reti locali]]
Sono lunghi tipicamente 6 byte, e ad oggi sono configurabili via software altrimente sono decisi dal costruttore della scheda.

I 3 byte più significati sono l'**Organization Unique ID**, e identificano la marca del costruttore, mentre i 3 byte meno significativi sono progressivi 

![[Pasted image 20221102121203.png]]

Gli indirizza MAC sono **Unicast, multicast o broadcasta**, a seconda se siano riferiti a una, più o tutte le stazione nella rete.

Le modalità di multicasting sono:
- Solicitation
- Advertising


# Ethernet
---
Standard di cablaggio principale per reti MAN e LAN, con le seguenti caratteristiche:
- un formato della trama ben definito
- commutazione di pacchetto a livello collegamento
- CSMA/CD

IEEE definisce a partire da ethernet lo **standard 802.3**
Esaminiamo ora i formati del pacchetto dei due standard:

| Ethernet                             | IEEE 802.3                           |
| ------------------------------------ | ------------------------------------ |
| ![[Pasted image 20221102175343.png]] | ![[Pasted image 20221102175414.png]] |

Il campo **Preambolo** di lunghezza di 7 byte permette la sincronizzazione del clock del RX e del TX.
Il **SFD Start of Frame Delimiter**, da 1 byte, determina la fine della sincronizzazione, la sequenza alternata di 1 e 0 viene interrotta da un doppio.
La prima differenza fra le 2 è la presenza del campo per il **tipo di protocollo livello superiore** in uno e la **lunghezza del campo dati**.
Il campo **Padding** serve solo a raggiungere la dimensione minima di 46 byte.
La **Frame Check Sequence FCS**, 4 byte, occorre per il controllo degli errori e infine il **Silenzio infrapacchetto** di 12 byte.

## Ethernet classico
Utilizza il protocollo CSMA/CD 1-persistente.
Se durante la trasmissione si rileva una collisione si interrompe la trasmissione e si invia una **sequenza di jamming**.
Il tempo per ritentare la trasmissione non può essere inferiore al RTT.

Il protocollo è semplice e distribuito, ha buone prestazione se la rete non è sovraccarica.

Non c'è ACK.

Relativamente economico, non gestisce priorità.

A livello fisico si usano cavi di diverse categorie e si usa la codifica di Manchester.

## Ethernet ad oggi
Ad oggi si utilizzano cavi in fibra ottica e topologie a centro stella ATTIVO.
Le comunicazioni avvengono in pratica solo in modalità full-duplex.


# Commutatori a livello collegamento
---
Per passare da una topologia a bus a uno a stella gerarchica occorre un centro stella, che si concretizza in due dispositivi:
- hub
- switch

### Hub
Apparato multiporta per l'interconnessione di LAN che opera a livello 1 [[OSI - Strato Fisico]].

Il suo modello è quello del centro stella passivo, il suo compito è rigenerare su tutte le uscite la codifica di linea sulla porta in entrata.

Non fanno altro, non riconoscono le trame e non separano i domani di collisione.

![[Pasted image 20221107142516.png]]


### Switch
Apparato multiporta per l'interconnesione di LAN che opera al livello OSI 2 [[OSI - Strato Collegamento]].

E' di fatto un nodo store & forward in grado di riconoscere (non modificare) le trame dei pacchetti.
E' possibile che delle trame si perdano per overflow della memoria interna.

Il modello è un centro stella attivo e instradano le trame in base al protocollo MAC, il tutto in modo trasparente all'utente e prestazioni elevate.

![[Pasted image 20221107142853.png]]

Ogni porta dello switch corrisponde a un dominio di collisione a se stante e lo switch è in grado di **eliminare le collisioni**, di fatto eliminando la necessità del CSMA/CD.

# Instradamento
---
Se connettiamo tramite switch segmenti di LAN otteniamo ancora una LAN.
Vogliamo che i comportamenti dei vari dispositivi non cambino (trasparenza) perciò la complessità dell'instradamento sarà nello switch.
- Address learning
- Frame forwarding
- spanning tree

## Address learning
Lo switch memorizza entry di una tabella contenente per ogni porta dello switch gli indirizzi MAC dei dispostivi raggiungibili.

Ogni volta che lo switch riceva la trama legge il MAC sorgente e lo memorizza nella tabella insieme alla porta.
Algoritmo di **backward learning**

## Frame Forwarding
Quando ricevo una trama cerco a quale porta è associato il MAC destinazione:
- Se è associato alla porta da cui è arrivata la trama, allora si scarta (non doveva arrivare lì)
- Altrimenti inoltro su porta corretta.
In Multicast inoltro su tutte le porte tranne quella di ingresso.

