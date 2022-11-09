# Collegamento con cavo coassiale
---
Data la struttura del cavo coassiale (conduttore, dielettrico, conduttore) di fatto è come inserire un **condensatore** in parallelo che collega il circuito al DSO.

![[Pasted image 20221005124431.png]]

Valori tipici: $R_{IN}=1M\ohm$ e $R_{g}=50\ohm$
Quando collego e c'è una corrente che scorre ottengo di fatto un filtro passa-basso con la sua relativa frequenza di taglio (ricordando che per un filtro passivo si ha $f_{t}=\frac{1}{2\pi\tau}$):
$$
f_{t} \approx\frac{1}{2\pi \cdot R_{g} \cdot(C_{d}+C_{IN})}
$$
Ho rilevato effetti di carico che dipendono sia dal circuito in misura che dal DSO ma anche dal cavo stesso.

I cavi che useremo saranno del tipo **RG-58** caratterizzati da una resistenza di $50\ohm$
e capacità $100 \frac{pF}{m}$

# Collegamento con sonda compensata
---
Il problema del cavo coassiale è che si ha già attenuazione del segnale prima di arrivare all'oscilloscopio (collo di bottiglia), per ovviare a ciò cerchiamo di 'compensare' questa perdita tramite una sonda.

![[Pasted image 20221005124954.png]]

La sonda compensata si basa sul principio del **partitore compensato**.
Una relazione da verificare è quella dell'uguaglianza delle costante $\tau$ di tempo:
$$
R_{s} \cdot C_{s}=R_{IN} \cdot(C_{IN} +C_{d})
$$

Allora se quest'ultima è vera possiamo ottenere una sonda solamente 'resistiva' definita dalla relazione:
$$
\frac{V_{IN}}{V_{G}}=\frac{R_{IN}}{R_{IN}+ R_{S}}
$$
Come per il caso del cavo coassiale, il collegamento va a definire un filtro passa basso con frequenza di taglio pari a:
$$
f_{t}=\frac{1}{2  \pi R_{g} C_{eq}}
$$
Per regolare $C_{eq}$ occorre ricorrere all'onda quadra, modifichiamone il valore con una manopola fino a quando l'onda quadra appare senza distorsioni sullo schermo: a quel punt significa che la sonda sta compensando.

Un comando importante nel menu del canale è il comando **Probe**, con una serie di scelte annesse. Occorre selezionare la voce corretta in funzione del collegamento che si va a fare:
- scegliamo **x1** se usiamo un cavo coassiale
- nel caso di sonda compensata scegliamo **x10** (sonda x10)

Come mai preferiamo modulare la capacità della sonda, rispetto alla resistenza?
- si preferisce modifica la capacità perchè dalla resistenza dipende la compensazione
- La resistenza si usa per verificare il fattore 1:10 della somma.


# Scala di misura
---
Lo schermo dell'oscilloscopio è un rettanggolo da 10 divisioni in orizzontale e 8 in verticale.
Non è quadrato per movtivi storici: a causa dello spostamento del pennello.

![[Pasted image 20221005132403.png]]

Due possibilità per effettuare misure dall'oscilloscopio:
- Il menu **measures** selezionabile con pulsanti sul DSO, può selezionare parametri da misurare automaticamente; il problema è l'assenza delle incertezze associate
- Per misure a cui interessa l'incertezza usiamo la scala (ogni tacca 0.2 divisioni)

Esempio, misurazione della tensione picco-picco:

![[Pasted image 20221005132838.png]]

$y_{2}=3.6 div$     $y_{1}=-3.4div$  ottengo ($K_{v}=0.5$) $V_{pp}=3.5V$
Ora devo applicare la legge di propagazione
$V_{pp}=L_{pp}K_{v}=(y_{2}-y_{1})K_{v}$
$\delta V_{pp}=\frac{ \partial V_{pp} }{ \partial y_{2} }\delta y_{2}\dots$
Ottengo
$\delta V_{pp}=K_{v}(\delta y_{1}+\delta y_{2})+\delta K_{v}(y_{2}-y_{1})$
Risultato analogo se uso i casi notevoli e qualche passaggio algebrico.
Le incertezze sulle letture di $y_{1}$ $y_{2}$ $K_{v}$ è basato sulla risoluzione dell'oscilloscopio.
In condizioni normali (senza rumore o altro) è l'operatore se decide in quale metà della divisione va il segnale, dunque di norma teniamo la risoluzione di lettura sul display pari a 0.1.

Possimao dunque considerare l'**incertezza in lettura pari alla metà della risoluzione**.
Per l'incertezza sul fattore di taratura verticale, è il costruttore che la fornisce (nella forma ridotta)
$$
\epsilon_{K_{v}}=\frac{2}{100}Full Scale
$$
Faccio i calcoli inversi con la definizione dell'incertezza ridotta.

Altro esempio: misurazione della base tempi

![[Pasted image 20221005134454.png]]

Ragionamenti analoghi a prima

Altra esempio: misurazione di rapporti di tensione(intervalli di tempo)

![[Pasted image 20221005134538.png]]

Nell'esempio cerco il rapporto $\frac{x_{1}-x_{2}}{x_{2}-x_{3}}$ ovvero il **duty cicle**.
Come calcolarne l'incertezza?
Assumiamo come nel caso precedente che le incertezza siano uguali e pari a 0.05.
Non posso ricorrere ai casi notevoli, ovvero non posso sommare le incertezze, perchè il numeratore e denominatore dipendono da una stessa variabile, dunque non sono indipendenti.
Uso la regola delle derivate parziali.

[[Incertezze, modello deterministico]]