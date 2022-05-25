## Guasti alle perifiche
I guasti alle perifiche consistono nel fallimento dell'hardware che mantiene la parte di [[Memoria Standard]] del DBMS.
La gestione di questi eventi può rivelarsi molto complicata: implementare soluzioni di **RAID** (*Reduntant Array of Independent Disks*) o **Georeplicazione** (*replicazione delocalizzata*) è un ottimo modo per farlo.

###### Dump
I dump consistono in delle **copie 1:1 della base di dati** salvate nella [[Memoria Stabile]] **a log azzerati**.
In caso di guasto si porta online la base di dati con il dump e si riapplicano le transazioni descritte all'interno del log.
E' detta anche **tecnica di ripristino a freddo** o **dump restore**.