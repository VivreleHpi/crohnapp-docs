# Sources cliniques

Échelles et scores utilisés dans l'application, avec leurs références et limites.

## Échelle de Bristol (Bristol Stool Form Scale)

- **Usage dans l'app** : classification des selles de type 1 à 7. Le type est affiché tel que
  saisi, et les saisies sont comptées par type, sans moyenne. Les commentaires et la mention d'une
  zone « normale » sont suspendus depuis la v1.2.6.
- **Référence** : Lewis SJ, Heaton KW. *Stool form scale as a useful guide to intestinal transit time.* Scand J Gastroenterol. 1997. PubMed : <https://pubmed.ncbi.nlm.nih.gov/9299672/>.
- **Limite** : outil descriptif auto-déclaré ; ne mesure pas l'inflammation.

## Index de Harvey-Bradshaw (HBI)

- **Usage dans l'app** : **calcul suspendu depuis la v1.2.6** (4 octobre 2026). Jusqu'à la
  v1.2.5, score Harvey-Bradshaw saisi à partir des réponses déclarées par l'utilisateur
  (bien-être, douleur, selles liquides, masse abdominale, complications), présenté comme repère
  indicatif de suivi. Les scores déjà enregistrés sont conservés dans le coffre et les
  sauvegardes.
- **Référence** : Harvey RF, Bradshaw JM. *A simple index of Crohn's-disease activity.* Lancet. 1980. PubMed : <https://pubmed.ncbi.nlm.nih.gov/6102236/>.
- **Formule, seuils, version et date de relecture** : documentés dans [hbi_calcul.md](hbi_calcul.md).
- **Limites** : score déclaratif, non substituable à une évaluation clinique.
- **Statut** : suspendu. Une relecture médicale versionnée par un gastro-entérologue et un avis
  réglementaire restent à obtenir avant de le rétablir.

## Signal de suivi (heuristique interne)

- **Usage dans l'app** : **suspendu depuis la v1.2.6** (4 octobre 2026). Il combinait sévérité
  déclarée, présence de sang et type Bristol.
- **Statut** : heuristique interne, **non validée cliniquement**. Les comptes sur lesquels elle
  reposait restent affichés tels que saisis, sans signal ni couleur dérivée d'un seuil.

## Cadres de référence produit

- HAS — Référentiel de bonnes pratiques sur les applications et objets connectés en santé (mHealth).
- CNIL — Recommandation relative aux applications mobiles.
- ANS — Référencement Mon espace santé (cible de moyen terme, non revendiquée aujourd'hui).
