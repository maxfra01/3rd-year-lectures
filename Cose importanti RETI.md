# Parte prima (Casetti)
---
- Per traffico uniforme e topologie regolari, il **throughput** è inversamente proporziale alla distanza media fra nodi.
- Un **protocollo** serve a far comunicare due entità DELLO STESSO LIVELLO.
- Una **connessione** avviene tra SAP di diversi sistemi ma sullo stesso livello.
- Nel CSMA/CD serve una dimensione minima della trama perchè se troppo piccola altre stazione trasmettono mentre questa è ancora sul mezzo.
- In Ethernet Classico (1-persistente CSMA/CD) se due stazioni sono nello stesso dominio di collisione allora il tempo minimo di trasmissione di un pacchetto non può essere inferiore al massimo RTT.
- Fast Ethernet ha un dominio di collisione 10 volte più piccolo rispetto a Ethernet normale (da 1000m a 100m)
- 


# Parte seconda (Marchetto)
---
- L'intestazione TCP è VARIABILE a seconda delle options.
- UDP ha un checksum per la correttezza dell'**intero payload** ma non ha meccanismi per richiederne la ritrasmissione.
- ARP serve per conoscere i MAC, a partire da IP
- Controllo di congestione, un timeout porta la **cwnd** a 1 MSS mentre il triplo ack dimezza la finestra (TCP RENO)
- In TCP TAHOE ogni evento posta la finestra a 1 MSS.

