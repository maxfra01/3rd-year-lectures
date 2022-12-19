# Transistor
---
La regione di saturazione, ovvero quella in cui un transistor si comporta come un generatore di corrente controllato in tensione, è descritta dalle seguenti condizioni
$$
v_{gs,sg}>V_{TH}
$$
$$
v_{ds,sd}>v_{gs-sg}-V_{TH}
$$
Altre utili relazione per descrivere il transistor sono:
$$
i_{D}=\frac{1}{2}\beta(v_{gs,sg}-V_{TH})^2(1+\lambda v_{ds,sd})
$$
$$
g_{m}=\frac{ \partial i_{D} }{ \partial v_{gs,sg} }=\beta(v_{gs,sg}-V_{TH})(1+\lambda v_{ds,sd}) \approx \sqrt{ 2I_{D}\beta } 
$$
$$g_{0}=\frac{1}{r_{0}}=\frac{ \partial i_{D} }{ \partial v_{ds,sd} } \approx I_{D}\lambda$$
E' possibile combinare più stadi comuni in cascata ricordandosi di inserire il condensatore di accoppiamente per trasferire solo la componente in AC.

# Operazionali
---
![[Pasted image 20221129093434.png]]
