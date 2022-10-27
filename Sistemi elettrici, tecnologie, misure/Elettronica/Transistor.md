# Transistori MOS
---
Oltre a questa tipologia esiste anche il **BJT (Bipolar Junction Transistor)**.

### Concetti generali
Nella pratica un **Trans**fer Res**istor** è un doppio bipolo non lineare unidirezionale, in cui individuaimo una porta di controllo e una porta controllata.
Corrisponde alla minima unità funzionale in ogni sistema elettronico.

![[Pasted image 20221024094429.png]]

### pMOS vs nMOS

![[Pasted image 20221024094840.png]]

Distinguiamo sempre 4 terminali nei transistori MOS:
- SOURCE
- DRAIN
- GAIN
- BULK
Il terminale BULK è solitamente cortocircuitato al SOURCE oppure collegato a una tensione costante; in ogni caso nel corso consideriamo il cortocircuito e quindi ci limitiamo a 3 terminali.

### Caratteristiche statiche
Possiamo individurare due porte, **Source-gate** e **Drain-Source**.
La gain-source (GS) è la porta di ingresso ed $v_{gs}$ è detta variabile indipendente.
Quella dipendente è la corrente che scorre nella porta di uscita $i_{d}$.

Per la porta di ingresso abbiamo la seguente caratteristica:
$$
i_{G}=i_{G}(v_{GS},v_{DS})=0 \quad \forall v_{GS}, \forall v_{DS}
$$
Da cui deduciamo che la potenza assorbita per la porta in ingresso è sempre nulla.
$$
P_{in}=v_{GS} \cdot i_{G}=0
$$
### Caratteristiche d'uscita
Sappiamo che l'uscita è dipendendente dalla variabile di ingresso $v_{GS}$

Fintanto che la tensione $v_{GS}$ non supera una certa soglia, il transistore mos si comporta come un circuito aperto e non dissipa potenza.
L'area in cui si verifica questo fenomeno è detta **Regione di interdizione**.

Mentre quando è rispettata la relazione $v_{GS} > v_{TH}$ AND $v_{DS}<v_{GS} - v_{TH}$
Allora posso dire che mi trovo nella **Regione di triodo** e la relazione all'uscita del transistore è:
$$
i_{d}=\beta \cdot v_{ds} \cdot\left( v_{gs}-v_{th}-\frac{v_{ds}}{2} \right)
$$
![[Pasted image 20221025090157.png]]

Notiamo che se $v_{gs}-v_{th} \gg v_{ds}$ allora la relazione è quasi lineare e si comporta come un resistore:
$$
R_{ON}=\frac{1}{\beta(v_{gs}-v_{th})}
$$
L'ultima regione del grafico è detta **Regione di saturazione**:
$$
I_{d}=\frac{\beta}{2} (v_{gs}-v_{th})^2(1+\lambda v_{ds})
$$
![[Pasted image 20221025090651.png]]

### Safe Operating Area (SOA)
Un transistor può andare incontro a un danneggiamento se le tensioni nelle porte eccedono un certo valore, oppure se la corrente che scorre supera un certo valore, o ancora se la potenza dissipata (significativa in saturazione) supera una soglia.

Definiamo allora la SOA, che è una piccola area del grafico analizzato di sopra.

![[Pasted image 20221025092535.png]]

### Transcaratteristica statica
Rappresentiamo la transcaratteristica fra $v_{gs}$ e $i_{D}$

![[Pasted image 20221025093119.png]]

Versione del pMOS su slide.


# Transistor in applicazioni analogiche
---
Considero il circuito in figura

![[Pasted image 20221026133349.png]]

Esso è composto da un transistore nMOS, una resistenza R, un tensione di alimentazione $V_{DD}$ e collegati al terminale di drain due **generatori di polarizzazione** di tensione, il primo genera tensione, il secondo il segnale.
All'ingresso della porta di gate risulta:
$$
v_{GS}=v_{in}+V_{GS}
$$
Mentre all'uscita, applicando la legge di Kirchoff sulla maglia di uscita:
$$
v_{DS}=V_{DD}-R \cdot i_{D}
$$

Se mi trovo nella regione di saturazione, la corrente di drain non è costante ma è data da $i_{D}=\frac{1}{2}\beta (v_{GS}-V_{TH})^2$ 
Perciò andiamo a esaminare la transcaratteristica del transistore (supponiamo che $v_{in}$ sia un segnale sinusoidale).

![[Pasted image 20221026134415.png]]

A sinistra notiamo il valore costante di $V_{GS}$ che si può scostare in base al segnale sinusoidale e ricaviamo il valore della corrente del drain.
Perciò idealmente la corrente di drain dipende solamente dalla tensione in ingresso al gate.
Per vedere quanto vale la $v_{DS}$ costruisco il grafico con la relazione di uscita, a destra.

>Il punto $Q$ in cui è centrato il segnale sinusoidale è detto **punto di quiescenza** o **punto di lavoro**, e si può determinare applicando al circuito solamente la tensione di indice ($V_{GS}$). In tal modo troviamo solamente un punto sul grafico.

>I termini di tensione scritti in maiuscolo e minuscolo sono quelli completi.
>Quelli solo maiuscoli indicano la componente continua.
>Quelli solo minuscoli indicano il segnale.

Avendo una dipendenza quadratica fra la corrente e la tensione in ingresso, produciamo anche la seconda armonica e quindi del rumore.
Per ovviare a ciò introduciamo il concetto della **Linearizzazione** che cerca di sostituire alla relazione quadratica la tangente in un intorno del punto di lavoro.
Ovviamente più il segnale oscillante ha un'ampiezza minore, più l'intorno è piccolo e quindi meglio l'approssimazione funziona.

# Analisi di piccolo segnale
---
L'approccio con metodo di Taylor è applicabile su ogni elemento circuitale che presenza caratteristiche non lineari.
Consideriamo un elemnto non lineare con entrata:
$$
x_{IN}(t)=X_{IN}+x_{in}(t)
$$
E uscita:
$$
y_{OUT}(t)=Y_{OUT}+ y_{out}(t)
$$
Allora ne posso eseguire lo sviluppo di Taylor centrato in $X_{IN}$ troncato al primo oridne:
$$
y_{OUT}(t)=f(X_{IN})+\frac{ \partial f }{ \partial x }|_{x=X_{IN}}\quad x_{in}(t) +o(|x_{in}|) = Y_{OUT}+y_{out}(t)
$$
Quindi il primo termine corrisponde al punto di lavoro/quiescenza, mentre la seconda parte diventa un sistema linearizzato (grazie alla derivata).
Facendo ciò abbiamo spezzato il sistema non lineare in due parti, uno non lineare statico e uno lineare per studiare le variazioni.

![[Pasted image 20221026141719.png]]

