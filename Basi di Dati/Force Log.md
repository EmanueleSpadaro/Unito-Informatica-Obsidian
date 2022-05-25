## Force Log
Il Force Log è una procedura chiamata su una o più transazioni che consiste nel rendere persistenti le operazioni descritte nei log files.

La persistenza è garantita a livello logico dal [[Gestore del Ripristino]], il quale però non è a conoscenza delle politiche in cui opera il [[Gestore del Buffer]]: è quindi possibile che una transazioni resa concettualmente persistente dal [[Gestore del Ripristino]] non lo sia fisicamente.
E.G.: per motivi di performance si potrebbe decidere di applicare permanentemente le modifiche in [[Memoria Standard]] solo dopo un determinato numero di transazioni.