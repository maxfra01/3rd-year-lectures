# Stadi comuni
---
Ora che abbiamo esaminato le caratteristiche dei [[Transistor]] possiamo costruire [[Amplificatori]] a partire da transistor MOS o BJT.

A seconda di come si dispone il transistore e di come si preleva l'uscita e l'ingresso otteniamo tre stadi comuni:

| Source comune                        | Drain comune                         | Gate comune |
| ------------------------------------ | ------------------------------------ | ----------- |
| ![[Pasted image 20221108085656.png]] | ![[Pasted image 20221108085714.png]] | ![[Pasted image 20221108085735.png]]            |

## Stadio Source comune

![[Pasted image 20221108093821.png]]

Dall'analisi di piccolo segnale si ottiene il circutio a destra, da cui deduciamo che:
$$
R_{in} \to \infty \quad R_{out}=R|| r_{0}
$$
$$
A_{v}=-g_{m}(R ||r_{0})
$$
Dalla funzione di trasferimento $A_{v}$ notiamo che la precedente configurazione crea un **amplificatore di tensione invertente** con modulo anche elevato.

## Drain comune

![[Pasted image 20221108094640.png]]

Dall'analisi circuitale ricavo che:
$$
R_{in} \to \infty \quad R_{out}=\frac{1}{g_{m}} || (R ||r_{0})
$$
$$
A_{v}=\frac{g_{m}R'}{1+g_{m}R'}
$$
Dove $R'=R ||r_{0}$ 
Otteniamo un **amplificatore di tensione con amplificazione positiva (non invertente) e minore di 1**.

## Gate comune

![[Pasted image 20221108095113.png]]

Dall'analisi di piccolo circuito otteniamo:
$$
R_{in}=\frac{R+r_{0}}{g_{m}r_{0}+1} \approx \frac{1}{g_{m}} \quad R_{out}=R'=R ||r_{0}
$$
$$
A_{v}=g_{m}R' + \frac{R'}{r_{0}} \approx g_{m}R'
$$
Abbiamo ottenuto un **amplificatore di tensione non invertente con modulo elevato**

| Tipo          | $A_{v}$                       | $R_{in}$                  | $R_{out}$                 | commenti |
| ------------- | ----------------------------- | ------------------------- | ------------------------- | -------- |
| Source comune | $-g_{m}R'$                    | $\to \infty$              | $R'$                      |          |
| Drain comune  | $\frac{g_{m}R'}{1+g_{m}R'}<1$ | $\to \infty$              | $\approx \frac{1}{g_{,}}$ |          |
| Gate comune   | $\approx g_{m}(R')$           | $\approx \frac{1}{g_{m}}$ | $R'$                      |          | 


# Amplificatore a più stadi
---
