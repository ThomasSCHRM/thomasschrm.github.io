# Développement d'une application de suivi des commandes pour l'administration des ventes

[← Retour au portfolio] (index.html)

*PME - Service administration des ventes - janvier 2026 - option SLAM*

## Contexte

Janvier, dans la PME dans laquelle j'effectue mon alternance, le service administration des vente suivait ses commandes clients à l'aide d'un fichier Excel situé sur un serveur partagé. C'est un fichier de 12 Mo mis en place il y a 6 ans et sur lequel travaillaient les trois personnes du service ADV pour y enregistrer la quarantaine de commandes hebdomadaires des clients.

## Problématique

Le problème avec cette façon de fonctionner c'est que les trois personnes du services ne pouvaient pas écrire en même temps sur le document. L'ouverture du fichier par plus d'une personne entrainait la création de doublons dans le serveur et c'est une situation qui pouvaient se présenter environ 3 fois par semaine.

A cause de ces doublons, il est arrivé à plusieurs reprises que des commandes soient enregistrées en double ou soient perdues.
Le mois précédent ma mission, 2 commandes avaient été saisies en double et une autre avait disparu.

La responsable du service administration des vente m'a demandé si je pouvais trouver une solution à ce problème sans avoir à changer tout le systèmes de gestion.

## Démarche

J'ai commencé par une phase d'observation d'une demi-journée pour connaitre leur façon de travailler. J'ai pris notes de leurs habitudes d'utilisation, les manipulations quotidiennes réalisées, les champs utilisés sur le fichier et ceux qu'elle ne remplissaient jamais.

Après cette phase d'observation j'ai envisagé 3 options:

- Option 1 : Garder le fichier Excel en le mettant en lecture seule pour deux personnes sur trois
- Option 2 : Acheter un module de gestion commerciale chez le même éditeur que le logiciel comptable
- Option 3 : Développer une petite application interne

La première option n'engendrait aucun coûts et réglait les problèmes de doublons et de commandes disparues mais reportait l'intégralité du travail de saisie sur une seule des trois personnes du service. J'ai donc décidé de ne pas retenir cette option.

La deuxième option était la solution la plus aboutie techniquement mais comportait trop d'inconvénients et a donc été écartée également:
- coût de 3500€ avec un abonnement en plus
- un délai de 3 mois pour le déploiement
- La facturation de la reprise des données depuis le fichier Excel
C'est surtout le critère du délai qui m'a poussé à écarter cette solution car il était urgent de résoudre le problème des doublons de commandes.

J'ai donc opté pour la troisième option.
J'ai développé une application interne composée d'une base de données MySQL et d'une formulaire  web de saisie.
Grâce à cette solution le formulaire de saisie est accessible depuis 3 postes en simultané, avec la liste des commandes filtrable, sans risque de doublons.

## Outils mobilisés

- PHP 8.2 → Langage utilisé pour programmer l'application
- MySQL → Logiciel utilisé pour la base de donnée
- XAMPP → Logiciel utilisé pour développer et tester l'application avant mise à disposition au service ADV
- Script d'import → Petit programme utilisé pour transférer automatiquement les 1850 commandes du fichier Excel vers la nouvelle base de données.

## Précautions prises

- Création d'une copie du fichier Excel d'origine et l'ai laissé en lecture seule dans un dossier d'archive pour sécuriser les données et pouvoir revenir en arrière si ma solution était rejetée par le service ADV.
- Tests à trois reprises du bon fonctionnement du script d'import sur une base de test avant utilisation sur la vraie base.
- Mise en place une sauvegarde automatique quotidienne de la base de données qui s'effectue chaque nuit pour ne pas perturber son utilisation en journée.
- Validation des libellés des champs par la responsable ADV avant finalisation du formulaire.
- L'accès au document a été limité aux trois comptes concernés pour la protection des coordonnées des clients
- Aucun export n'est sorti de l'entreprise tout au long du processus y compris pour les tests.

## Résultats

Depuis la bascule vers cette application, plus aucun conflit de version ne s'est produit en dix semaines et plus aucun doublon de commande n'a été constaté.
Le temps de saisie d'une commande a aussi été amélioré en passant d'environ 4 minutes à 1 minute 30 grâce à un système de liste mis en place pour la sélection du client et du produit.
Cette mission m'a demandée 22 heures de travail étalées sur 5 semaines.

## Bilan personnel

Cette mission m'a permis d'apprendre à observer avant d'agir. J'allais commencer à développer mon application immédiatement, car je pensais déjà savoir quelle solution mettre en place. Pourtant, ma demi-journée d'observation m'a permis de mieux comprendre les besoins des futurs utilisateurs et d'adapter ma solution.
J'ai aussi pris conscience de l'importance de tester une application avant de l'utiliser en situation réelle grâce à un incident lors du premier essai sur le fichier Excel. Une quinzaine de lignes avaient disparues lors du transferts.

