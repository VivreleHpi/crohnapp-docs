# Calcul du score Harvey-Bradshaw Index (HBI)

> Version du calcul HBI : 1.0.0 (indépendante de la version produit CrohnApp)
> Dernière relecture : 2026-07-16 (relecture interne, non médicale — une relecture par un
> gastro-entérologue reste à planifier avant toute revendication clinique)
> Statut dans l'application : **calcul suspendu depuis la v1.2.6** (4 octobre 2026)

## Statut

**Depuis la v1.2.6, le calcul du score HBI est suspendu dans CrohnApp**, dans l'attente d'une
relecture médicale et réglementaire. L'application ne propose plus le calculateur et n'affiche
plus ni score ni repère : ni à l'accueil, ni dans la synthèse, ni dans le PDF, ni dans le texte
de partage.

Les scores déjà enregistrés ne sont pas effacés. Ils restent dans le coffre et continuent d'être
inclus dans les sauvegardes ; seul leur affichage est suspendu.

Ce document conserve la formule telle qu'elle était appliquée jusqu'à la v1.2.5. Le score était
alors **calculé à partir des données déclarées par l'utilisateur** et présenté comme un repère de
suivi. Il ne permettait pas, à lui seul, de confirmer une poussée, une rémission ou l'activité
inflammatoire de la maladie. Aucune conclusion automatique (rémission, poussée, stabilité,
sévérité, urgence, efficacité d'un traitement) n'était produite par l'application.

## Source

- Harvey RF, Bradshaw JM. *A simple index of Crohn's-disease activity.* The Lancet,
  1980;315(8167):514. PubMed : <https://pubmed.ncbi.nlm.nih.gov/6102236/>.

C'était la référence liée depuis l'application, sur l'écran de calcul du score.

## Formule appliquée jusqu'à la v1.2.5

Somme de cinq composantes, telles que déclarées par l'utilisateur pour les dernières 24 h :

| Composante | Valeurs possibles |
| --- | --- |
| 1. Bien-être général | 0 (très bien) à 4 (terrible) |
| 2. Douleurs abdominales | 0 (aucune) à 3 (sévère) |
| 3. Nombre de selles liquides sur 24 h | 1 point par selle liquide (pré-rempli à partir des selles Bristol 6-7 saisies sur 24 h, modifiable avant validation) |
| 4. Masse abdominale | 0 (aucune) à 3 (définie et douloureuse) |
| 5. Complications actives | 1 point par complication cochée (arthralgie, uvéite/iritis, érythème noueux, pyoderma gangrenosum, aphtes, fissure anale, nouvelle fistule, abcès) |

`score = bien_être + douleur + selles_liquides + masse + nombre_de_complications`

## Seuils de repère (non affichés depuis la v1.2.6)

Le calcul et les bandes de repère provenaient d'une source unique dans l'application, afin que
l'écran de calcul, le tableau de bord et la synthèse affichent toujours la même valeur. Les
libellés étaient volontairement non diagnostiques :

| Score | Libellé affiché |
| --- | --- |
| < 5 | Repère HBI faible |
| 5 à 7 | Repère HBI intermédiaire |
| 8 à 16 | Repère HBI élevé |
| > 16 | Repère HBI très élevé |

Ces bandes reprennent les seuils usuels décrits dans la littérature pour le HBI, mais sont
présentées comme des repères de discussion, jamais comme rémission/poussée.

## Historique des versions

| Version | Date | Changement |
| --- | --- | --- |
| 1.0.0 | 2026-07-16 | Documentation initiale de la formule, des seuils et des libellés non diagnostiques. |

La formule n'a pas changé depuis. Le 13 août 2026, le calcul et les bandes ont été regroupés dans
une source unique côté application et couverts par des tests de valeur, afin d'écarter tout risque
de divergence entre les écrans. Le score affiché est resté inchangé.

Le 4 octobre 2026, avec la v1.2.6, le calcul a été suspendu dans l'application. La formule n'a pas
été modifiée et les scores enregistrés sont conservés.
