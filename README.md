## COME USARE IL PROGETTO

Lo scopo del progetto e' quello di guidare l'utente:
1. nella creazione del database neo4j (con docker-compose) e tramite il dataset instagram di kaggle
2. fare un'analisi dei dati guidata dalle research question

L'utente dovra' quindi seguire le istruzioni date dai commenti del notebook come una sorta di "guida". 
Nel caso in cui l'utente voglia provare direttamente sul browser di neo4j le varie call (load csv, match,...) puo' accedervi come indicato sul notebook dopo aver avviato il docker container. Per scrivere le varie call basta copiare tutto il testo dentro i tre apici (es: '''match (a) return a''').

**NB**: Si puo' saltare il passaggio di download del dataset. Questo è reso possibile dal fatto che rendo disponibili gia' unzippati i file .csv necessari.

## CARTELLA DATA

La cartella data contiene 8 file csv che serviranno per la costruzione del grafo:
* `comments.csv`; elenco dei commenti fatti da un certo utente sotto un post
* `follows.csv`; relazioni di quale utente segue quale
* `likes.csv`; relazioni dei like di un utente ad un post
* `photo_tags.csv`; relazioni di un tag su un post
* `photos.csv`; le foto uploadate da un certo utente
* `tags.csv`; i tag scritti 
* `users.csv`; gli utenti della piattaforma  

Nella cartella media verrano invece salvate tulle le immagini che serviranno come corredo ai commenti markdown del notebook; ad esempio per la spiegazione dello schema del grafo.


## REFERENCE PER EVENTUALI PROBLEMATICHE

* [dataset kaggle](https://www.kaggle.com/datasets/bhanupratapbiswas/instgram) 
* [documentazione GDS](https://neo4j.com/docs/graph-data-science/current/)
* [documentazione docker-compose](https://docs.docker.com/compose/)
* [documentazione apoc core e apoc extended](https://neo4j.com/labs/apoc/)