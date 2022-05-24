# Architettura dei DBMS
L'architettura dei DBMS è strutturata principalmente in 4 macrocomponenti:
- **Gestore delle Transazioni** : è il modulo software adibito al rispetto della proprietà di **atomicità** delle transazioni.
- **[[Serializzatore]]** : si occupa di garantire la proprietà di **isolamento** delle transazioni, che permette all'utente di progettare le proprie transazioni come se fossero eseguite singolarmente.
- **Gestore del Ripristino** : modulo dedicato al ripristino della base di dati in caso di crash o malfunzionamento, è il garante della proprietà di **consistenza** in quanto permette di riportare ad uno stato consistente la base di dati
- **[[Gestore del Buffer]]** : modulo software dedicato allo scambio di informazioni tra memoria persistente e memoria centrale, facendo sì che le pagine della base di dati caricate in memoria centrale riflettano le proprie modifiche sulle pagine in memoria permanente. Questo modulo si occupa della **durabilità** dei dati.
Come possiamo notare l'architettura dei DBMS è studiata attorno alle transazioni e la stretta correlazione con le proprietà **[[ACID]]**, *Atomicità*, *Consistenza*, *Isolamento*, *Durabilità*. 