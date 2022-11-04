## Pré-requis

Il est nécessaire d'avoir la dernière version de Ansible pour utiliser les rôles. 
Vous pouvez l'installer sur votre sous système Linux comme ceci : 

- Installation de pip : 

```
apt update && apt install python3-pip
```

- Installation de virtualenv : 

```
pip3 install virtualenv
``` 

- Créer un user dédié : 

```
adduser ansible
```

- Passer sur ce user et créer un environnement python :

```
su - ansible
virtualenv ansible
source ansible/bin/activate
```
