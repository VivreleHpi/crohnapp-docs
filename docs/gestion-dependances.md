# Gestion des dépendances et limites des contrôles

*Référence : CrohnApp v1.3.5. État documentaire du 20 novembre 2026.*

CrohnApp utilise des composants tiers pour son interface et des outils pour préparer, construire
et vérifier l'application. Leur suivi fait partie de la maintenance de sécurité, même lorsque
ces outils ne sont pas utilisés directement par une personne qui ouvre son carnet.

## Comment les mises à jour sont examinées

- Les versions résolues sont enregistrées dans un fichier de verrouillage, utilisé lors des
  installations de validation et de construction.
- Des alertes et des propositions de mise à jour automatiques complètent la consultation des
  avis des fournisseurs. Une proposition automatique ne vaut pas autorisation de publication.
- Les changements sont examinés par périmètre. Les migrations majeures sont traitées séparément ;
  une incompatibilité peut justifier un report documenté, sans faire disparaître l'alerte.
- Les contrôles pertinents vérifient le typage, les tests, la construction de l'application et
  les parcours navigateur, dont le fonctionnement hors ligne. Ils ne prouvent pas, à eux seuls,
  l'absence de vulnérabilité.
- Le contenu clinique, le chiffrement et la compatibilité des sauvegardes doivent être préservés.

## Application et outillage : deux périmètres à suivre

| Périmètre du contrôle | Ce qu'il permet d'observer | Sa limite |
| --- | --- | --- |
| Dépendances déclarées pour l'application, hors outils de développement | Alertes connues dans ce périmètre déclaré | Ne couvre pas tous les outils ni tous les risques du code livré |
| Ensemble des dépendances, outillage compris | Alertes connues pouvant aussi concerner le poste de développement ou la construction | Une alerte demande une analyse d'usage ; l'outil ne prouve ni son exploitation ni son absence d'impact |

Le contrôle automatisé utilisé pour la publication échoue sur une alerte élevée ou critique
dans le premier périmètre. Son succès ne signifie pas « aucune alerte » : des alertes modérées
peuvent subsister et l'audit complet peut encore échouer. Le seuil et les exclusions d'un audit
doivent donc rester visibles dans son interprétation.

La [documentation npm](https://docs.npmjs.com/cli/audit/) précise le rôle du seuil d'échec et
des dépendances omises. Un audit de dépendances ne remplace pas une revue du code ou un audit
de sécurité indépendant.

## État relevé pour v1.3.5

Le 19 novembre 2026, après la publication de v1.3.5, aucune alerte de dépendance connue n'est
ouverte, ni pour l'application ni pour l'outillage. Les mises à jour ont été menées par étapes
séparées, chacune vérifiée avant publication : typage, tests, construction, parcours navigateur
dont le fonctionnement hors ligne, et compatibilité des carnets, des photos et des sauvegardes
créés avec des versions antérieures. Les évolutions qui demanderaient d'adapter une partie
sensible du code sont examinées séparément, avant toute publication.

Cet état est daté et ne constitue pas une certification de sécurité : de nouveaux avis peuvent
apparaître. Voir la [note de maintenance v1.3.5](maintenance-v1.3.5.md).

## État relevé pour v1.3.4

Le 14 novembre 2026, le contrôle hors outillage ne relève aucune alerte élevée ou critique ;
des alertes modérées restent présentes. L'audit complet relève encore des alertes d'outillage,
y compris de niveau élevé. Elles restent suivies dans le dossier technique privé et ne sont
pas considérées sans risque au seul motif qu'elles concernent la construction ou les tests.

La livraison v1.3.4 inclut une mise à jour de sécurité de l'outillage de construction, sans
changement des carnets, du coffre ni des formats de sauvegarde. Voir le
[journal des changements](../compliance/journal_changements.md).

Cet état est daté : de nouveaux avis peuvent apparaître après la publication. Il ne constitue
pas une certification de sécurité et ne clôt pas les alertes encore présentes.

## Informations publiées et informations protégées

La documentation publique décrit le processus, son périmètre et ses limites. Les clés, jetons,
mots de passe réels, données et sauvegardes de patients doivent en rester exclus. Les journaux
privés, les configurations internes et les procédures détaillées de reproduction des alertes
non corrigées restent dans le suivi technique privé.

Expliquer le principe du chiffrement ou citer un algorithme ne révèle pas une clé. Les captures
destinées aux guides utilisent des données fictives et masquent les champs de mot de passe.
