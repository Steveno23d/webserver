Découverte du cookie

En envoyant une requête simple :
curl -I http://192.168.1.87
Le serveur renvoie :
<img width="434" height="429" alt="image" src="https://github.com/user-attachments/assets/e2d51de8-2f73-4c37-b800-25eb00c1b792" />

Après analyse, on observe que le cookie ressemble à un hash MD5 :
<img width="362" height="126" alt="image" src="https://github.com/user-attachments/assets/5c972a17-c208-46da-b9b0-0888842510f7" />

On envoie une requête en définissant ce cookie :
<img width="515" height="108" alt="image" src="https://github.com/user-attachments/assets/a0c9417e-00ab-4c04-9ef3-11d3b4680c81" />



