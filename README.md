# Création sauvegarde et restsauration d'un site Wordpress
-------------------------------------------

## Description générale
3 scripts ont été mis en place dans le cadre du projet 6 du Parcours Administrateur Infrastructure et Cloud d'Openclassroom. Ils permettent la création d'un site WordPress vierge, la sauvegarde incrémentale du site  et sa restauration à partir d'une sauvegarde récupérée pour retrouver un site fonctionnel.

Le but du projet est la mise en place d'une sauvegarde automatique afin de maintenir uns site en ligne et de limiter la perte de données en cas de problème physique sur le serveur. 

### Environnement de test
Les scripts shell ont été testé dans un environnement virtuel composé de machines virtuelles sous debian 10. L'infrastructure se compose de:
* un serveur Wordpress fonctionnel 
* un serveur vierge 
* un serveur FTP pour envoyer les sauvegardes

Une connexion Internet est néccessaire dans l'execution des scripts pour la récupération des paquets néccessaires

### Description des scripts

1.lamp_wp

2.backup_data_WP

3.restore_WP


Diverses action de configuration-création-administration de site WordPress
Mise en place de plusieurs script permettant les actions suivantes:
-Création et configuration  d'un serveur LAMP, configuration d'une base de donnée et installation de la dernière version de l'application Wordpress
-Sauvegarde des données et de la base de donnée d'un site WordPress, transfert sur serveur Ftp et rotation des sauvegardes
-Choix de la sauvegarde à restaurer transfert de cette dernière sur la machine exécutant le script. Restauration de la sauvegarde permettant de récupérer un site fonctionnel 
