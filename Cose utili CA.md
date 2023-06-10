# Sistema a stabilità regolare
---
Condizioni necessarie:
Considerando il termine dato dal prodotto dei blocchi della funzione ad anello tenendo conto dei poli del controllore:
$$
F_{1}(s)F_{2}(s) \cdot \frac{1}{s^h}
$$
Abbiamo a vedere se:
- Non ci sono poli a parte reale POSITIVA
- Non ci sono zeri a parte reale POSITIVA
- I guadagni dei blocchi sono positivi
- Nel diagramma di bode c'è una sola omega di crossover e un solo punto a fase -180

# Progetto del controllore PID
---
A partire dalla funzione di trasferimento data $F(s)$ oppure $G(s)$ applichiamo il comando MATLAB:

```matlab
[Gm,Pm,Wgm,Wpm] = margin(F);
```

Così facendo ho il valore del margine di guadagno in unità naturali, il quale corrisponderà a $\overline{K}_{p}$.
L'informazione riguardo la `Wgm` ci dice a che pulsazione leggiamo il gain margin.

Se il valore del margine di guadagno risulta finito posso procedere con il metodo in catena chiusa.

Definisco quindi la funzione ad anello `Ga=Rpid*F` e applicando `margin(Ga)` noto se il margine di fase è sufficiente.

