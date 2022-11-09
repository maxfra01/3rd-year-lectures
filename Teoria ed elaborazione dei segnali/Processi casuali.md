# Introduzione
---
Fin'ora (da [[Grandezze di interesse sui segnali]] a [[Auto Correlazione]]) ci siamo concentrati su segnali **determinati**, ovvero che il loro andamento nel tempo è descritto da una precisa funzione matematica.
Ora vogliamo estendere i concetti per segnali con evoluzione aleatoria nel tempo e per farlo ci serviamo dei **Processi Casuali**.

L'idea è di raccogliere tante **realizzazioni** del segnale e descriverle con dei parametri basati sulla probabilità.

Un esempio di processo casuale è la tensione ai capi di un resistore non alimentato...

![[Pasted image 20221104164148.png]]

# Definizioni
---
Un **Processo casuale** è un modello probabilistico per un insieme di segnali.
Si associa per ogni realizzazione del segnale una probabilità.
Dunque un processo casuale si può pensare come un **insieme di funzioni caratterizzate statisticamente.**

Ad ogni istante di tempo $t_{0}$ ottengo una variabile casuale:
$$
x(t_{0},s_{1}) \quad x(t_{0},s_{2}) \quad x(t_{0},s_{3}) 
$$
corrispondente alle diverse realizzazioni del processo.

Possiamo dunque pensare a un processo casuale come **una sequenza di variabili aleatorie scandite dagli istanti temporali.**

La classificazione dei processi casuali aggiunge due particolari categorie alla già precedente classificazione per i segnali determinati:
- **Processo quasi determinato**, il segnale è esprimibile come un segnale determinato dipendente da una serie di variabili casuali 
- **Processo non quasi determinato**, quando il segnale non può essere espresso come qui sopra

Consideriamo un processo quasi determinato, allora lo definiamo come:
$$
x(t)=A \cos(2\pi f_{0}t +\phi)
$$
Dove $A$, $f_{0}$, e $\phi$ sono variabili casuali.
Al variare di queste 3 variabili si otteranno diverse realizzazioni del segnale.

Possiamo anche considerare dunque un segnale **determinato** come un un non determinato degenere con unica realizzazione con probabilità uguale a 1.


# Descrizione probabilistica
---
Avendo a disposizione un insieme $n$ di realizzazione possiamo definire le probablità congiunte di ogni possibile sottoinsieme.

E' possibile dunque caratterizzare completamente un processo casuale solo se possiamo definire ogni quantità statistica per ogni insieme di realizzazioni.

![[Pasted image 20221105112954.png]]

Per caratterizzare dunque ci si limita a una caratterizzazione statistica del primo ordine:
$$
f_{X}(x;t)
$$
In pratica definiamo la densità di probabilità del processo osservata su ogni possibile realizzazione.

### Media di un processo casuale
La possiamo definire come:
$$
m_{x}(t)=E\{X(t)\}=\int xf_{X}(x;t) \, dx 
$$
e rappresenta dunque un segnale determinato!

### Autocorrelazione di un processo casuale
Definita come:
$$
R_{x}(t_{1},t_{2})=E\{X(t_{1})X^*(t_{2})\}=\int \int x_{1}x^*_{2}f_{X_{1},X_{2}}(x_{1},x_{2};t_{1},t_{2}) \, dx_{1}  \, dx_{2} 
$$
Media e correlazione insieme definiscono la **caratterizzazione di insieme del processo**.
