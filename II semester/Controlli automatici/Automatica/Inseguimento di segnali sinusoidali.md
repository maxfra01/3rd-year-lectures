# Errore della risposta in frequenza
---
Il riferimento canonico diventa: $r(t)=\sin(\omega_{0}t)$
Mentre per quanto riguarda la fdt d'errore è del tipo:
$$
W_{e}(s)=\frac{e(s)}{r(s)}=\frac{K_{r}}{1+G_{a}}
$$
L'errore è quindi del tipo sinusoidale con pulsazione corrispondente a quella del riferimento:
$$
e_{p}(t)=E \cdot \sin(\omega_{0}t+\phi_{e})
$$
Per limitare l'errore mi limito a limitare l'ampiezza della sinusoide ovvero minimizzo:
$$
E=|\frac{K_{r}}{1+G_{a}(j\omega_{0})}|
$$
Per fare ciò $G_{a}$ dev'essere molto grande, e questo avviene a **Basse frequenze**.

# Implicazioni sul progetto del controllore
---
