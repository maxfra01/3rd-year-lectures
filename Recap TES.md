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
| sinusoide                       | sinusoide alla stessa frequenza ma diversa fase e ampiezza                                |

- **Causalità** è una proprietà di un LTI che non dipende da ingressi futuri; in altre parole si richiede che $$
h(t)=0\quad \forall t <0
$$
- **Stabilità, BIBO** $$
\int |h(t)| \, dt <\infty \implies |H(f)|<\infty 
$$
- **Blocchi lineari in serie** $$
H_{eq}(f)=H_{1}H_{2}\dots
$$
- **Blocchi lineari in parallelo** $$
H_{eq}(f)=h_{1} +H_{2}+\dots
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


#