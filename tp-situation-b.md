# Dépannage d'un poste de travail

[← Retour au portfolio (tp-camille.html)

*PME de conception de pièces mécaniques et d'outillages pour l'industrie, 25 postes, Site principal — septembre 2026 — option SISR*

## Contexte

Le site principal comporte un bureau d'études au sein duquel les ingénieurs réalisent les études et plans pour répondre aux appels d'offres des potentiels clients ou développer de nouvelles pièces.

## Problématique

Cela faisait environ 15 jours que l'on constatait un dysfonctionnement sur l'un des postes du bureau d'études. Le poste redémarrait entre 2 et 3 fois par jour faisant perdre tout le travail effectué et non sauvegardé.

## Démarche

Mon premier reflexe a été de consulter l'observateur d'évènements.
J'ai constaté la presence de "Kernel-Power 41", ce qui confirme bien que le poste s'arrête et redémarre sans suivre la procédure normale mais ne donne pas la cause exacte du problème.

J'ai d'abord voulu vérifier que le problème ne venait pas du système d'exploitation. J'ai fait toutes les mises à jour mais le problème persistait.

J'ai ensuite décidé de vérifier le bon fonctionnement de la RAM car un dysfonctionnement de celle-ci peut également entrainer un redémarrage intempestif. J'ai lancé un test de la mémoire vive durant la nuit mais celui-ci n'a détecté aucune erreur.

Pour finir, j'ai décidé d'ouvrir le poste pour observer les composants et détecter une autre source au problème. J'ai constaté une grande quantité de poussière dans l'alimentation du poste. J'ai donc décidé de mesurer la consommation à l'aide d'une prise Wattmétrique.
C'est la que j'ai constaté une consommation à la limite de la capacité maximale de l'alimentation. 310 W en point sur une capacité maximale de 350 W.
J'ai donc effectué un nettoyage du poste ainsi qu'un remplacement de l'alimentation par un modèle plus puissant avec une capacité de 550W.

## Outils mobilisés

- Observateur d'évènements → Constater la panne et faire un premier diagnostique
- Windows Update → Vérifier les mises à jours et mettre à jour le système d'exploitation
- Memtest86 → Tester le bon fonctionnement de la mémoire vive
- Prise Wattmétrique → Mesurer la consommation d'énergie du poste en temps réel.

## Précautions prises

Avant d'ouvrir le poste, j'ai pris soin d'éteindre complètement le poste puis de débrancher son alimentation et tous les périphériques.
J'ai aussi maintenu le bouton d'alimentation enfoncé quelques secondes après l'avoir débranché pour évacuer une partie de l'énergie résiduelle.
J'ai fait en sorte de d'ouvrir le boitier sur une surface propre et bien éclairée sans éléments pouvant produire de l'électricité statique à proximité.
 
## Résultats

Avec le remplacement de l'alimentation 350W par une alimentation 550W, pas un seul redémarrage intempestif n'a été constaté depuis 1 mois.

## Bilan personnel

Ce premier dépannage m'a permis de développer ma capacité à diagnostiquer une panne matérielle. J'ai recherché plusieurs causes possibles et procédé par élimination pour trouver l'origine du problème et le résoudre.
J'ai aussi développé ma connaissance du matériel utilisé par l'entreprise en intervenant directement dessus.
