## Log Files
I log files sono file contenuti all'interno della [[Memoria Stabile]] e sono file in cui figurano tutte le operazioni svolte dalle transazioni durante il runtime del DBMS.

I log files contengono **transazioni già [[Criterio di Serializzabilità|serializzate]]**, le cui operazioni vengono descritte riga per riga attraverso:
- $<T_1,$ start$>$: direttiva che informa dell'inizio di una determinata transazione $T_1$.
- $<T_1, X, BS(X), AS(X)>$: direttiva che descrive un'operazione della transazione $T_1$ in riferimento all'oggetto $X$.
  Figura inoltre il **B**efore **S**tate di $X$, cioè lo stato iniziale di $X$ prima della transazione, ed lo **A**fter **S**tate di $X$, stato finale dell'oggetto $X$ dopo la transazione.
- $<T_1,$ commit$>$: direttiva che informa che la transazione è stata applicata alla base di dati in [[Memoria Standard]].
  E' preceduta da un [[Force Log]].
- $<T_1,$ abort$>$: direttiva che informa che la transazione è stata abortita, implicando un rollback delle operazioni eseguite.
  E' preceduta da un [[Force Log]].

Il logging nei database transazionali, cioè quelli affrontati nel corso, è fondato sul principio di **Write-Ahead Logging (WAL)**: tutte le operazioni eseguite vengono prima scritte sui file di log e poi effettuate concretamente.
È il metodo che garantisce atomicità e durabilità e, al tempo stesso permette di mantenere prestazioni elevate.

### Checkpoint
I checkpoint sono delle direttive introducibili all'interno dei Log Files periodicamente che descrivono tutte le transazioni ancora attive in un determinato punto.
Il loro scopo è quello di rendere più leggero il ripristino, evitando quindi che la Base di Dati resti offline per troppo tempo durante questa fase.
 