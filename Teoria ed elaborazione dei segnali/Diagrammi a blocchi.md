# Combinazioni di sistemi LTI
---
E' possibile combinari sistemi LTI insieme per ottenere ancora un [[Sistemi lineari]] in cui la funzione di trasferimento si ricava con semplici operazioni.
Sono descritti tramite **diagrammi a blocchi**.

### Parallelo di LTI

![[Pasted image 20221021120506.png]]

$$
Y(f)=H_{1}(f)X(f) + H_{2}(f)X(f)=X(f)(H_{1}(f)+H_{2}(f))
$$
Dunque nel caso di parallelo otteniamo che la funzione di trasferimento del sistema è la somma delle funzioni di tasferimento dei sottosistemi.
$$
H_{tot}(f)=H_{1}(f)+H_{2}(f)
$$

### Serie di LTI

![[Pasted image 20221021120729.png]]

$$
Y(f)=(H_{1}(f)X(f))H_{2}(f)=X(f)[H_{1}(f)H_{2}(f)]
$$
Dunque nel caso di serie abbiamo che la funzione di trasferimento è il prodotto delle funzioni di trasferimento dei sotto-sistemi.
$$
H_{tot}(f)=H_{1}(f) \cdot H_{2}(f)
$$
### Retroazione

![[Pasted image 20221021121102.png]]

...calcoli....


# Amplificatori e ritardatori
---
Consideriamo la risposta all'impulso e la funzione di trasferimento dei due sistemi:

| Ritardatore          | Amplificatore            |
| -------------------- | ------------------------ |
| $h(t)=\delta(t-T)$   | $h(t)=A \cdot \delta(t)$ |
| $H(f)=e^{-2j\pi fT}$ | $H(f)=A$                         |

Nel caso del ritardatore avremo un output del tipo $x(t) \implies x(t-T)$

Nel caso dell'amplificatore $x(t) \implies A \cdot x(t)$

### Reti di amplificatori e ritardatori
Combinando opportunamente questi due elementi possiamo ottenere le strutture base per:
- **FIR, Finite Impulse Response**, con funzione di trasferimento pari a (senza retroazione):$$
H_{FIR}(f)=\sum_{i}\alpha_{i}e^{-2j\pi f\tau_{i}}
$$
- **IIR, Infinite Impulse Response**, con funzione di trasferimento pari a: $$
H_{IIR}(f)=\frac{\sum_{i} \alpha_{i}\exp(-2j\pi f\tau_{i})}{\sum_{j}\beta_{i}\exp(-2j\pi f \tau_{j})}
$$

# Banda
---

