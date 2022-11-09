# Instradamento
---
Una delle funzione dello [[OSI - Strato Rete]] è il routing dei pacchetti (per ogni PDU).
L'instradamento è effettuato leggendo informazioni da tabelle che contengono il **next-hop** cioè prossimo router.

- **Protocollo di instradamento**: definizione delle modalità di scambio di informazioni sullo stato della rete al fine di costruire tabelle di instradamento.
- **Algoritmi di instradamento**: operazioni necessarie per scegliere il percorso verso la destinazione
- **Forwarding**: operazioni per instradare i pacchetti sulla porta di uscita giusta.

Il costo degli algoritmi di instradamento dipendono da distanze, ritardo, euro, livello di congestione e dipendono dal variabile stato della rete.

I complesso algoritmi si dividono in due categorie:
- **centralizzati**, dove un nodo si occupa di raccogliere informazioni su tutti gli altri, calcola i percorsi e restituisce il risultato (troppo scomodo e complesso, vulnerabile ai guasti)
- **distribuiti**, dove la complessità è distribuita su tutta la rete, ovviamente si richiede che i nodi siano intelligenti e abbiamo più resistenza ai guasti.

Gli algoritmi **distribuiti** si dividono a loro volta in globali e parziali:
- nel primo caso ogni nodo conosce tutta la topologia, troppo complesso
- nel secondo ogni nodo conosce solo quelli adiacenti e c'è uno scambio di info solo tra questi ultimi.

Esempi di algortimi: Dijkstra, Distance vector


