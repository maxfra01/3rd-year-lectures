### Campionamento
**E' il campo continuo dei valori assunti da un segnale analogico**
Si associa al FR un insieme di valori discreti in base a quanti bit abbiamo a disposizione
$$
N \space \textrm{bit} \implies 2^{Nb} \space \textrm{ stati discreti } \quad     
$$
Da ciò consegue che la tensione di quantizzazione è pari a 
$$
V_{q}= \frac{V_{FR}}{2^{Nb}}
$$

### Interpolazioni
Sotto l'ipotesi di segnale con banda limitata $\omega_{max}=2\pi f_{max}$ allora 
$$
10 >\frac{f_{c}}{f_{max} }> 2.5 \quad \textrm{Interpolazione sync (troncata)} \quad   
$$
$$
 20> \frac{f_{c}}{f_{max}}> 10 \quad \textrm{Interpolazione lineare} \quad  
 
$$
$$
 \frac{f_{c}}{f_{max}}> 20 \quad \textrm{Dots mode} \quad  
$$
### Aliasing
Si verifica quano non rispetto il teorema di Shannon aka teorema del campionamento
$$
f_{c} \geq 2 f_{max}
$$
