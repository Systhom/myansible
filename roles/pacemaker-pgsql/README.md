Pacemaker-pgsql
=========

Ce rôle permet de déployer un cluster PostgreSQL avec Corosync Pacemaker. (Failover + failback) 



Role Variables
--------------

Il faut définir dans roles/pacemaker-pgsql/vars/main.yml, les variables suivantes : 


```
---
corosync_clustername: "<nom du cluster>"
corosync_node1_hostname: "<hostname du master>"
corosync_node2_hostname: "<hostname du slave>"

vip_config:
  - vip: <adresse ip privée de l'ip flottante>
    int: <nom de l'interface réseau qui accueillera l'ip flottante> (ex: eth0)
    netmask: <masque réseau de l'ip flottante> (ex: 24)

postgres_version: <version majeur de postgres> (ex: 11)
postgres_vip: <adresse IP sur lequel postgres écoutera (ip flottante)>
```

Il faudra ajouter la clé SSH de votre utilisateur sur les 2 nodes.
Définir un fichier inventory.ini contenant : 

```
[cluster]
node2   ansible_port=22 role=slave ip_internal=<ip privée du slave> ansible_user=root
node1   ansible_port=22 role=master ip_internal=<ip privée du master> ansible_user=root
```
/!\ Il faut conserver les noms node1 et node2, il faut donc ajouter node1 et node2 pointant sur les IPs publiques dans votre fichiers hosts /!\

Dependencies
------------

Ne fonctionne qu'avec PostgreSQL =< 11


Example Playbook
----------------

```
ansible-playbook launch_pacemaker-pgsql.yml -i inventory.ini
```


Author Information
------------------

Thomas CAS
