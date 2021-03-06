## Metodo Basato sui Lock
Il metodo basato sui lock consiste nell'introduzione di un protocollo che prevede l'utilizzo di 3 procedure per effettuare delle operazioni sui dati:
- **LS(X)**: *Lock Shared su X*, è una procedura che permette di acquisire un lock non esclusivo che è ottenibile anche da altre transazioni in contemporanea. Questo lock è caratteristico delle transazioni che voglio effettuare delle operazioni di lettura sui dati, in quanto non vi è alcun problema se due o più transazioni leggono contemporaneamente lo stesso dato.
- **LX(X)**: *Lock eXclusive su X*, è una procedura che garantisce l'accesso in mutua esclusione alla risorsa X ed è sostanzialmente utilizzata per delle operazioni di modifica che coinvolgono la scrittura del dato.
- **UN(X)**: *UNlock su X*, è una procedura che rilascia la risorsa, permettendo al database di fornire il lock su quest'ultima ad altre transazioni. Viene usata quando la transazione ha terminato di effettuare operazioni su una determinata risorsa.

Il metodo basato sui lock utilizza un tecnica chiamata [[Two-Phase Lock]].

I lock hanno un [[Grado di Granularità]] che determina quanto minuziosa sia la gestione delle risorse.