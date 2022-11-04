Apache2
=========

Ce rôle permet d'installer et de configurer apache2 : 

* Installation d'apache2
* Configuration : logrotate, servername
* Création de vhosts multiples 

Role Variables
--------------

Vous pouvez définir les variables suivantes dans roles/apache2/vars/main.yml : 

```apache2_vhosts:
# servername : nom de domaine
# ssl : création du vhost en https également (c'est le ssl snakeoil qui est mis) 
# redirect : ajout de la redirection http => https 
# extra_parameters : ajout de paramètres supplémentaires dans le vhost
  - servername: test.ansible.com
    ssl: True
    redirect: True
    extra_parameters: ""
  - servername: test2.ansible.com
    ssl: True
    redirect: True 
  ```

```
#Permet d'indiquer quel module apache2 vous souhaitez activer
apache2_modules:
  - module: ssl
  - module: rewrite
  ```

Fonctionnement
----------------

Pour lancer le playbook, simplement lancer : ansible-playbook launch_apache2.yaml

Author Information
------------------

Thomas CAS
