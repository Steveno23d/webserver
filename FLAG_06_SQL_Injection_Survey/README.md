En arrivant sur la page /survey, j’ai observé un tableau présentant différents sujets, chacun accompagné d'un bouton permettant de leur attribuer une note.

<img width="458" height="628" alt="image" src="https://github.com/user-attachments/assets/1db65d78-4e2c-4f90-beba-d03c07e3a5fb" />


En inspectant l'interface (voir capture ci-dessous), j’ai remarqué que cliquer sur la note déclenche automatiquement l’envoi du formulaire.

Cela suggère que la fonction JavaScript this.form.submit() est exécutée, ce qui indique que la page utilise une requête POST pour transmettre la note au serveur.

L’analyse du code HTML confirme que :

<select name="valeur" onChange="javascript:this.form.submit();">


Le formulaire POST envoie donc deux paramètres :

sujet → l’identifiant du sujet

valeur → la note attribuée

Aucune validation n’empêche d’envoyer une valeur anormale (ex : 9999).
J’ai donc reproduit la requête POST avec curl, et en envoyant une valeur hors limites (9999), le serveur m’a retourné le flag.

<img width="917" height="596" alt="image" src="https://github.com/user-attachments/assets/a096af7d-3b94-4b9c-8e38-16d2fe1ecf34" />

