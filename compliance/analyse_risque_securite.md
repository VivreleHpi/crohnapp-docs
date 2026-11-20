# Analyse de risques — sécurité et santé

Chaque risque identifié est associé à une mesure de réduction. Analyse initiale du 13 août 2026 ;
mise en cohérence documentaire le 14 novembre 2026 (v1.3.4), puis le 20 novembre 2026 pour
**CrohnApp v1.3.5**.

> **Portée** : relecture interne des mesures décrites et des vérifications disponibles. Elle ne
> constitue ni une analyse exhaustive des risques, ni une validation clinique ou juridique,
> ni un audit de sécurité indépendant.

## Risques techniques

| Risque | Impact | Mesure de réduction | Statut |
|---|---|---|---|
| Perte des données locales (effacement navigateur, perte d'appareil) | Perte de l'historique | Sauvegardes chiffrées du carnet et des photos, restaurables, avec rappel dans l'application | En place |
| Accès physique à l'appareil par un tiers | Lecture des données de santé | Carnet et photos chiffrés, reverrouillage après rechargement, verrouillage de l'appareil | En place |
| Import d'un fichier de sauvegarde corrompu ou malveillant | Corruption des données | Contrôle du contenu à l'import et confirmation explicite avant tout remplacement | En place |
| Suppression accidentelle | Perte définitive | Double confirmation avec saisie du mot SUPPRIMER | En place |
| Dépendances vulnérables | Compromission de l'application ou de son outillage | Versions verrouillées, suivi des avis, examen des alertes et mises à jour vérifiées ; application et outillage suivis distinctement | Suivi continu ; aucune alerte connue ouverte au 19 novembre 2026 (état daté) |

## Risques santé (les plus importants)

| Risque | Impact | Mesure de réduction | Statut |
|---|---|---|---|
| L'utilisateur croit à un diagnostic automatique | Retard de prise en charge | Disclaimer permanent, aucune formulation diagnostique, page Qualité & sécurité | En place |
| Rapport interprété comme donnée médicale vérifiée | Décision fondée sur des données déclaratives | Titre « Synthèse des données déclarées pour la consultation » sur le PDF, mention qu'il ne constitue ni un dossier médical ni un diagnostic, et encadré « Limites de lecture » | En place |
| Absence de saisie interprétée comme absence de symptôme | Sous-estimation | Encadré « Limites de lecture » dans le PDF, indicateur « Complétude des saisies » (jours renseignés sur la période), aucun jour sans saisie affiché comme un zéro | En place |
| Urgence non détectée par l'application | Danger vital | L'app ne fait aucun triage ; numéros d'urgence (15/112) rappelés dans le PDF | En place |
| Score HBI mal calculé ou mal compris | Mauvaise appréciation | Calcul suspendu dans l'application depuis la v1.2.6 ; relecture médicale à obtenir avant de le rétablir | Suspendu |
| Seuil interne lu comme une évaluation médicale | Fausse réassurance ou inquiétude injustifiée | Signal de suivi, couleurs dérivées d'un seuil et commentaires sur l'échelle de Bristol suspendus depuis la v1.2.6 ; seuls les comptes saisis sont affichés | Suspendu |
| Perte du mot de passe du coffre ou d'une sauvegarde | Perte définitive de l'accès | Avertissement explicite : aucune récupération n'est possible, ni localement ni à distance | En place |

## Limites assumées

Un audit de sécurité indépendant n'a pas encore été réalisé, et la relecture clinique par un
professionnel reste à obtenir. Ces deux points sont des conditions préalables à un usage élargi,
pas des cases déjà cochées.

Un contrôle de dépendances limité à l'application ne couvre pas tous les outils de construction
et de test. Les résultats et leurs limites sont décrits dans la
[gestion des dépendances](../docs/gestion-dependances.md) ; une alerte d'outillage n'est pas
considérée sans risque du seul fait qu'elle ne concerne pas un paquet déclaré pour l'application.

## Ce qui déclencherait une nouvelle analyse

- Tout ajout de backend ou de synchronisation cloud.
- Toute fonction d'interprétation automatique (IA, prédiction, alerte).
- Tout échange automatisé avec Mon espace santé ou un système tiers.
