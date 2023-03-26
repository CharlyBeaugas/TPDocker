# TP Docker - TLC
## Charly Beaugas - Jules Benveniste

## Lancer le projet
Effectuer la commande suivante à l'aide votre terminale:```sudo docker-compose up -d```

## Problème
A l'exécution de la commande *docker-compose*, une erreur est renvoyé relative à la commande présente dans le Dockerfile (./App/Dockerfile: ```RUN    apt-get install -f libdc1394-22 ```).
Il semblerait que la librairie échoue à s'installer.