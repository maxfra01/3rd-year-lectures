# Definizioni di base
---
Tralasciando le classificazione riportiamo le formule notevoli utili alla risoluzione degli esercizi.
- **Energia di un segnale analogico** $$
E(x)=\int_{-\infty}^\infty |x(t)|^2 \, dt 
$$
- **Potenza media di un segnale analogico** $$
P(x)=\lim_{ a \to \infty } \int _{-a}^a |x(t)|^2 \, dt  
$$
Notiamo immediatamente che per segnali a energia finita, la potenza media risulta essere nulla!
Viceversa per un segnale a potenza media finita possiamo dedurre che la sua energia è infinita!

- **Distanza euclidea fra segnali** $$
d(x,y)=\sqrt{ \int _{-\infty}^\infty |x(t)-y(t)|^2 \, dt  }
$$
- **Convoluzione fra segnali analogici** $$
z(t)=x(t)*y(t)=\int_{-\infty}^{\infty} x(\tau)y(t-\tau) \, d\tau 
$$

# Sistemi LTI
---
Intendiamoi sistemi in cui vale la **sovrapposizione degli effetti** e **un ritardo in ingresso si traduce in un ritardo sull'uscita**.

- **Risposta all'impulso** è l'uscita del sistema se all'ingresso è applicata una delta di Dirac $$
h(t)=\mathcal{L}[\delta(t)]
$$
- **Uscita di un LTI** calcolabile come convoluzione fra l'ingresso e la risposta all'impulso $$
y(t)=h(t) * x(t)
$$
- **Risposta in frequenza** $$
H(f)=\mathcal{F}[h(t)]
$$
- **Uscita di un LTI** calcolabile nel dominio della frequenza $$
Y(f)=H(f)\cdot X(f)
$$

| Ingresso                        | Uscita                          |
| ------------------------------- | ------------------------------- |
| esponenziale $e^{2j\pi f_{0}t}$ | $y(t)=H(f_{0})e^{2j\pi f_{0}t}$ |

- A un ingresso sinusoidale otteniamo un' altra sinusoide a stessa frequenza!
$$y(t)=|H(f_{0})|\sin(2\pi f_{0}t+ arg\{H(f_{0})\})$$

- **Causalità** è una proprietà di un LTI che non dipende da ingressi futuri; in altre parole si richiede che $$
h(t)=0\quad \forall t <0
$$
- **Stabilità, BIBO** $$
\int |h(t)| \, dt <\infty \implies |H(f)|<\infty 
$$
- Per **sistemi reali** abbiamo $h(t)$ reale e inoltre per $H(f)$ abbiamo parte reali pari, parte immaginaria dispari, modulo pari e fase dispari


- **Blocchi lineari in serie** $$
H_{eq}(f)=H_{1}H_{2}\dots
$$
- **Blocchi lineari in parallelo** $$
H_{eq}(f)=H_{1} +H_{2}+\dots
$$
- **Sistema NON distorcente** solo se l'uscita è formato dall'ingresso moltiplicato per una costante e ritardato, in quanto questi due non distorgono il segnale $$
y(t)=k \cdot x(t-t_{D})
$$
# Segnali periodici
---
- **Segnale periodico, definizione** $$
x(t)=x(t+T)\quad \forall t
$$
- **Segnale periodico, definizione con periodo troncato** $$
x(t)=\sum_{n=-\infty}^\infty x_{T}(t-nT)
$$
- **TdF di un segnale periodico** $$
X(f)=\frac{1}{T}\sum_{n=-\infty}^\infty X_{T}\left(  \frac{n}{T} \right) \cdot \delta\left( f- \frac{n}{T} \right)
$$
Si tratta dunque di uno spettro a righe interspaziate di $\frac{1}{T}$.


# Autocorrelazione, spettro potenza ed energia
---
- **Spettro di energia** $$
S_{x}(f)=|X(f)|^2
$$
Inoltre è legato all'energia perchè:
$$
E(x)=\int_{-\infty}^{\infty} S_{x}(f) \, df 
$$
- **Spettro in uscita da LTI** $$
S_{y}(f)=|H(f)|^2 \cdot S_{x}(f)
$$
- **Autcorrelazione di un segnale analogico**: $$
R_{x}(\tau)=\int_{-\infty}^{\infty} x(t+\tau)x^*(t) \, dt 
$$
Inoltre ricordiamo il legame fra spettro e autocorrelazione $$
S_{x}(f)=\mathcal{F}[R_{x}(\tau)]
$$
Per segnali reali, la autocorrelazione è pari, reale, con un massimo nell'origine pari all'energia del segnale.

- **Spettro di potenza** 


# Processi casuali
---
Per la caraterizzazione di insieme di un segnale, occorre descrivere due caratteristiche, media e autocorrelazione:$$
m_{x}=E\{X(t)\}=\int xf_{x}(x;t) \, dx 
$$
$$
R_{x}(t_{1},t_{2})=E\{X(t_{1})X^*(t_{2})\}=\int \int x_{1}x^*_{2}f_{x_{1}}f_{x_{2}} \, dx  \, dx 
$$
Definiamo i **WSS Processi stazionari in senso lato** come quelli per cui:
$$
m_{x}=m_{x}(t)  \quad \quad R_{x}(t_{1},t_{2})=R_{x}(t_{1}-t_{2})
$$
Ovvero quelli per cui la media non dipende dal tempo e l'autocorrelazione dipende solamente dalla differenza fra istanti temporali.

Per la funzione di correlazione abbiamo: $$
R_{x}(\tau)=E\{X(t)X^*(t+\tau)\}
$$
Per il caso reale abbiamo $R_{x}(\tau)=E\{X^2(t)\}$.

# Ergodicità
---
- Operatore di **Media temporale**:$$
\langle g[x(t)] \rangle=\lim_{ T \to \infty } \int_{-\frac{T}{2}}^{T/2}  g[x(t)]\, dt 
$$
- **Ergodicità** garantita per media di insieme e media terporale coincidente