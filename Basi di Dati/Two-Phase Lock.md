## Two-Phase Lock
E' una tecnica che consiste nell'imporre 2 fasi durante una transazione:
- **Locking Phase**: è la fase in cui il grafico del numero di lock richiesti da una transazione aumenta in rapporto al tempo, è l'unica fase in cui una transazione può richiedere un lock **LS(X)** o **LX(X)**.
- **Releasing Phase**: fase in cui la transazione inizia a rilasciare i lock attraverso la procedura **UN(X)**.