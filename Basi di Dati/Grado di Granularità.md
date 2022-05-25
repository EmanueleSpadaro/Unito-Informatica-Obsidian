## Grado di granularità
Il grado di granularità di un [[Metodo Basato sui Lock |Lock]] determina quanto minuziosa sia la gestione delle risorse condivise tra le transazioni.
Una **maggiore granularità** dei lock consegue in una **maggiore complessità** della [[Gestione della Concorrenza]].

Il grado di granularità è da vedere come il livello in cui il DBMS inizierà a [[Gestione della Concorrenza|gestire la concorrenza]] attraverso l'utilizzo del [[Metodo Basato sui Lock]].
- **Tuple**: l'accesso alle tuple di una tabella sarà il livello in cui il DBMS inizierà a gestire la concorrenza tra le transazioni.
- **Attributo**: grado di granularità maggiore rispetto a quello in riferimento alle *tuple*, l'accesso alle tuple è permesso a transazioni multiple, e la loro concorrenza verrà gestita al livello degli attributi interessati.
- **Pagine**: grado di granularità riferito alle pagine del DB.
- **File**: grado di granularità in riferimento agli interi file contenenti le pagine che a loro volta contengono le tuple che sono composte da attributi.
