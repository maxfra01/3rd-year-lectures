# Classificazione dei sistemi
Per questo capitolo occorre ricordare le proprietà della trasformata di fourier [[Serie e trasformata di Fourier]].

Un **Sistema** è un elemento che dato un segnale in ingresso lo trasforma in un segnale differente tramite una **trasformazione**.
$$
\mathcal{T}:x_{1}(t) \implies y_{1}(t)
$$
Segue la classificazione dei sistemi.

### Sistemi Lineari
Sistemi per cui vale la proprietà di **sovrapposizione degli effetti**
$$
\mathcal{T}[ax_{1} +bx_{2}]=a \mathcal{T}[x_{1}]+b\mathcal{T}[x_{2}]
$$
![[Pasted image 20221013120810.png]]

### Sistemi Tempo Invarianti
Sistema in cui un ritardo sugli ingressi si traduce in un ritardo sulle uscite.
$$
\mathcal{T}[x(t)]=y(t) \leftrightarrow \mathcal{T}[x(t-\theta)]=y(t-\theta)
$$
![[Pasted image 20221013121025.png]]

Nella maggior parte del corso tratteremo **LTI (Linear and Time Invariant)**.

### Sistemi senza memoria
Sistemi in cui l'uscita dipende solo dal valore in ingresso in quel momento.
(parallelismo con sistemi combinatori (vedi Calcolatori elettronici)).

Se un sistema è senza memoria e tempo invariante allora si può descrivere il sistema con una **relazione ingresso-uscita**.



# Sistemi LTI
---
### Risposta all'impulso
In questi sistemi assume particolare importanza la **risposta all'impulso**: ovvero quando osservo l'uscita del sistema quando applico una **delta di Dirac**.
$$
h(t)=\mathcal{L}(\delta(t))
$$
![[Pasted image 20221013121508.png]]

Si dimostra che grazie alla risposta all'impulso (indicata con $h(t)$) è possibile calcolare la risposta di ogni ingresso per un sistema LTI.
$$
y(t)=x(t)*h(t)=\int x(u)h(t-u) \, du 
$$
Tramite un integrale di convoluzione fra l'ingresso e la risposta all'impulso.
Vale anche traslare l'ingresso e non la risposta all'impulso: $\int h(u)x(t-u) \, du$
Useremo Fourier per non calcolare mai integrali di convoluzione.

### Funzione di trasferimento
Si dice **Funzione di Trasferimento** la trasformata di Fourier della risposta all'impulso:
$$
H(f)=\mathcal{F}[\mathcal{L}(\delta(t))]
$$
Spesso è anche detta **risposta in frequenza** di un sistema lineare.
Da ciò si possono dimostrare le seguenti relazioni:
$$
Y(f)=H(f)X(f) \quad \quad \quad H(f)=\frac{Y(f)}{X(f)}
$$
Dunque possiamo caratterizzare un LTI tramite **la risposta all'impulso** oppure **la funzione di trasferimento**.

### Ingressi in LTI di tipo esponenziale complesso

