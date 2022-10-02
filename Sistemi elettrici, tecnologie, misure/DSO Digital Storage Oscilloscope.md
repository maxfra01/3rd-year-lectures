# Architettura di un oscilloscopio digitale

Come tutti i dispositivi di questa tipologia, il DSO presenta il seguente schema (generico) con le componenti 'base' che consentono l'elaborazione, la memorizzazione e la visualizzazione dl segnale.

![[Pasted image 20220929184736.png]]

Tra i componenti abbiamo:
- I circuiti di condizionamenti, utili ad esempio all'amplificazione del segnale o all'attenuazione a seconda del Full Range
- l'ADC, il convertitore
- La memoria di acquisizione che conserva temporaneamente o no i segnali
- un microcontrollore per permettere l'elaborazione
- una memoria video e dispostivo di output(CRT o LCD) per la visualizzazione finale


# Schema operativo 1

Un primo tipo si sistema DSO è rappresentato nel seguente schema che verrà trattato in dettaglio per ogni componente:

![[Pasted image 20220929185441.png]]

Notiamo che esistono subito diverse interfacce per la post-elaborazione a carico di un computer.
Nella parte superiore distinguiamo diversi parametri di interesse:
- Banda passante dai circuiti analogici (Hz)
- Incertezze delle misure in ampiezza
- Frequenza di campionamento (Sa/s)
- Profondità della memoria (Sa)

Ora andiamo in profondità con l'analisi dello schema:

### Blocco 1

![[Pasted image 20220929185823.png]]



### Processo di acquisizione

![[Pasted image 20220929190203.png]]

I parametri di interesse dell'ADC sono:
- frequenza di campionamento (ordine dei GigaSample/s)
- Numero di bit per rappresentare gli stati
La frequenza di campionamento è decisa dall'utilizzatore andando ad agire con il comando `time/div` nella sezione 'Base tempi'.

In corrispondenza del segnale di trigger inizia la conversione alla frequenza stabilita, in modo da ottenere il numero predefinito di campioni.
Una volta in memoria i campioni acquisiti sono conservato per un tempo indefinito **a meno di un altro evento di trigger**.
Questo distingue gli oscilloscopi digitali da quelli analogici (i **transitori** negli analogici non erano memorizzabili).

Distinuguiamo due tipi di campionamento:
- quello **in tempo reale** che avviene alla frequenza di campionamento
- quello **in tempo equivalente** che si usa solo per segnali ripetuti (periodici)

Questa seconda tecnica si attua attivando ripetutamente il trigger e far partire l'acquisizione con dei ritardi crescenti; dopo aver ottenuto un numero di campioni sufficienti (pari al record lenght) possiamo ricostruire il segnale.

![[Pasted image 20220929200832.png]]

Secondo questa tecnica si ottiene un campionamento a frequenza: $$f_{c_{eq}}=\frac{1}{\Delta t} > f_c$$
L'inconveniente di questa tecnica è l'elevata durata del processo di acquisizione.



