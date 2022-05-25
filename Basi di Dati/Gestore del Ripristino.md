## Gestore del Ripristino
Il Gestore del Ripristino è un modulo del DBMS che si occupa dell'integrità della base di dati durante la sua operatività ed è responsabile di garantire la proprietà di **Consistenza** di [[ACID]].
E' secondariamente responsabile dell'*atomicità* delle transazioni durante la fase di ripristino della base di dati attraverso l'utilizzo dei [[Log Files]].
Agisce in caso di problemi software quali i rollback richiesti dal [[Serializzatore]], dal Gestore delle Transazioni o crash, e in caso di problemi fisici come i [[Guasti alle Periferiche]]. 
### Fase di Ripristino
La fase di ripristino consiste nell'esecuzione di due procedure su due tipologie di lista di transazioni.
**LA** sta ad indicare la **L**ista *(transazioni)* **A**ttive, ovvero tutte le transazioni il quale commit non è stato ancora effettuato.
**LC** sta ad indicare la **L**ista *(transazioni)* **C**ommit, ovvero tutte le transazioni il quale commit è stato citato all'interno dei log files.
- **UNDO(LA)**: per ogni transazione $T_i$ all'interno della lista, si esegue un **rollback al BS(X)**.
- **REDO(LC)**: per ogni transazione $T_i$ all'interno della lista, si esegue un **force log dello AS(X)**.

La fase di ripristino può richiedere molto tempo, ma può differire qualora vengano implementati i [[Log Files#Checkpoint|Checkpoint]] all'interno dei [[Log Files]].
In tal caso vengono gestite solo le transazioni attive descritte all'interno dei [[Log Files#Checkpoint|Checkpoint]].
