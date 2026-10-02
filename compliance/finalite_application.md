# Finalité de l'application

## Ce que fait CrohnApp

CrohnApp est un **carnet de suivi personnel** pour les personnes vivant avec une maladie
de Crohn ou une MICI. Il permet de :

- Consigner les selles (échelle de Bristol, sang, mucus), les symptômes et le suivi des prises
  déclarées des traitements.
- Visualiser des tendances simples et explicables (fréquence, sévérité, prises renseignées).
- Générer une **synthèse des données déclarées pour la consultation** (PDF), avec un indicateur
  de complétude signalant si les saisies sont suffisantes pour être exploitables.
- Exporter ses données : CSV et JSON lisibles, sauvegardes chiffrées du carnet et des photos,
  graphiques en PNG, et préparer un dépôt manuel de la synthèse dans **Mon espace santé**.

## Ce que ne fait pas CrohnApp

- **Pas de diagnostic** ni d'évaluation d'urgence automatique.
- **Pas de recommandation thérapeutique** ni d'ajustement de traitement.
- **Pas de prédiction de poussée**.
- **Pas de score clinique calculé** ni de signal dérivé de seuils : ces fonctions sont suspendues
  (voir ci-dessous).
- Pas d'envoi automatique vers Mon espace santé ou le DMP (l'application n'est pas référencée
  au catalogue Mon espace santé).

## Fonctions suspendues

Depuis la v1.2.6 (4 octobre 2026), trois fonctions sont suspendues dans l'attente d'une relecture
médicale et réglementaire :

- le calcul du score Harvey-Bradshaw (HBI) — voir [hbi_calcul.md](hbi_calcul.md) ;
- le « signal de suivi », qui appliquait des seuils internes aux saisies, avec les repères qui en
  dérivaient à l'accueil, dans les analyses et dans le PDF ;
- les commentaires et la mention d'une zone « normale » sur l'échelle de Bristol.

L'application restitue ce qui a été saisi : comptes, répartitions, graphiques et tableaux. Les données
déjà enregistrées, scores HBI compris, sont conservées dans le coffre et dans les sauvegardes.

## Statut

Application de suivi personnel. **Non revendiquée comme dispositif médical** ; elle n'a pas
encore fait l'objet d'une étude clinique destinée à démontrer son efficacité. La synthèse PDF
est un résumé de données déclarées par l'utilisateur, destiné à préparer une consultation ;
son interprétation relève d'un professionnel de santé.

Toute évolution de la destination d'usage ou des fonctionnalités, notamment l'analyse
individualisée, les alertes cliniques, la prédiction ou l'aide à la décision, devra faire
l'objet d'une nouvelle analyse réglementaire.
