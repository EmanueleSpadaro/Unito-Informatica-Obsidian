## Gestore del Buffer
Il gestore del buffer è il modulo che si interfaccia in maniera diretta con i due tipi di memoria con i quali interagiamo, memoria persistente e memoria volatile.
Garantisce la proprietà di *durabilità* di [[ACID]].
L'accesso alla memoria può avvenire in 3 modi:
- **Accesso sequenziale**: è distinguibile tra *sequenziale* e *seriale*, dove la differenza tra le due tipologie risiede nell'ordinamento o meno dei dati. Questo tipo di accesso ha un caso peggiore di N accessi, dove N sono i record.
- **Accesso tabellare**: l'accesso tabellare utilizza gli [[Indici]] per ottimizzare il processo di ricerca dei record. Gli [[Indici]] risiedono fuori dall'area primaria dove risiedono i dati, ma comunque nella zona standard della memoria persistente.
  L'implementazione di questo accesso in memoria è spesso riconducibile all'utilizzo della struttura dati **[[B-Albero]]**.
- **Accesso diretto**: l'accesso diretto fa utilizzo delle tabelle di hash, ma purtroppo non verrà coperto dal corso.
L'utilizzo degli [[Indici]] è estremamente consigliato qualora le opzioni di modifica non siano molto frequenti, in quanto garantiscono ottime prestazioni per le prestazioni di ricerca, ma impongono costi computazionali pesanti per le alterazioni degli [[Indici]].
Caricando i dati delle pagine in memoria, è il modulo che si occupa anche dell'[[Ottimizzazione Fisica]] delle query.