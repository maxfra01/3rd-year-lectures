# Loop Shaping
---
Una volta determinata la parte statica del controllore, la parte dinamica $C'(s)$ viene costruita in modo che:
$$
\begin{cases}
\omega_{c} \approx \omega_{c,des} \\
m_{\phi} \geq m_{\phi,min}
\end{cases}
$$
Si parla proprio di **loop shaping** perchè $C(s)$ viene modellata in modo da rispettare le specifiche idonee.

Per la costruzione della funzione ad anello si parte dalla sua forma based:
$$
G_{a1}(s)=\frac{K_{c}}{s^h}F(s)
$$
Si procede valutando modulo e argomento di $G_{a1}(j\omega_{c,des})$ e calcolo in particolare la **variazione di fase necessaria per ottenere il margine di fase desiderato**, e la variazione **di modulo per portare la pulsazione di crossover a quella desiderata**.
$$
\Delta m_{dB}=-|G_{a1}(j\omega_{c,des})|_{dB}
$$
Solitamente per la fase si richiede di anticipare, mai di ritardare ($\Delta \phi\geq 0$)
Per ottenere l'anello completo tramite il loop shaping, si fa uso di **reti di compensazione**:
$$
G_{a}(s)=C'(s) \cdot G_{a1}(s)
$$
Ogni rete che introduciamo è tale da apportare una certa modifica in modulo o fase all'anello finale.
Questa fase di progetto è detta **sintesi per tentativi**, in quanto servono numerose correzioni successive e occorre verificare ogni volta ciò che si è ottenuto.


# Reti anticipatrici
---
Una rete **anticipatrice o derivativa** è descrita da una fdt in questa forma:
$$
R_{d}(s)=\frac{1+\tau_{d}(s)}{1+\frac{\tau_{d}}{m_{d}}s} \quad \tau_{d}>0, m_{d}>1
$$
La rete ha i seguenti diagrammi di Bode:

![[Pasted image 20230519111907.png]]

Posso usare questa rete per far salire la fase, compensando il margine desiderato. Come svantaggio però ci sarà un aumento del modulo.
Usaremo queste reti ogni volta che dobbiamo **anticipare fase**.

Se abbiamo bisogno di molto anticipo di fase, è consigliabile usare due reti con $m_{d}$ piccolo (in genere minore di 16) piuttosto che un'unica rete con $m_{d}$ grande.

Uso perfetto di queste reti: quando devo recuperare fase e devo aumento il valore di $\omega_{c}$ ovvero aumentare il modulo di $G_{a}(s)$