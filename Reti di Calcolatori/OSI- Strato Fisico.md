# Mezzi trasmissivi
---
Il mezzo fisico ottimale è caratterizzato da:
- Resistenza, capacità trasmissiva e impedenze basse
- Resistenza alla trazione
- Flessibilità
- Facilità dei collegaementi

## Doppino
Classimo mezzo della telefonia, composto da due fili di rame ritorti (per ridurre le interferenze elettromagnetiche).
Hanno costi ridotti e l'installazione è semplice

Il connettore del doppino è il RJ-45.

![[Pasted image 20221019134040.png]]

Esistono classificazione dei doppini in base alla schermatura:
- UTP-Unshielded Twisted Pair
- FTP-Foiled Twisted Pair
- STP-Shielded Twisted Pair
Inoltre distinguiamo i doppini in base alla categoria (**Cat.**)

## Cavo Coassiale
Mezzo fisico realizzato con un connettore centrale e una o più calze di schermo.
Grazie a quest'ultimo (principio della gabbia di Faraday) otteniamo molte meno interferenze.
Costi elevati e difficoltà di installazione.
Spesso usati in connessioni verso antenne radio.

![[Pasted image 20221019134515.png]]

## Fibra Ottica
Realizzato con un piccolo e flessibile filo di vetro costituito da due parti, **Core e cladding** con indici di rifrazione diversi.
Principio di funzionamento: un raggio luminoso che entra con un certo angolo di accettazione rimane confinato nel core (Legge di Snell).

![[Pasted image 20221019134735.png]]

| Vantaggi                             | Svantaggi                                              |
| ------------------------------------ | ------------------------------------------------------ |
| Immanità da disturbi elettromagntici | Adatte solo a collegamenti punto-punto                 |
| Alte velocità                        | Difficili le interconnesioni dei cavi e dei connettori |
| Bassa attenuazione                   | Raggio di curvatura del cavo fisico deve essere basso  |
| Dimensioni ridotte, costi contenuti  | Soffre di vibrazioni                                                       |

L'attenuazione e perdita di segnale al km è sicuramente il fattore più rilevante: per evitare il problema individuiamo tre "finestre" di lavoro centrate alle lunghezze d'onda di $0.8 \mu m$ , $1.3 \mu m$ , $1.55 \mu m$ .

![[Pasted image 20221019135603.png]]

## Canale Radio
Detto anche Etere, le informazioni si propagano mediante l'uso di antenne.
Se TX o RX sono in movimento si parla di *radiomobile*.
La qualità del segnale dipende dal rapporto tra potenza ricevuta e potenza trasmessa.
$$
\frac{P_{R}}{P_{T}}=G_{T}G_{R} \frac{\lambda^2}{(4\pi D)^2}
$$
(Eq. di Friis, propagazione nello spazio libero)
La potenza in ricezione è influenzata da:
- Fenomeni atmosferici
- Interferenze di altre sorgenti
- Osticali
In particolare la presenza di ostacoli determina **riflessioni e copie** del segnale trasmesso.
- **Fading**: variazione veloce del segnale dovuto alle altre copie ricevute
- **Shadowing**: variazione lenta dell'ampieza del segnale

![[Pasted image 20221019140408.png]]



# Trasmissione sul mezzo fisico
---
