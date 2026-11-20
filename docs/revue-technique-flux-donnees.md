# Revue technique interne des flux de données — CrohnApp

*Analyse initiale du 13 août 2026 sur v1.1.0 ; relecture interne mise à jour le 14 novembre 2026
pour CrohnApp v1.3.4, confirmée le 20 novembre 2026 pour v1.3.5, version de maintenance qui ne
change ni les chemins de stockage, ni les exports, ni la mesure d'audience.*

La relecture porte sur les chemins de stockage, d'export et de mesure d'audience du code de cette
version. Un contrôle du chargement de l'accueil en production confirme aussi la présence du
script de mesure d'audience. Il ne constitue pas une analyse exhaustive du trafic de tous les
parcours ni un examen de données de santé réelles.

> **Ceci n'est pas un audit indépendant.** Ce document est une revue interne réalisée pour
> le projet. Aucune société d'audit, aucun auditeur externe et aucun rapport signé ne sont
> associés à ce travail. Un audit de sécurité externe reste à réaliser ; c'est une étape
> identifiée, pas une case cochée.

Il répond à une question simple : est-ce que l'application envoie quelque chose quelque part ? Il
est écrit pour être lisible sans compétence technique. Le code source reste privé ; une lecture
peut être accordée sur demande motivée à [crohnapp@gmail.com](mailto:crohnapp@gmail.com).

Ce document publie la méthode, les constats et les limites de la revue. Les relevés détaillés qui
l'appuient (extraits de code, commandes, journaux de vérification) sont conservés dans le dossier
technique privé du projet.

## Ce qui a été cherché

- des outils de mesure d'audience ou de suivi (statistiques, publicité, profilage) ;
- des services de rapport d'erreur automatique ;
- des ressources chargées depuis d'autres sites (polices, scripts) ;
- des envois de données vers un serveur, quel qu'il soit ;
- des données de santé qui se glisseraient dans une adresse web ou un journal technique.

## Ce qui a été constaté

| Sujet | Constat |
| --- | --- |
| Mesure d'audience | Vercel Web Analytics est prévu et chargé sur le domaine de production pour une liste de pages publiques autorisées. Aucun suivi des actions ou du contenu du carnet n'est prévu. |
| Publicité et profilage clinique | Aucun cookie publicitaire, rejeu de session ou événement clinique personnalisé intégré à cette mesure. |
| Rapport d'erreur automatique | Aucun service de ce type n'est utilisé. |
| Polices et ressources de l'application | Les polices sont fournies avec l'application ; aucun service distant de polices n'est nécessaire. |
| Échanges réseau | Chargement des fichiers du site et mesure d'audience publique. Aucun mécanisme de téléversement automatique du carnet ou des photos repéré dans le périmètre relu. |
| Adresse de page envoyée à la mesure d'audience | Limitée aux routes publiques autorisées ; paramètres et fragments retirés. Do Not Track et Global Privacy Control désactivent l'envoi des pages vues. |
| Restriction du navigateur | Les connexions de l'application sont limitées à sa propre origine. La mesure Vercel utilise cette origine : la restriction ne signifie donc pas absence de traitement par un tiers. |

Des liens permettent aussi d'ouvrir volontairement des sites tiers : information de l'Assurance
Maladie, Mon espace santé, pages sociales et professionnelles du projet, questionnaire facultatif
et messagerie. L'application ne place pas le contenu du carnet dans ces adresses. La navigation
et les informations saisies ensuite sur un service tiers relèvent de ce service. Le périmètre
publié figure dans la [politique de confidentialité](https://crohnapp.com/privacy).

## Où vivent les données

- Le carnet de suivi est enregistré sur l'appareil, dans un coffre chiffré qu'ouvre le mot de
  passe du profil.
- Les photos et les informations qui les accompagnent sont chiffrées dans un espace séparé.
- Seules des informations non cliniques restent en clair : l'identifiant du profil sur cet
  appareil et les préférences d'affichage.
- Les exports — CSV, JSON, sauvegardes chiffrées, PDF, PNG — sont fabriqués sur l'appareil et
  n'existent que si l'utilisateur les demande.

## Ce que cette vérification ne prouve pas

C'est une relecture interne, pas un audit indépendant. Le constat exact est « aucun envoi de
données de santé n'a été trouvé dans le périmètre examiné », et non « zéro risque ». En
particulier :

- une extension de navigateur, un appareil compromis ou une dépendance malveillante ne sont pas
  couverts par cette lecture ;
- la restriction imposée au navigateur limite les destinations possibles, mais ne prouve pas
  qu'un code injecté ne pourrait rien faire ;
- un contrôle du trafic réseau en conditions réelles reste souhaitable, de même qu'un audit de
  sécurité indépendant, qui n'a pas encore été réalisé.

Les alertes portant sur les composants tiers sont suivies séparément : voir la
[gestion des dépendances](gestion-dependances.md). Une vérification des flux ou un audit limité
aux dépendances de l'application ne permet pas de déclarer tout l'outillage exempt de risque.

## Quand refaire cette vérification

À chaque mise en production notable, et systématiquement si l'application venait à intégrer un
compte serveur, une synchronisation, une sauvegarde en ligne, une extension de la mesure
d'audience ou un nouveau mécanisme d'envoi automatique.
