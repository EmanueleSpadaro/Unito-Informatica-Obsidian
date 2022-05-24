L'ottimizzazione fisica delle query viene effettuata dal [[Gestore del Buffer]] e consiste principalmente in due categorie:
- **Ottimizzazione fisica delle selezioni**: avviene seguendo due strategie principali.
La prima strategia consiste nel valutare le selezioni per i predicati congiunti da una AND separatamente, se coinvolgono attributi indicizzati, dando vita a diversi insiemi di tuple che rispettano tali predicati. Essendo congiunti, il DBMS effettua una intersezione degli insiemi ottenendo le tuple che rispettano tutti e tre i predicati, e carica le rispettive pagine in memoria centrale. Eventuali predicati che non valutano attributi indicizzati lavoreranno ora su una tabella in memoria centrale, quindi con tempi di accesso di 6 ordini di secondo inferiori.
La seconda strategia consiste nel valutare il costo di accesso sequenziale alla tabella con la selettività degli attributi indicizzati attraverso algoritmi di euristica.
Solo il predicato più selettivo viene effettuato inizialmente, il resto verrà eseguito sulla conseguente tabella caricata in memoria centrale.
Diversi studi di comparazione hanno indicato che le due strategie danno tempi di calcolo paragonabili.
- **Ottimizzazione fisica delle join**: è la porzione dell'algoritmo di ottimizzazione fisica che decreta fondamentalmente la differenza tra DBMS di successo e non. La join è l'operazione più costosa computazionalmente e vengono considerati parametri quali:
  la possibilità di caricare in memoria centrale gli operandi, l'unione insiemistica e la differenza insiemistica, se vi è richiesto ordinamento tramite clausola *order by* oppure se è stata utilizzata la clausola *distinct*.
In ogni caso, il DBMS ricorre all'utilizzo degli indici solo quando il costo sequenziale è maggiore di quello tabellare.