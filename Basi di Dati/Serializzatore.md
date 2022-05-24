## Serializzatore
Il serializzatore è un modulo del DBMS che si occupa della [[Gestione della Concorrenza]] tra le transazioni e garantisce la proprietà di *isolamento* di [[ACID]].

Supponendo che vi siano due transazioni $T_1,T_2$ che eseguono delle operazioni sulla base di dati, e che la loro esecuzione sequenziale $T_1T_2$ e $T_2T_1$ porti a due stati differenti la base di dati, ma comunque consistenti, il DBMS esegue indifferentemente una [[Storia]] delle due disponibili.
E' cura del programmatore fare in modo che se si vuole forzare uno specifico ordine di esecuzione delle transazioni da parte del DBMS, queste vengano inviate sequenzialmente.

L'esigenza di eseguire le transazioni in parallelo deriva dai tempi morti che coinvolgono le operazioni con la memoria.

