# Liste de contrôle des meilleures pratiques de sécurité API

## 1. Authentification

1. [ ] Évitez l'authentification **Basic**, utilisez un standard (ex : JWT). ([exemple](exemples/01-jwt-fastapi.md))
2. [ ] Ne réinventez pas la roue en matière de mécanismes d'authentification. ([exemple](exemples/02-ne-pas-reinventer-la-roue.md))
3. [ ] Utilisez la **reprise automatique** et des mécanismes de sécurité lors des tentatives de connexion. ([exemple](exemples/03-limite-tentatives-et-blocage.md))
4. [ ] Utilisez le chiffrement pour toutes les données sensibles. ([exemple](exemples/04-utiliser-chiffrement.md))

## 2. JWT (JSON Web Token)

1. [ ] Utilisez un bon **secret JWT** pour rendre les attaques par force brute difficiles.
2. [ ] Ne pas extraire l'algorithme depuis l'en-tête, utilisez plutôt le backend.
3. [ ] Définissez une expiration du jeton (TTL, RTTL) aussi courte que possible.
4. [ ] Évitez de stocker des données sensibles dans la charge utile JWT.
5. [ ] Gardez la charge utile légère pour réduire la taille du JWT.

## 3. Contrôle d'accès

1. [ ] Limitez les requêtes (throttling) pour éviter les attaques DDoS ou de force brute.
2. [ ] Utilisez HTTPS côté serveur et sécurisez les clients.
3. [ ] Utilisez l'en-tête HSTS avec SSL pour éviter les attaques SSL Strip.
4. [ ] Désactivez les listes de répertoires.
5. [ ] Les API privées doivent être accessibles uniquement à partir d'adresses IP de confiance.

## 4. Authentification

1. [ ] Validez toujours **redirect_uri** côté serveur.
2. [ ] Évitez **response_type=token** et préférez échanger le code.
3. [ ] Utilisez le paramètre **state** pour prévenir les attaques CSRF.
4. [ ] Définissez un champ d'application par défaut et validez-le pour chaque application.

## 5. Entrées

1. [ ] Utilisez les bonnes méthodes HTTP pour l'opération.
2. [ ] Validez l'en-tête **content-type** dans la requête.
3. [ ] Validez les entrées utilisateur pour éviter les vulnérabilités courantes.
4. [ ] Utilisez un en-tête **Authorization** standard pour les données sensibles.
5. [ ] Utilisez uniquement le chiffrement côté serveur.
6. [ ] Utilisez une passerelle API pour la mise en cache, les politiques de limitation, etc.

## 6. Sorties

1. [ ] Envoyez l'en-tête **X-Content-Type-Options: nosniff**.
2. [ ] Envoyez l'en-tête **X-Frame-Options: deny**.
3. [ ] Envoyez l'en-tête **Content-Security-Policy: default-src 'none'**.
4. [ ] Supprimez les en-têtes d'identification (ex. : X-Powered-By, etc.).
5. [ ] Forcez le **content-type** pour votre réponse.
6. [ ] Évitez de renvoyer des données sensibles (identifiants, etc.) dans les réponses.
7. [ ] Renvoyez les codes de réponse appropriés selon l'opération.

## 7. Traitement

1. [ ] Vérifiez que tous les points d'accès sont protégés par authentification pour éviter les erreurs d'authentification.
2. [ ] Évitez l'utilisation d'ID personnel dans les URL (ex. : `/users/242/orders`).
3. [ ] Préférez utiliser UUID au lieu d'ID auto-incrémentés.
4. [ ] Désactivez le parsing des entités si vous parsez du XML pour éviter les attaques XXE.
5. [ ] Désactivez l'expansion des entités si vous utilisez XML, YAML ou tout autre langage.
6. [ ] Utilisez un CDN pour le téléchargement de fichiers.
7. [ ] Évitez le blocage HTTP si vous manipulez de grandes quantités de données.
8. [ ] Assurez-vous que le mode débogage est désactivé en production.
9. [ ] Utilisez une pile non exécutable si disponible.

## 8. CI & CD

1. [ ] Auditez votre conception et votre implémentation avec des tests unitaires/d'intégration.
2. [ ] Utilisez un processus de revue de code et écartez l'auto-approbation.
3. [ ] Analysez continuellement la sécurité de votre code.
4. [ ] Vérifiez vos dépendances pour détecter les vulnérabilités connues.
5. [ ] Concevez une solution de retour en arrière pour les déploiements.

## 9. Surveillance

1. [ ] Utilisez des connexions centralisées pour tous les services et composants.
2. [ ] Utilisez des agents pour surveiller toutes les requêtes, réponses et erreurs.
3. [ ] Utilisez des alertes via SMS, Slack, Email, Kibana, Cloudwatch, etc.
4. [ ] Assurez-vous de ne pas enregistrer de données sensibles.
5. [ ] Utilisez un système IDS et/ou IPS pour tout surveiller.
