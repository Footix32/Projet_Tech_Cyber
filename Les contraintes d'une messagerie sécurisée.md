Une messagerie sécurisée est contraignante pour plusieurs raisons, comme discuté dans le podcast NoLimitSecu. 

## Présentation des interlocuteurs :

intervenant : Matthieu Finiasz et [Thomas Baigneres](https://www.linkedin.com/in/baigneres/) société Olvide 

Contributeur NoLimitSecu : Paul amar, hervé Shoer, Nicolas Rue

Matthieu Finiasz : cryptologue, enseignant-chercheur, crypto-expert

[Thomas Baigneres](https://www.linkedin.com/in/baigneres/) : Cryptologue, crypto-expert

## Contexte :

Olvide est une société qui propose une messagerie instantanée sécurisée
ils font de la sécu de bout en bout

- fonctionne un peu comme Whatsapp
- une version payante et une version gratuite

la payante comprends : 

- Multi appareil synchronisé 
- Appel et appel visio
- Bot olvide, automatisation de message

Toutes les informations échangées via Olvid sont [chiffrées de bout en bout](https://fr.wikipedia.org/wiki/Chiffrement_de_bout_en_bout).

- Système de chiffrement qui permet seulement à l’utilisateur d’avoir accès à ses données, la société Olvide ne peut pas y avoir accès car les données sont chiffrés

- Nos serveurs sont hébergés par AWS. La rupture technologique d’Olvid est de garantir la sécurité de ses utilisateurs via des mécanismes cryptographiques, qui n’ont pas de nationalité, sans avoir à faire confiance aux serveurs.

- Ne conserve pas l’adresse IP des clients sur leurs serveurs

- Pas de tracker

- A la création du compte, aucune donnée n’est envoyé aux serveurs, le compte est stocké en local sur l’endpoint, Olvide utilise l’adresse IP pour son fonctionnement 

- Pas de sous-traitant à part les serveurs AWS

les données échangées avec Olvid sont ***systématiquement*** chiffrées de bout en bout. Tout ce qu’un appareil envoie sur le réseau via Olvid présente la structure suivante :

`Données chiffrées ou aléatoires || Clé publique du destinataire`

Étant donnés les algorithmes de chiffrement utilisés par Olvid (dans le cas des messages : Encrypt-then-MAC avec AES-256 en mode CTR et HMAC sur SHA256), les données chiffrées sont indistinguables de données aléatoires uniformément distribuées (autrement dit, indistinguables d’un bruit numérique). Il est donc cryptographiquement impossible d’en extraire quelque information que ce soit (en dehors de la taille de la donnée chiffrée, mais là encore, Olvid applique certaines techniques pour mitiger ce risque). La clé publique du destinataire (en clair) permet de transmettre le message à son destinataire (à l’image d’une adresse sur une enveloppe cachetée). Cette clé publique ne permet pas de déduire la moindre information personnelle sur son propriétaire (i.e., sur l’appareil détenant la clé cryptographique privée correspondante).

confidentialité :  Si Olvid n’est pas l’unique solution de messagerie instantanée grand public à proposer du chiffrement de bout en bout, ***elle garantit également l’authentification de bout en bout, autrement dit, à ne pas faire reposer la confidentialité et l’authenticité des échanges sur un annuaire centralisé***.

Voici les principales contraintes :

1. **Complexité du chiffrement** : Mettre en place et gérer des systèmes de chiffrement robustes est techniquement complexe. Cela implique l'utilisation de clés publiques et privées, la gestion de certificats, et des protocoles de chiffrement avancés pour assurer que seules les parties autorisées peuvent lire les messages.

2. **Authentification stricte** : La nécessité de vérifier l'identité des utilisateurs de manière fiable ajoute une couche de complexité. Les méthodes comme l'authentification à deux facteurs (2FA) ou la biométrie doivent être implémentées pour éviter les accès non autorisés, ce qui peut être perçu comme contraignant pour les utilisateurs.

3. **Protection des métadonnées** : Même si le contenu des messages est chiffré, les métadonnées telles que les informations sur les expéditeurs, les destinataires, et les horodatages peuvent encore révéler des informations sensibles. Protéger ces métadonnées nécessite des techniques supplémentaires comme l'anonymisation ou le routage sécurisé, ce qui ajoute à la complexité.

4. **Conformité réglementaire** : Les solutions de messagerie doivent se conformer à diverses régulations locales et internationales, comme le RGPD en Europe. Cela implique des audits réguliers et des mises à jour pour rester en conformité, ce qui peut être contraignant pour les entreprises et les développeurs .

5. **Facilité d'utilisation vs sécurité** : Il est souvent difficile de trouver un équilibre entre une sécurité renforcée et une facilité d'utilisation. Les utilisateurs peuvent être réticents à adopter des mesures de sécurité trop complexes ou intrusives, ce qui peut limiter l'acceptation et l'utilisation de la messagerie sécurisée.

6. **Gestion des incidents** : Les systèmes de messagerie sécurisée doivent avoir des protocoles en place pour réagir rapidement et efficacement en cas de compromission ou d'attaque. Cela nécessite des ressources et des compétences spécifiques pour surveiller, détecter et répondre aux incidents de sécurité.

En résumé, les contraintes d'une messagerie sécurisée proviennent principalement de la complexité technique, de la nécessité de procédures strictes d'authentification, de la protection des métadonnées, de la conformité réglementaire, de la recherche d'un équilibre entre sécurité et convivialité, et de la gestion proactive des incidents de sécurité. Ces éléments rendent le déploiement et l'utilisation de telles solutions plus difficiles et contraignantes que les messageries classiques.

Source : ([NoLimitSecu](https://www.nolimitsecu.fr/les-contraintes-dune-messagerie-securisee/))