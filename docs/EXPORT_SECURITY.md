# Sauvegardes et exports : ce qui est protégé, ce qui ne l'est pas

*Revérifié le 30 août 2026 sur CrohnApp v1.2.4.*

## Choisir le bon format

| Format | Contenu | Protection une fois le fichier téléchargé |
| --- | --- | --- |
| CSV ou JSON lisible | Données du carnet, en clair | Aucune : toute personne qui obtient le fichier peut le lire |
| Sauvegarde du carnet, chiffrée | Profil, selles, symptômes, traitements, rendez-vous, scores | Protégée par un mot de passe de sauvegarde |
| Sauvegarde des photos, chiffrée | Images et informations associées | Fichier distinct, avec son propre mot de passe |
| Synthèse PDF, graphique PNG | Document lisible destiné à être montré | Aucune : vérifier le destinataire avant de partager |

Les sauvegardes chiffrées utilisent AES-GCM 256 bits, avec une clé dérivée du mot de passe par
PBKDF2-SHA-256 (600 000 itérations) et des valeurs aléatoires renouvelées à chaque export. Un
mot de passe incorrect ou un fichier modifié est rejeté plutôt que restauré partiellement.

## Deux sauvegardes, pas une

La sauvegarde du carnet et la sauvegarde des photos sont deux fichiers séparés. Aucune des deux
ne restaure le contenu de l'autre. Si vous avez des photos, il faut donc conserver les deux.

## Partager la synthèse PDF

Depuis la v1.2.2, la synthèse peut être remise directement à une autre application du téléphone.
C'est une **sortie volontaire**, déclenchée par un bouton, et non un envoi automatique. Aucun
serveur de CrohnApp n'intervient à aucune étape.

Le déroulement est le suivant :

1. **La synthèse est fabriquée sur l'appareil.** Rien n'est envoyé pour la produire.
2. **Le PDF obtenu n'est pas chiffré.** C'est un document destiné à être lu par un médecin ou un
   proche : il est lisible par quiconque obtient le fichier. C'est voulu, et c'est la raison pour
   laquelle il ne remplace pas une sauvegarde.
3. **Le partage n'a lieu que si vous le demandez.** L'application ouvre alors la feuille de partage
   du système, où vous choisissez la destination.
4. **Deux éléments partent ensemble** : le fichier PDF et un court résumé textuel qui l'accompagne,
   afin que le destinataire sache de quoi il s'agit. Ce résumé porte sur les mêmes données
   déclarées que le PDF.
5. **Après le partage, la destination vous appartient.** Messagerie, cloud, application tierce :
   ce qui advient du fichier relève ensuite de l'application choisie et de ses propres règles.
   CrohnApp n'a plus aucun moyen d'agir dessus, pas plus que sur un fichier que vous auriez
   téléchargé puis envoyé vous-même.

Trois comportements complètent ce parcours :

- Si le partage système n'existe pas sur l'appareil, le PDF est simplement **téléchargé** dans vos
  fichiers.
- Si vous **annulez** dans la feuille de partage, rien n'est partagé et rien n'est téléchargé.
- Si la remise du fichier **échoue**, l'application vous le dit. Un échec silencieux laisserait
  croire que la synthèse est partie.

Le partage de la synthèse n'est pas proposé depuis le profil de démonstration.

## Ce que personne ne peut faire pour vous

CrohnApp n'enregistre pas les mots de passe de sauvegarde et ne peut pas les réinitialiser. Il n'y
a pas de copie sur un serveur : un mot de passe perdu signifie une sauvegarde définitivement
illisible. Conservez chaque fichier et son mot de passe à des endroits distincts.

## Aller plus loin

Pour la marche à suivre pas à pas, voir le guide
[Créer et restaurer une sauvegarde chiffrée](guides/sauvegarder-restaurer.md). Pour une question
technique sur les formats ou une demande de lecture du code :
[crohnapp@gmail.com](mailto:crohnapp@gmail.com).
