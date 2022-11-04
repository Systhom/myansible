MariaDB
=========

Ce rôle permet d'installer de configurer MariaDB :

* Installation de MariaDB
* Configuration : listen 0.0.0.0
* Création de base de données, utilisateurs multiples .

Role Variables
--------------

Vous pouvez définir les variables suivantes dans roles/mariadb/vars/main.yml : 
Exemple: 
```
mariadb_databases:
  - db: "premieredb"
    user: "us_wordpress"
    password: "123456"
    host: "localhost"
  - db: "deuxiemedb"
    user: "deuxiemedb_user"
    password: "131241232131"
    host: "%"
```

Tout les droits seront donnés sur la base de données à l'utilisateur indiqué. 


Fonctionnement
----------------

Pour lancer le playbook, simplement lancer : ansible-playbook launch_mariadb.yaml

L'adresse IP, le username et le mot de passe vous seront ensuite demandés

Author Information
------------------

Thomas CAS
