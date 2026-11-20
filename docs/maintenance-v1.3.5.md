# Note de maintenance — CrohnApp v1.3.5

*Version publiée le 19 novembre 2026. La version installée se lit dans **Profil**.*

Dans le cadre de la maintenance régulière de CrohnApp, une campagne de vérification et de mise à
jour de plusieurs composants logiciels a été menée à la suite de notifications de sécurité et de
maintenance.

Cette intervention a permis d'actualiser les composants concernés tout en vérifiant la
compatibilité avec les carnets et les sauvegardes existants. Les fonctions de suivi personnel
restent inchangées : la version 1.3.5 n'en ajoute ni n'en retire aucune.

Ce travail s'inscrit dans une démarche continue de qualité, de fiabilité et de transparence. La
documentation publique est actualisée en même temps, pour aider chacun à comprendre les
évolutions, le fonctionnement et les limites de CrohnApp.

## Ce qui a été fait

CrohnApp s'appuie sur des composants tiers, ainsi que sur des outils qui servent à la préparer et
à la vérifier. Des notifications automatiques signalent lorsqu'une faiblesse est connue dans l'un
de ces composants publics, utilisés par de nombreux logiciels. Une notification décrit une
faiblesse possible d'un composant, pas un incident survenu sur CrohnApp.

Les notifications reçues ont été examinées, puis traitées par des mises à jour contrôlées. Ces
mises à jour ont été menées par étapes, et chaque étape a été vérifiée séparément. Au
19 novembre 2026, aucune notification ne restait ouverte (état daté). Aucun incident n'a été
constaté sur CrohnApp.

## Comment la version a été vérifiée avant publication

- Tests automatisés de l'application.
- Parcours complets dans un navigateur, sur ordinateur et en affichage mobile.
- Fonctionnement hors ligne de l'application installée.
- Ouverture de carnets créés avec des versions antérieures, photos comprises.
- Restauration de sauvegardes chiffrées créées avec une version antérieure.
- Sur un carnet d'essai, retour à la version précédente puis à la nouvelle, sans perte.
- Après publication, contrôle que le site sert bien la version vérifiée.

Les essais ont porté uniquement sur des données fictives.

## Ce qui ne change pas

- Vos carnets, le coffre chiffré et les photos.
- Les formats de sauvegarde et la restauration.
- Le fonctionnement local : aucune donnée de santé ne quitte l'appareil sans une action de votre
  part (export, sauvegarde, PDF, partage).
- Les fonctions de suivi : selles, symptômes, traitements, analyses, synthèse PDF et exports.

## Que faire de votre côté ?

Rien de particulier. La mise à jour s'installe comme les précédentes : voir
[Mettre à jour CrohnApp](guides/mise-a-jour-pwa.md).

Comme toujours, conservez une sauvegarde récente de votre carnet et, si vous avez des photos,
une sauvegarde des photos : voir [Créer et restaurer une sauvegarde chiffrée](guides/sauvegarder-restaurer.md).

## Limites de cette note

Cette note décrit un état daté. Elle ne constitue ni une certification ni un audit de sécurité
indépendant. Le suivi des composants tiers est une partie de la maintenance de sécurité : il ne
remplace ni une revue complète du code ni un audit indépendant, qui reste à réaliser. De nouvelles
notifications peuvent apparaître après la publication ; elles seront examinées de la même façon.

Le suivi des dépendances est décrit dans [Gestion des dépendances](gestion-dependances.md), et
l'historique des versions dans le [journal des changements](../compliance/journal_changements.md).
Pour une question précise : [crohnapp@gmail.com](mailto:crohnapp@gmail.com).
