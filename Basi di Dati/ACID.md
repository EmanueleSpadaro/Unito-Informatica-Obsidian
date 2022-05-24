Le proprietà **ACID** delle transazioni permettono ai DBMS di funzionare correttamente.
- **A**tomicità: sono una unità di programma e vengono eseguite per intero.
- **C**onsistenza: vengono eseguite solo se la loro esecuzione mantiene la base di dati in uno stato consistente, nel rispetto dei vincoli di integrità referenziali per esempio.
- **I**solamento: devono essere scritte pensando che siano le uniche ad essere eseguite, senza preoccuparsi della concorrenza.
- **D**urabilità: meglio tradotta con persistenza, la loro esecuzione completa deve essere riflettuta in maniera permanente sulla base di dati