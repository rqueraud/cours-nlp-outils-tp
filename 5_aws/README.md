# Partie 5 : AWS

## Pré-requis

Vous pouvez dans un premier temps tester les services d'Amazon depuis la console AWS (l'interface web).

Pour accéder aux services par le biais de code, vous pouvez soit utiliser l'`aws-cli` en ligne de commande, soit utiliser [boto3](https://docs.aws.amazon.com/transcribe/latest/dg/getting-started-python.html) que vous pourrez installer via pip. Vous trouverez ensuite des exemples sur le [site](https://docs.aws.amazon.com/transcribe/latest/dg/getting-started.html) d'AWS.

Puisque vous allez utiliser le micro de votre ordinateur, le mieux est d'avoir votre environnement en local. Toutefois, si votre environnement python tourne sur une EC2, on peut imaginer mettre en place un service intermediaire pour l'envoi du fichier de son.

## Comprendre les services AWS

Tester les services **Transcribe** et **Polly** d'AWS.

  - [Transcribe](https://aws.amazon.com/blogs/machine-learning/amazon-transcribe-now-supports-real-time-transcriptions/) est le service de speech-to-text d'AWS et est depuis peu capable de gérer de la transcription en temps réél. Vous allez donc pouvoir appeler le service via l'api AWS
  - [Polly](https://eu-west-1.console.aws.amazon.com/polly/home/SynthesizeSpeech) est le service de text-to-speech d'AWS.

## Créer le robot

Incorporer le travail du premier TP avec les N-grams pour créer un jeu ou un utilisateur au micro complète les phrases d'un robot qui lui répond à l'oral.

Exemple : 

  - User :  Alice was beginning...
  - Bot :   Alice was beginning to get very...
  - User : Alice was beginning to get very tired of sitting...
  - Bot : Alice was beginning to get very tired of sitting by her sister...
  - ...

