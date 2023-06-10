La potenza dinamica consumata da un circuito CMOS è:
$$
P_{d}=fCV_{AL}^2
$$
Tempo di propagazione HL o LH:
$$
t_{pLH}=0.69 \cdot R \cdot C
$$
# Linee di trasmissione
---
Impedenza caratteristica di una linea di trasmissione:
$$
Z_{\infty}=\sqrt{ \frac{L_{u}}{C_{u}} }
$$
Velocità della linea:
$$
p = \frac{1}{\sqrt{ L_{u}C_{u} }}
$$
Coefficiente di riflessione:
$$
\Gamma_{T} =\frac{ R_{T}- Z_{\infty}}{R_{T}+Z_{\infty}}
$$

# Jitter in apertura
---
Massimo Jitter in apertura:
$$
\Delta V \cdot SR \cdot \Delta T_{JA}
$$
Dove Lo slew Rate cambia a seconda della forma del segnale:
- Triangolare $SR=\frac{A_{s}}{T}$ con $T$ che è meta del periodo dell'onda
- Sinusoidale $SR=A\pi f$ dove $f=\frac{\omega}{2\pi}$ 

# Campionamento
---
$$
SNR_{a}=20 \cdot \textrm{n poli }  \cdot \log_{10}\left( \frac{F_{s,1CH} \cdot k-f_{B}}{f_{B}} \right)\quad  
$$
$$
SNR_{j}=20 \cdot \log_{10}\left( \frac{1}{\pi \cdot f_{B} \cdot t_{j}} \right)
$$
$$
SNR_{TOT} =10 \log_{10} \sum_{i} \frac{1}{A_{i}}\quad \textrm{dove} \quad  A_{i}=10^{-SNR_{i}/10}
$$
$$
ENOB=\frac{SNR_{tot}}{6}-0.3
$$

# Raddrizzatori
---
Raddrizzatore a singola semionda:
$$
I_{O}=C \frac{V_{ripple}}{\frac{T}{2}}
$$
Raddrizzatore a onda intera:
$$
I_{O}=C \frac{V_{ripple}}{T}
$$

# Regolatori di tensione
---
Tipo BUCK:
$$
\frac{V_{OUT}}{V_{IN}}=D
$$
Tipo BOOST:
$$
\frac{V_{OUT}}{V_{IN}}=\frac{1}{1-D}
$$
Tipo BUCKBOOST:
$$
\frac{V_{OUT}}{_{VIN}}=- \frac{D}{1-D}
$$
# 