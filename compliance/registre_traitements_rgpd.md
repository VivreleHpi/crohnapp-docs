# Traitements décrits — carnet local et fonctionnement du site

*Référence : CrohnApp v1.3.5. Mise en cohérence documentaire du 14 novembre 2026 (v1.3.4),
confirmée le 20 novembre 2026 : v1.3.5 ne modifie aucun traitement de données.*

## Situation actuelle

Les **données de santé du carnet restent sur l'appareil**. CrohnApp ne dispose d'aucun serveur
de compte ou de copie distante du carnet. Le fonctionnement du site comprend néanmoins des
traitements techniques et une mesure d'audience des pages publiques : le mode local du carnet
ne signifie pas que le site n'effectue aucune communication réseau.

Ce document décrit les traitements identifiés. Il ne tranche pas leur qualification juridique,
leurs bases légales ou les obligations applicables. La
[politique de confidentialité](https://crohnapp.com/privacy) décrit les engagements publiés ;
une relecture technique ne remplace pas une validation juridique.

## Traitements liés au fonctionnement du site

| Traitement | Finalité et périmètre | Limites |
|---|---|---|
| Hébergement du site statique | Servir les fichiers et traiter les requêtes de connexion, notamment l'adresse IP et les caractéristiques du navigateur | L'hébergeur ne reçoit pas le contenu du carnet par ce mécanisme |
| Mesure d'audience Vercel Web Analytics | Statistiques générales de fréquentation des pages publiques autorisées sur crohnapp.com en production | Pages du carnet exclues, pas d'événement clinique personnalisé ; paramètres et fragments retirés de l'adresse mesurée ; envoi des pages vues désactivé par Do Not Track ou Global Privacy Control |
| Contact par e-mail | Répondre aux messages envoyés volontairement à crohnapp@gmail.com | Ne jamais envoyer de mot de passe, de sauvegarde ou de donnée de santé |

La mesure d'audience est assurée par Vercel même si ses échanges passent par le domaine du site.
Elle est distincte des calculs de la page « Analyses & tendances », exécutés localement. Le fonctionnement
sans cookie annoncé par le fournisseur ne démontre pas, à lui seul, une exemption de consentement,
une durée de conservation de toutes les données ou une localisation du traitement. Ces questions
doivent être examinées séparément ; aucune conformité générale n'est certifiée ici.
Les [conditions publiées par la CNIL pour la mesure d'audience](https://www.cnil.fr/fr/cookies-solutions-pour-les-outils-de-mesure-daudience)
constituent une référence pour cet examen, sans attester de la conformité de CrohnApp.

## Droits de l'utilisateur

Pour le contenu du carnet, les actions sont exercées directement dans l'application :

- **Accès et portabilité** : exports CSV et JSON lisibles, sauvegardes chiffrées du carnet et des
  photos.
- **Rectification** : édition directe de chaque entrée.
- **Effacement** : suppression entrée par entrée, ou remise à zéro complète depuis la page
  « Données & sauvegardes ». La suppression est locale et définitive.

CrohnApp ne conserve pas de copie distante du contenu du carnet à purger. Cette observation ne
s'applique pas aux informations techniques traitées par l'hébergeur, à la mesure d'audience ou
aux e-mails reçus. Pour une question concernant ces traitements, utilisez le contact indiqué
dans la politique de confidentialité.

## Si un backend est envisagé un jour

Le cadre devrait être entièrement réévalué **avant tout déploiement** : détermination des rôles
RGPD et des bases juridiques applicables, registre des traitements, examen de la nécessité d'une
analyse d'impact, politique de conservation, modalités d'exercice des droits, mesures de sécurité,
qualification du besoin d'hébergement certifié pour les données de santé, et gouvernance adaptée.

La nécessité de désigner un délégué à la protection des données, comme les modalités de recueil
d'un éventuel consentement, dépendraient de la finalité retenue et du cadre juridique applicable :
elles ne peuvent pas être présumées ici. **Aucun backend de données de santé ne sera déployé avant
que cette réévaluation ait été conduite.**
