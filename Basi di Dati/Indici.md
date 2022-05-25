Gli indici risiedono fuori dall'area primaria e si suddividono in:
- **Indice primario**: è un indice con diretta corrispondenza all'attributo chiave con il quale i record vengono ordinati, che non permette quindi la presenza di duplicati all'interno del [[B-Albero]].
- **Indice clusterizzato**: è un indice applicato su attributi non chiave con il quale viene effettuato l'ordinamento, permettendo la presenza di duplicati poiché non primari.
  **Può essere fuso con l'area primaria rendendo le data entry del tipo *<k, tupla>***, rendendo il [[B+Albero]] la vera area primaria, contenendo sia dati che indici.
- **Indice secondario**: è un indice applicato su attributi non chiave con i quali non viene effettuato alcun tipo di ordinamento dei record.
In una tabella possono esserci **al più un indice primario o un indice clusterizzato** e **zero o più indici secondari**.

L'utilizzo effettivo degli indici da parte del DBMS avviene principalmente in due fasi dell'[[Ottimizzazione Fisica]].

L'esperienza di progettazione ha portato allo sviluppo di alcune best practices:
- Non ha senso implementare degli indici su tabelle di poche pagine.
- L'utilizzo degli indici su tabelle ad alta frequenza di update/modifica/cancellazione è sconsigliato in quanto rallenta troppo il DBMS per il mantenimento della struttura dati.
- Applicare degli indici su chiavi poco selettive rende poco performante la ricerca indicizzata rispetto a quella sequenziale (non ha senso indicizzare un attributo che può assumere pochissimi valori e quindi restituire la maggior parte delle tuple).
- Indicizzare gli attributi chiave primaria e chiavi esterne è estremamente consigliato per efficientare le operazioni di join.
- Indicizzare eccessivamente una tabella sulla maggior parte degli attributi equivale all'utilizzo di indici su tabelle ad alta frequenza di update/modifica/cancellazione, in quanto la modifica di pochi attributi potrebbe costare eccessivamente per il mantenimento dell'indicizzazione.
- L'utilizzo degli indici è consigliatissimo su tabelle soggette ad alta intensità di query con richieste di ordinamento.
- E' opportuno conoscere gli algoritmi di ricerca del DBMS per poter adattare le proprie tabelle e i relativi indici al fine di massimizzare l'efficienza del DBMS.