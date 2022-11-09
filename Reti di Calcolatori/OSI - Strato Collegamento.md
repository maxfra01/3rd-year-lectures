# Reti private/locali/LAN
---
All'interno di questo modello, lo strato OSI del collegamento è divisio in due sottolivelli:
- **LLC Logical Link Control**
- **MAC Medium Access Control**

Il Logical Link Controlo LLC è anche il nome del protocollo che regola l'omonimo strato.
E' anche detto standard IEEE 802.2 ed ha le seguenti caratteristiche:
- orientato al byte
- non si controllano gli errori

Il suo compito è quello di fornire informazioni allo strato superiore, tramite appositi campi (si noti la dimensione variabile per il campo informazioni).

![[Pasted image 20221028160115.png]]

Ma a questa struttura dsi cerca di aggiungere un campo supplementare necessario per lo strato superiore (3).

![[Pasted image 20221028160431.png]]

Si aggiunge perciò quella che viene denominata **SNAP PDU**.

Per le funzionalità del sottostrato MAC vedere il prossimo capitolo [[Protocolli di accesso per reti locali]].