# Definizioni 
---
Sono protocolli che compaiono in quasi tutte le reti telematiche, hanno lo scopo di:
- Recuperare gli errori di trasmissione
- controllo del flusso di trasmissione
- controllo di sequenza

I bit di parità fanno parte dell'intestazione della PDU, dunque nella PDI.
A seconda della quantità di bit di parità si può procedere in due modi:
- **FEC (Forward Error Connection)**: i molti bit di parità si usano per cercare di correggere gli errori, senza la ritrasmissione del pacchetto.
- **ARK(Automatic Repeat reQuest)**: i pochi bit di parità cercano di rilevare errori e chiedere la ritrasmissione.

Nel corso ci occuperemo di ARQ di cui esistono 3 tecnica differenti.
- Stop and wait
- Go back N
- Selective repeat

# Stop and wait
---
Passi del processo di Stop and wait:
- Il TX fa una copia della PDU da inviare (per una possibile ritrasmissione). 
- Inizializzazione del TX e del RX sui parametri del protocollo, ovvero abbiamo V(T)=0 e V(R)=0.
- Successivamente invia la PDU al RX e fa partire un orologio (timer) detto tempo di **timeout**. In questo lasso di tempo attende una risposta alla PDU che viene inviata (cioè attende l’ACK). Se il timeout scade prima dell’arrivo della conferma, ripete la trasmissione facendo ripartire il timeout.

Quando il RX riceve la PDU allora:
- RX controlla la correttezza della PDU
- Se è corretta allora fa il controllo in sequenza (ovvero se è proprio quella che si aspettava)
- Manda al TX l'ACK.
- La PDU è passata ai livelli superiori

![[Pasted image 20221012110144.png]]

Se arriva un pacchetto al ricevitore con il codice di parità sbagliato, **il ricevitore non fa nulla!** 

**Round trip time (RTT)**: intervallo temporale dall'invio del primo bit del pacchetto alla ricezione dell'ultimo bit del relativo ACK.
Come gestire la numerazione dei pacchetti?

### ALTERNATING BIT PROTOCOL 
Metodo per il quale si alterna la numerazione fra 0 e 1.

Nel caso di ricezione errata della PDU allora devo tenere conto che la regolazione del timeout è delicata, se troppo lunga perdo efficienza, se troppo corto (e magari l'ACK è un po' in ritardo) riinvio il pacchetto anche se era arrivato.

Nel caso di perdita dell'ACK di un pacchetto allora dopo un po' il TX prova a rinviare la PDU, ma il RX che ha già incrementato il numero di sequenza finirà per ricevere il pacchetto sbagliato.
A questo punto RX rinvia la conferma, che corrisponde al pacchetto che si aspetta.

Nel caso di canali non sequenziali si possono verificare eventi di perdita e/o duplicazione di PDU. Per ovviare a ciò dobbiamo aumentare i bit per numerazione e introdurre il concetto di **TTL (Time To Leave)**.

# Go Back N
---
