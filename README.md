## COME USARE IL PROGETTO

Lo scopo del progetto e' quello di guidare l'utente:
* nella creazione del database neo4j (con docker-compose) e tramite il dataset instagram di kaggle
* fare un'analisi dei dati guidata dalle research question

L'utente dovra' quindi seguire le istruzioni date dai commenti del notebook come una sorta di "guida". 

**NB**: Si puo' saltare il passaggio di download dei dati (1° casella di codice) nel caso in cui l'utente non abbia un account kaggle. Questo è reso possibile dal fatto che rendo disponibili gia' unzippati i file .csv necessari.

## CARTELLA DATA

La cartella data contiene 8 file csv che serviranno per la costruzione del grafo.
* `comments.csv`; elenco dei commenti fatti da un certo utente
* `follows.csv`; relazioni di quale utente segue quale
* `likes.csv`; relazioni dei like di un utente ad una foto
* `photo_tags.csv`; relazioni di un tag su una foto
* `photos.csv`; le foto uploadate da un certo utente
* `tags.csv`; i tag scritti 
* `test.csv`; un mini csv di tre righe usato come test per il salvataggio dei file in docker
* `users.csv`; gli utenti della piattaforma  


## REFERENCE PER EVENTUALI PROBLEMATICHE

* [dataset kaggle](https://www.kaggle.com/datasets/bhanupratapbiswas/instgram) 
* [documentazione GDS](https://neo4j.com/docs/graph-data-science/current/)
* [documentazione docker-compose](https://docs.docker.com/compose/)
* [documentazione apoc core e apoc extended](https://neo4j.com/labs/apoc/)