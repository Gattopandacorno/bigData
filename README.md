## COME USARE IL PROGETTO

Lo scopo del progetto e' quello di guidare l'utente:
1. nella creazione del database neo4j (con docker-compose) e tramite il dataset instagram di kaggle
2. fare un'analisi dei dati e provare a rispondere alle research question

Si dovra' quindi seguire le istruzioni date dai commenti del notebook come una sorta di "guida". 
Nel caso in cui si voglia provare direttamente sul browser di neo4j le varie call (load csv, match,...) ci si puo' accedere come indicato sul notebook dopo aver avviato il docker container. 
Per scrivere le varie call basta copiare il testo dentro i s.run(''' '''); ad esempio in `s.run('''match (a) return a''')` bisogna copiare solo `match (a) return a`.

Per quanto riguarda l'installazione delle dipendenze python è stato usato `poetry` ma pyproject.toml viene letto anche dal comando `pip`.
Si riportano i due modi per installare le dipendenze:
1. ```bash 
    poetry install
2. ``` bash
    pip install
Se si sta utilizzando un IDE come visual studio code l'ambiente virtuale che dovra' poi essere usato per il notebook viene detectato di default e non dovrebbero essere necessari ulteriori passaggi. 
Se si notano errori per quanto riguarda l'import delle dipendenze python si controlli il virtual env o l'env selezionato per l'interprete python.
Nel caso in cui ci fossero dubbi sul fatto che l'ambiente virtuale sia stato attivato ed in uso si puo' controllare con 
```bash
poetry env use python
```

**NB**: I comandi devono essere ovviamente lanciati da terminale nella cartella principale contenente pyproject.toml .

**NB**: Si puo' saltare il passaggio di download del dataset. Questo è reso possibile dal fatto che esistono gia' unzippati i file .csv necessari.

## CARTELLA DATA

La cartella data contiene 8 file csv che serviranno per la costruzione del grafo:
* `comments.csv`; elenco dei commenti fatti da un certo utente sotto un post
* `follows.csv`; relazioni di quale utente segue quale
* `likes.csv`; relazioni dei like di un utente ad un post
* `photo_tags.csv`; relazioni di un tag su un post
* `photos.csv`; le foto uploadate da un certo utente
* `tags.csv`; i tag scritti 
* `users.csv`; gli utenti della piattaforma  
* `test.csv`; nel primo commit github è stato pubblicato anche questo mini test
usato appunto per capire dove vengano salvati i file sul container. Potrebbe sparire in altre versioni del codice.

Dopo aver lanciato il comando di docker questa cartella viene oscurata a qualsiasi utente che non sia neo4j e root. Si può riportare alle permission di una cartella consultabile anche da un altro utente con il comando:
```bash
sudo chmod 755 -R data  
```
dove 755 sono i permessi assegnati e -R estende la modifica anche ai file nella cartella.
In quanto non utile consultarne i file si sconsiglia di usare il comando, nel caso dovesse servire consultare prima la [documentazione](https://linux.die.net/man/1/chmod) per capire anche come meglio assegnare le permission.
Si ricorda inoltre che non è mai una buona prassi assegnare 777 in quanto non è sicuro.

## CARTELLA MEDIA
In essa vengono salvate tulle le immagini che serviranno come corredo ai commenti markdown del notebook; ad esempio per la spiegazione dello schema del grafo.

## REFERENCE PER EVENTUALI PROBLEMATICHE

* [dataset kaggle](https://www.kaggle.com/datasets/bhanupratapbiswas/instgram) 
* [documentazione GDS](https://neo4j.com/docs/graph-data-science/current/)
* [documentazione docker-compose](https://docs.docker.com/compose/)
* [documentazione apoc core e apoc extended](https://neo4j.com/labs/apoc/)