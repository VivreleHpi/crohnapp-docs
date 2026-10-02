# Statut dispositif médical et frontières à ne pas franchir

## Statut actuel

CrohnApp est un **carnet de suivi personnel**, non revendiqué comme dispositif médical.
Sa qualification réglementaire doit être confirmée par un conseil juridique et réglementaire avant
toute mise sur le marché.

Depuis la v1.2.6 (4 octobre 2026), le calcul du score HBI, le signal de suivi et les commentaires
sur l'échelle de Bristol sont suspendus dans l'attente d'une relecture médicale et réglementaire.
Aucun d'eux n'a été validé cliniquement.

## Fonctions actuelles compatibles avec ce statut

- Journal de selles, symptômes et traitements.
- Statistiques descriptives (comptes, répartitions par type et par intensité, graphiques). Aucune
  moyenne de l'échelle de Bristol ou de l'intensité n'est affichée, et un jour sans saisie n'est
  jamais affiché comme un zéro.
- Rapport PDF de synthèse « données déclarées par le patient » avec score de qualité de saisie.
- Exports contrôlés par l'utilisateur.

## Fonctions qui feraient basculer vers le statut de dispositif médical

À ne PAS implémenter sans analyse réglementaire dédiée. La qualification et la classe éventuelles
dépendraient de la destination revendiquée et ne peuvent pas être déterminées par cette seule
documentation :

- Diagnostic ou suggestion de diagnostic (« vous êtes en poussée »).
- Recommandation ou modification de traitement.
- Triage d'urgence automatique (« vous pouvez attendre » / « consultez immédiatement »).
- Prédiction de poussée ou score de risque présenté comme fiable.
- Alerte clinique automatisée adressée à un professionnel de santé.

## Règles de rédaction dans l'application

- Toute synthèse est formulée comme un **constat de données déclarées**, jamais comme un avis.
- Aucun score, signal ni commentaire de norme n'est affiché tant que les fonctions correspondantes
  sont suspendues. Les comptes sont restitués tels que saisis, sans signal ni couleur dérivée d'un
  seuil.
- Le disclaimer médical est permanent et le PDF rappelle les numéros d'urgence (15 / 112).
- La France est le seul pays activé, et l'application n'est proposée qu'en français. Toute ouverture
  d'un nouveau pays est bloquée jusqu'à la revue juridique et clinique définie dans
  [international-rollout.md](../docs/international-rollout.md).
