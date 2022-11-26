# DNS
---
**Domain Name System** è uno dei protocolli/sistemi che troviamo nell'application layer, ma di supporto al protocollo IP.

Permette di mappare un "nome" o "dominio" con un corrispondente indirizzo IP, e per fare ciò necessitiamo di un sistema di **Database distribuito** organizzato tramite **gerarchia di name server**.
La struttura centralizzata non è consigliata per tolleranza ai guasti, dimensioni eccessive, distanza fisica del server e manutenzione.
Come per altri protocolli l'obiettivo è di confinare la **complessità al bordo** della rete, lasciando al singolo utente un metodo semplice da gestire.

![[Pasted image 20221116114445.png]]

Sotto i **root DNS servers** abbiamo quelli che vengono definiti i **Top Level Domain**, tipo com, net, org, edu, mentre sotto i TLD abbiamo i server **autoritativi**.

| TDL                                                                 | Autoritativo                                         | Root                                               |
| ------------------------------------------------------------------- | ---------------------------------------------------- | -------------------------------------------------- |
| Sono i domini come com, net, org, ecc...                            | Server DNS proprietari dell'azienda                  | Sono circa una ventina di server in tutto il mondo |
| Non contengono il mapping ma i puntatori ai DNS server autoritativi | Fornisce le informazioni relative al mapping nome-IP | Corrispondono al punto di ingresso alla gerarchia dei name server                                                   |

```ad-info
Mantenere aggiornati i root server DNS è semplice in quanto le informazioni che posseggono sono molto statiche, ad esempio il server che gestisce il TDL .com non cambia mai!
```

Esiste anche il **Local DNS server**, fuori dalla gerarchia, che è responsabile di mantenere una **Cache** per usi futuri di quel mapping.
Ne esiste uno integrato nei router oppure gestiti da un ISP.

## Risoluzione DNS

| Iterativa | Ricorsiva |
| --------- | --------- |
|    ![[Pasted image 20221116120914.png]]       | ![[Pasted image 20221116121159.png]]          |

 
I record di un local DNS server hanno un formato detto **RR, Resource Record**:

| name | value | type | TTL | 
| ---- | ----- | ---- | --- |

Il campo type specifica la relazione fra `name` e `value`

| Type  | Significato                                                                         |
| ----- | ----------------------------------------------------------------------------------- |
| A     | Il name è l'hostname, mentre il value è un IP address                               |
| NS    | Name è il dominio, mentre value è l'hostname del corrispondente server autoritativo |
| CNAME | Name è un alias per un canonico dominio (east.backup2.ibm.com sta per ibm.com)      |
| MX    | Value è il nome di un mailserver associato a name                                                                                    |

Il formato dei pacchetti DNS è la stessa sia per la **query** che per la **response**.

![[Pasted image 20221116123735.png]]

