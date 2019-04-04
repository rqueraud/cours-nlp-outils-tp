# Partie 6 : Elasticsearch

Elasticsearch stocke les données dans un index. Un index permet de lister les champs des documents à stocker et de définir leur type pour en optimiser le stockage/requetage.

C'est un base de données NoSQL qui a la propriété de maintenir un index inversé pour les données text. C'est à dire qu'au lieu de stocker les élements comportant chaque document, elle stocke quels sont les documents associés aux différents champs. Elle intègre de plus une notion de shards et de replicas, on augmente ainsi les performances en lecture tout en profitant d'une meilleure disponibilité.

Elle propose un accès aux données par le biais de requêtes HTTP GET/POST. Vous pouvez donc y accéder directement avec Postman ou votre navigateur. Toutefois, le mieux pour traiter les données reste tout de même un bon script python.

## Exercice 1 : Préparer l'environnement

Installer et lancer une instance d'Elasticsearch et de Postman pour executer facilement des requêtes HTTP.

  - Elasticsearch : https://www.elastic.co/fr/
  - Postman : https://www.getpostman.com/

En python, vous aurez également besoin de la librairie https://elasticsearch-py.readthedocs.io/en/master/ :

```bash
pip install elasticsearch
```

## Exercice 2 : Chargement des données

Vous pouvez donc :
  - Écrire un script python (ou autre) pour charger les données de tous les livres du dossier `../data` dans Elasticsearch.
  - L'idée est d'avoir un document pour une phrase du livre.
  - Vous aurez besoin d'un index pouvant stocker la `langue`, le `titre` du livre, la `phrase` et pourquoi pas d'autres informations annexes comme la `date de parution`. Nous sommes dans une base NoSQL dans un environnement BigData, le stockage coûte peu donc n'ayez pas peur de dupliquer la donnée pour améliorer les performances en requête !

## Exercice 3 : Requête sur les données

Elasticsearch est très performant sur les requêtes des champs full-text.

Vous pouvez donc effectuer les requêtes suivantes pour tester :
  - Utiliser une requête Elasticsearch pour retourner toutes les phrases contenant le mot `Alice` dans le livre en `français` d'`Alice au pays des merveilles`.
  - Utiliser une requête Elasticsearch pour connaître le nombre de phrases contenant le mot `Lapin` dans le livre en `français` d'`Alice au pays des merveilles`.
  - Utiliser une requête Elasticsearch pour connaître les mots les plus représentés dans le livre en `anglais` du `Livre de la jungle`.
