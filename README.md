# `TIC TAC TOE`

En partant du framework React nous avons progressivement intégrer les éléments fonctionnels de l’application Tictactoe et mis en place un système de déploiement automatique via jenkins en suivant les contraintes du CI/CD.

## `Contributeurs:`

**GASSAMA Adama**

**DIALLO Souleymane**

**CONTE Kankou** 


## `Stack Utilisés:`

    •   REACT est le framework dans lequel le projet est réalisé. 

    •	Jenkins est responsable du build vers un dossier local qui sera la simulation de notre dossier de production.

    •	Git est responsable du versionning du projet.

    •	GitHub héberge le Repo de notre projet.


## `Étape 1: Set up de repository`

Pour ce projet 

    •	Nous avons initialisé un nouveau Repo Git avec un projet React vide

    •	Nous avons ajouté tous les contributeurs nécessaires au projet


## `Étape 2 : Création des Branches`

Dans le cadre d’une intégration en continue :

    •	Notre stratégie est de mettre en place un Repo git avec une branche principale appelé `main ` qui est géré par l’intégration manager

    •	 Ensuite nous avons crée une seconde branche `develop` qui est la branche sur laquelle chaque contributeur tirera un topic pour chaque feature (nouvelle fonctionnalité), pour la fixation de chaque bug, pour le factoring du code et pour la documentation

    •	 Dans le respect de la méthodologie Agile, imaginons dans le futur d’autres collaborateurs rejoignent notre équipe de développeurs, l’intégration Manager leurs donneront accès à la branche `develop` et ils pourront créer leurs topics sans pour autant toucher la branche `main` 


## `Étape 3 : Ajout de la première fonctionnalité`


Comme demander dans le TP,

    •	Nous avons commencé à mettre en place les premières fonctionnalités du tutoriel tictactoe

    •	Pour le déploiement, un développeur met en place le code et le publie

    •	L’intégrateur manager valide selon les règle mises en place


## `Étape 4 : Configuration Jenkins et connexion avec git`

Pour la mise en place des pipelines dans Jenkins, nous avons procéder en plusieurs étape

**1 - Installation Jenkins :**

    •	Télécharger le fichier War se trouvant sur le site de Jenkins

    •	Installer java et vérifier la version

**2 - Couplage Jenkins et notre Repo Git**

    •	Nous avons créé un Personnal Acces Token pour la génération de nos futures clés publiques et privées

    •	Nous avons configuré notre Jenkins Administer en création notre crédentiel

    •	 Ajouter les informations (nom et url) de notre repo git dans la section gitHub de Jenkins

**3 - Création de notre pipeline**

En fonction de besoin, nous avons mis en place un script avec 3 stages

    •	Build: ce stage contient les informations nécessaires pour le build de notre projet 

    •	Deploy to Production : ce stage crée un dossier production et y ajoute le contenu de tous les fichiers du dossier build.

    •	Notification : ce stage contient le message de notification dans le cas où le déploiement se passe avec succès et crée un tag à la fin


## `Testing`

Dans le cadre du CI/CD, nous avons mis en place un sytème de testing