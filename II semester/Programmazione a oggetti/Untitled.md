# Classi astratte 
---
Certe volte vogliamo implementare delle classi i cui figli verranno effettivamente istanziate: pensiamo ad esempio ad una classe che descriva la forma di una figura da disegnare:
```
public abstract class Shape{
	private int color;

	//Implemented in child classes
	public abstract void draw();
}
```
La parola chiave abstract indica che non i metodo è in qualche modo incompleto e adnrà implementato in classi figlie tramite @override.

```ad-note
Se anche solo un metodo di una classe è abstract, la classe intera va dichiarata come tale.
```

# Pattern
---
Ci troviamo in contesto di un problema comune, come ordinare dei dati, ma dobbiamo implementare una metrica di paragone per i dati.
Questo esempio va nella categoria del **Template Method** la cui forma generale è la seguente:

![[Pasted image 20230329165502.png]]

Un altro Template del tipo **Composite pattern** è dato dall'esempio dell'**extension tree**.
Possiamo definire una classe astratta Espressione, che verrà poi estesa da un classe operazione e una classe valore.
Possiamo dunque dichiarare due metodi astratti per eval() e formula() e implementarli singolarmente.
Il pattern noto generale è del tipo:

![[Pasted image 20230329165954.png]]


### Pattern Iteratore

![[Pasted image 20230329172246.png]]

