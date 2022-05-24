Il B-Albero è una struttura dati con parametro *branching factor* **m**.
Il **branching factor** consiste nel numero di rami che può avere un nodo.
Un **nodo corrisponde ad una pagina**.
Gli elementi di un nodo sono detti [[Data Entry]]

Se un B-Albero ha un branching factor 5, i nodi hanno 4 elementi e avranno al massimo 5 rami, perché un nodo con j elementi ha j+1 rami.

La struttura peculiare del B-Albero permette al DBMS di **trasformare il B-Albero in un [[B+Albero]]**, cioè un albero le chiavi nei nodi superiori vengono portate fino alle foglie all'interno delle slot libere per poter emulare un accesso sequenziale.
L'accesso sequenziale è reso possibile in quanto **le foglie hanno un puntatore alla foglia adiacente**.

Considerando un valore di branching factor 100 e 3 livelli di albero, il numero di tuple N diventa 100^3 -> 1 Milione di chiavi indicizzabili con la struttura piena.
Questa struttura dati pone la sua fondamentale efficienza sul bilanciamento dell'albero, un albero troppo vuoto non mi serve a nulla, un albero troppo pieno impone lo spezzamento dell'albero per l'introduzione di ogni chiave.
I DBMS operano per garantire un **bilanciamento che si attesta sul 70% del numero di tuple indicizzabili**: un B-Albero con branching factor m e 3 livelli di albero diventa quindi ottimale per indicizzare circa 700.000 chiavi.

L'ordinamento permette di leggere in modo sequenziale e ordinato le chiavi da sinistra a destra.

