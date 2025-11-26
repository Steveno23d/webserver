En allant sur :

http://192.168.1.87/?page=signin

<img width="1125" height="620" alt="image" src="https://github.com/user-attachments/assets/602a7420-a2da-445e-9c48-ed746dd75695" />

En inspectant la requête envoyée par le bouton "Login", on remarque que le site utilise une requête GET :

?page=signin&username=ADMIN&password=xxxx&Login=Login#


Donc les paramètres passent en GET, ce qui rend le bruteforce très simple.

Je crée un fichier :

wordlist.txt

<img width="728" height="300" alt="image" src="https://github.com/user-attachments/assets/11901926-52cd-4a6c-8306-6ddd1ed7a216" />

Écriture du script de bruteforce (brute.py)

Le script utilise requests et envoie les paramètres en GET, pas en POST

<img width="604" height="536" alt="image" src="https://github.com/user-attachments/assets/3b011a0e-0f1b-4d42-b904-90d0d4de61ca" />

on lance le script : python3 brute2.py

<img width="1045" height="655" alt="image" src="https://github.com/user-attachments/assets/f1f7796e-ae83-468c-9295-d0cb99551111" />

<img width="1167" height="540" alt="image" src="https://github.com/user-attachments/assets/e71cbcbf-cf2d-4cc1-996b-e095c29c94f8" />


