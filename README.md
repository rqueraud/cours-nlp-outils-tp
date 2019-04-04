# Cours YNOV - Les outils pour le NLP - 05/04/19

L'objectif de ce cours est de présenter les différents outils pour le NLP.  
Deux cours préliminaires ont déjà eu lieu, présentés par Clément. Le premier constituait une introduction théorique sur le NLP, le second une approche plus pratique sur les algorithmes utilisés dans SpaCy et Stanford ainsi que les approches word2vec et clustering.

Ce cours propose une série une série d'exercices à trou sous la forme de notebooks jupyter. Pour lancer les notebooks, il convient d'avoir un environnement `python` avec le module `pipenv` installé. `pipenv` permet de lancer un environnement virtuel python avec les dépendances définies dans le fichier `Pipfile`.

## Pré-requis : Préparer son environnement

Si vous n'avez pas d'environnement python, vous pouvez utiliser une machine virtuelle sur AWS.

Pour cela, aller sur le service EC2 et lancer une nouvelle instance **m5.large** avec **Ubuntu 18.04** ou une autre distribution Linux si vous préférez. Récupérer la clé pour l'accès SSH et connectez-vous à l'instance.

Sur l'instance, installez python, pip et pipenv :
```bash
sudo apt-get update && sudo apt-get upgrade -y

sudo apt-get install -y python3-pip python3-dev
pip3 install --user pipenv
echo "PATH=$HOME/.local/bin:$PATH" >> ~/.bashrc
source ~/.bashrc
```

Que vous soyez sur une EC2 ou en local sur votre machine, une fois votre environnement `python` et `pipenv` installé, pour lancer l'outil, ouvrir un terminal puis :
```bash
git clone this-project
cd this-project-folder
pipenv install
pipenv run jupyter-notebook  # This should open jupyter in your web browser
```

Si vous êtes sur une EC2, vous allez devoir autoriser l'accès à distance pour jypyter. Pour cela ouvrez le port **8888** dans les security-group sur la console AWS pour pouvoir vous connecter à jupyter. Vous allez également devoir configurer jupyter sur l'instance pour qu'il autorise la connection à distance :
```bash
pipenv run jupyter-notebook --generate-config
pipenv run nano /home/ubuntu/.jupyter/jupyter_notebook_config.py

# Puis changer et décommenter les lignes suivantes :
    c.NotebookApp.allow_origin = '*'
    c.NotebookApp.ip = '0.0.0.0'
    c.NotebookApp.token = ''

# Vous pouvez maintenant redémarrer le notebook et vous connecter depuis votre navigateur sur le port 8888
pipenv run jupyter-notebook
```

## Exercice 1 : Géneration de texte

Cet exercice constitue un échauffement à python. Nous allons utiliser NLTK pour générer les trigrams et calculer les probabilités associées à chaque combinaison de mots.

A partir de 3 mots de départ, nous allons ensuite génerer automatiquement un texte.


## Exercice 2 : Classification de texte

Nous allons utiliser quelques outils NLTK vus le matin, cette fois-ci pour le découpage des phrases.

Nous allons ensuite enlever tous les diacritiques des phrases, compter les lettres la composant, visualiser les données et entrainer un modèle de Machine Learning pour la classification de langue.


## Exercice 3 : Pytorch

Plusieurs TPs pris sur le site de Pytorch : 

  1. Une introduction aux Tensors.
  2. Une introduction aux Réseaux de Neurones avec les words_to_index, la création d'un layer non-linéaire, l'utilisation d'une fonction de loss et la création/entrainement d'un classifier pour les langues.
  3. *Bonus* : N-grams avec plusieurs layers.


## Exercice 4 : OCR

Nous allons installer (Tesseract)[https://github.com/tesseract-ocr/tesseract] et tester sur différentes versions du texte d'Alice.

## Exercice 5 : AWS

Les vidéos de présentation des différents services : https://www.aws.training/

  - Transcribe pour le speech-to-text
  - Polly pour le text-to-speech
  - Comprehend pour l'analyse de texte
  - Lex pour le chatbot

## Exercice 6 : Elasticsearch

Elasticsearch est une base pour stocker et indexer des données full-text de manière efficace.
