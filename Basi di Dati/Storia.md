## Storia delle transazioni
La storia delle transazioni corrisponde alla sequenza delle operazioni che quest'ultime vanno ad effettuare sulla base di dati.

Date due transazioni $T_1,T_2$ per cui $$T_1=\{r_1(A), w_1(A), r_1(B), w_1(B)\}\space\space\space T_2=\{r_2(A), w_2(A), r_2(B), w_2(B)\} $$ si considerano storie di una transazione tutte le possibili sequenze di tali operazioni.

### Storie seriali (o Storie corrette)
Le storie seriali consistono in delle storie che corrispondono all'esecuzione sequenziale di un gruppo di transazioni.
Il numero di storie seriali ammonta a $n!$, dove $n$ equivale al numero di transazioni prese in considerazione.

Date $T_1,T_2$ come sopra, le storie seriali sono $2! = 2$ e cioè:
$$ T_1T_2 \space\text{e}\space T_2T_1$$
### Storia equivalente (o view-equivalente)
Una storia è detta equivalente (view-equivalente) ad un'altra se e solo se:
1. L'**insieme delle operazioni** di $S_1$ è uguale a quelle di $S_2$.
2. **Condizioni sull'input**:
   - se in $S_1$ figura una operazione di lettura $r(A)$ prima di una sua scrittura, allora anche in $S_2$ deve esservi la stessa occorrenza
   - l'ordine di lettura $r(A)$/scrittura $w(A)$ su un dato $A$ deve essere globalmente rispettato da entrambe le storie, anche se in momenti differenti
3. **Condizioni sullo stato**: l'ultima operazione su un dato deve coincidere. Quindi se l'ultima operazione su un dato $A$ in $S_1$ è $w_1(A)$, allora l'ultima operazione sul dato $A$ in $S_2$ sarà $w_2(A)$.
La definizione di storia view-equivalente permette di definire il **[[Criterio di Serializzabilità]]**.
 