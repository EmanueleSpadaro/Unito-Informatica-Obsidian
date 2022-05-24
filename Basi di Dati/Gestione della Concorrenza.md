## Gestione della concorrenza
La gestione della concorrenza è il motivo per il quale viene sviluppato il [[Serializzatore]].
Gli approcci per gestire la concorrenza sono principalmente 2:
- **Metodo ottimista**: il DBMS parte dall'ipotesi che le transazioni non vadano in conflitto, ma al momento del commit verifica che la [[storia]] delle operazioni eseguite sia una [[Storia#Storie seriali o Storie corrette|storia corretta]] secondo il [[Criterio di Serializzabilità]]. Non viene approfondito ulteriormente all'interno del corso.
- **Metodo pessimista**: il metodo pessimista parte dall'ipotesi diametralmente opposta, **previene la non serializzabilità**.
  Il metodo pessimista più diffuso consiste nel [[Metodo Basato sui Lock]].