# Création sauvegarde et restsauration d'un site Wordpress
-------------------------------------------


## Description générale
3 scripts ont été mis en place dans le cadre du projet 6 du Parcours Administrateur Infrastructure et Cloud d'Openclassroom. Ils permettent la création d'un site WordPress vierge, la sauvegarde incrémentale du site  et sa restauration à partir d'une sauvegarde récupérée pour retrouver un site fonctionnel.

Le but du projet est la mise en place d'une sauvegarde automatique afin de maintenir uns site en ligne et de limiter la perte de données en cas de problème physique sur le serveur. 

### Environnement de test
Les scripts shell ont été testé dans un environnement virtuel composé de machines virtuelles sous ##debian 10##. L'infrastructure se compose de:
* un serveur Wordpress fonctionnel 
* un serveur vierge 
* un serveur FTP pour envoyer les sauvegardes

Une connexion Internet est néccessaire dans l'execution des scripts pour la récupération des paquets néccessaires

### Description des scripts

Les droits en exécution doivent être appliqué sur le répertoire téléchargé pour rendre tous les scripts exécutables.
```
$ sudo chmod 755 -R /user/wp_action
```

1.lamp_wp

Le code mis en place dans le script lamp_wp permet d'effectuer les actions suivantes:
* Création et configuration  d'un serveur LAMP
*  Création et configuration d'une base de donnée  
*  Installation de la dernière version de l'application Wordpress

Le premier script permet la mise en place rapide d'un site WordPress Vierge. Il peut être utilisé pour la création rapide d'une base WordPress pour commencer à concevoir son site. En cas d'un crash du serveur Hébergeant un site WordPress, ce script peut être utilisé pour rapidement remettre en place un site et une base de données vierge avant de restaurer la sauvegarde souhaitée avec le script 

#### Exécution du script
```
$ sudo ./lamp_wp
```

2.backup_data_WP

Le code mis en place dans le script backup_data_WP permet d'effectuer les actions suivantes: 
* Sauvegarde des données et de la base de donnée du site WordPress hébergé sur le serveur sur lequel le script est exécuté. 
* Transfert de la sauvegarde sur un serveur FTP
* Rotation des sauvegardes sur une période de 31 jours

Le second script permet la sauvegarde des données et de la base de données du site WordPress. Il est possible de mettre en place une sauvegarde reccurente en faisant une planification cron

#### Exécution du script
```
$ sudo ./backup_data_WP
```

3.restore_WP

Le code mis en place dans le script restore_WP permet d'effectuer les actions suivantes: 
* Choix de la sauvegarde situé sur le serveur FTP à restaurer
* Transfert de la sauvegarde sur la machine exécutant le script et destiné à héberger le site WordPress. 
* Restauration de la sauvegarde permettant de récupérer un site fonctionnel 

Le troisième script permet la restauration des données et de la base de donnée via la sauvegarde effectuée.Cette restauration doit être effectué uniquement sur un serveur vierge avec le paquet LAMP et l'appication WordPress installés

#### Exécution du script
```
$ sudo ./restore_WP
```

### Cas d'utilisation

 




### Gestion des erreurs


