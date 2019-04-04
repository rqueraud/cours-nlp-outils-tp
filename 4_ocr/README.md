# Partie 4 : OCR

L'objectif de l'OCR est d'extraire le texte d'une image. Nous allons utiliser cette technique pour extraire le texte de la première page du livre d'Alice.

## Installer Tesseract 

(Tesseract)[https://github.com/tesseract-ocr/tesseract] est probablement l'outil open-source le plus abouti en ce qui concerne l'OCR.

Vous pourrez trouver le code source et les instructions d'installation à l'adresse suivante : https://github.com/tesseract-ocr/tesseract/wiki.


## Tester sur des images de livres

Vous pouvez tester d'extraire le texte des images, dans l'ordre :

  - alice_text.jpg
  - alice_text_low.jpg : Le retour de Tesseract sera de mauvaise qualité si vous n'avez pas la dernière version !
  - alice_handwriting.jpg

## Tester sur des images plus complexes

Le cas d'usage que nous avons ici est basique et les images de plutôt bonne qualité. On peut imaginer d'autres cas d'usages où nous souhaitons, en plus d'extraire le texte, extraire certaines propriétés associées comme sa position ou l'inclinaison.

Testez l'outil sur l'image `excel.jpg` et reconstituez les lignes de données.
