# Code Review : Meilleures Pratiques

## 1. Pratiques Équipe (une fois par projet)

- [ ] Documenter et standardiser le processus de code review. ([exemple](exemples/01-documenter-et-standardiser-processus-code-review.md))
- [ ] Assurer que l'objectif des revues de code est clair pour tous. ([exemple](exemples/02-objectif-code-review.md))
- [ ] Assurer que la "Définition de Fait" est documentée et claire pour tous. ([exemple](exemples/03-definition-of-done.md))
- [ ] Offrir du temps aux développeurs pour participer aux revues de code. ([exemple](exemples/04-allocation-du-temps.md))
- [ ] Définir un processus de résolution des conflits dans les revues de code. ([exemple](exemples/05-resolution-des-conflits.md))
- [ ] Avoir un guide de style définitif pour les préférences de style. ([exemple](exemples/06-coding-style.md))
- [ ] Utiliser des analyses statiques/dynamiques pour réduire les bruits durant les revues (linting, diffing, etc.). ([exemple](exemples/07-analyse-code-review.md))
- [ ] Définir des attentes claires pour les délais de code review. ([exemple](exemples/08-guide-delais-review.md))
- [ ] Mettre en avant les grandes versions ou les zones de code importantes afin que cela devienne une priorité dans les revues. ([exemple](exemples/09-priorite-code-review-majeure.md))
- [ ] Créer un environnement ouvert et encourageant pour le partage de code et d'apprentissage. ([exemple](exemples/10-code-conduite-collaboration-code-review.md))
- [ ] Encourager un processus de revue sain où personne ne se sent jugé. ([exemple](exemples/11-code-conduite-positive-code-review.md))
- [ ] Récompenser les contributions aux revues de code autant que d'autres formes de contributions. ([exemple](exemples/12-reconnaissance-contribution-code-review.md))
- [ ] Avoir un bon équilibre d'automatisation dans CI avec un minimum de faux positifs. ([exemple](exemples/13-optimisation-ci.md))
- [ ] Impliquer les membres de l'équipe dans les revues de code pour partager les connaissances. ([exemple](exemples/14-partager-la-connaissance.md))
- [ ] Encourager les revues à être un exercice d'équipe, pas une attaque personnelle. ([exemple](exemples/15-pratiques-code-review-orientee-equipe.md))

## 2. Pendant le Développement (Auteur)

- [ ] Suivre les normes de codage et toute autre directive de l'équipe.
- [ ] Rester cohérent avec la conception et l'architecture globales du projet.
- [ ] Écrire un test en échec si la modification concerne la correction d'un bogue.
- [ ] Découper les tâches complexes en PR/MRs plus petites et plus faciles à gérer.
- [ ] Considérer l'impact du changement sur d'autres parties du système.
- [ ] Prendre des notes sur toute question ou préoccupation concernant le changement pour en discuter lors de la revue.
- [ ] Écrire des tests automatisés.
- [ ] Rédiger la documentation pour la fonctionnalité ou le changement si nécessaire.
- [ ] Mettre à jour toute documentation qui pourrait avoir été affectée par les changements.

## 3. Après le Développement (Auteur)

- [ ] Réviser votre code avant de le soumettre à la revue.
- [ ] S'assurer que les modifications sont complètes et prêtes pour la revue, y compris tous les tests et la documentation nécessaires.
- [ ] Vérifier que le changement de code a été correctement testé dans un environnement de développement.
- [ ] Vérifier que le code respecte les normes de codage et les meilleures pratiques du projet.
- [ ] Identifier tout problème potentiel de performance, de sécurité ou d'évolutivité et les noter pour en discuter lors de la revue.
- [ ] Faire des listes et marquer les fichiers appropriés (par exemple, fichiers tiers, fichiers générés automatiquement) pour éviter toute confusion dans la PR/MR.
- [ ] Aborder le processus de revue avec l'esprit ouvert et être prêt à apprendre et collaborer avec d'autres membres de l'équipe.

## 4. Avant la Revue (Relecteur)

- [ ] Comprendre la demande et le contexte dans lequel le changement a été effectué.
- [ ] En fonction des exigences, préparer une liste des éléments qui devraient avoir été couverts dans les modifications.
- [ ] Effectuer une exploration de l'application pour détecter les cas particuliers.
- [ ] Considérer le point de vue de l'auteur et les raisons derrière le changement.
- [ ] Faire une liste des risques ou des problèmes potentiels et demander des informations sur les mesures d'atténuation possibles.
- [ ] Fournir des retours clairs et exploitables, y compris des suggestions spécifiques pour améliorer et explorer les préoccupations.
- [ ] Identifier tout problème potentiel de performance, de sécurité ou d'évolutivité, et en discuter avec l'auteur.
- [ ] Prioriser vos retours, en vous concentrant d'abord sur les problèmes les plus importants.
- [ ] Revoir les tests inclus avec les modifications de code pour vérifier qu'ils couvrent adéquatement la fonctionnalité et les cas particuliers.
- [ ] S'assurer que la modification du code respecte les normes de codage et les meilleures pratiques du projet.
- [ ] S'assurer que la documentation pertinente a été mise à jour.
- [ ] Travailler avec l'autorité décisionnelle lors de la vérification des modifications par rapport à la sortie ou aux préférences personnelles.
- [ ] Fournir des commentaires pour suggérer des améliorations, mais les préfixer par "Nit:" s'ils ne sont pas essentiels pour répondre aux normes.
- [ ] Avoir en tête des considérations à court et à long terme.
- [ ] Envisager d'utiliser la programmation en binôme comme alternative ou complément aux revues de code.
- [ ] Fournir des retours positifs en plus des critiques constructives, pour renforcer les bonnes pratiques et encourager le moral de l'équipe.

## 5. Après la Code Review (Auteur)

- [ ] Traiter tous les retours reçus, y compris tous les commentaires ou questions soulevés.
- [ ] Implémenter les modifications suggérées et fournir des explications si nécessaire.
- [ ] Lancer les tests et s'assurer qu'ils passent tous après avoir apporté les modifications.
- [ ] Mettre à jour toute documentation ou commentaire de code affecté par les modifications.
- [ ] Demander l'avis d'autres membres de l'équipe si vous n'êtes pas sûr des modifications.
- [ ] Soumettre le code mis à jour pour une nouvelle revue si nécessaire.

## 6. Après la Code Review (Relecteur)

- [ ] Résoudre rapidement les opinions conflictuelles ; que ce soit un PR/MR prêt à être terminé en raison d'un désaccord.
- [ ] Vérifier que tous les retours ont été traités par l'auteur.
- [ ] Revoir le code mis à jour et s'assurer que les modifications suggérées ont été mises en œuvre comme prévu.
- [ ] Être réactif et s'assurer que la traînée de revue avance à un bon rythme.
- [ ] Être ouvert aux retours de l'auteur et être prêt à ajuster vos retours si nécessaire.

## 7. Après Approbation (Auteur / Relecteur)

- [ ] Fusionner les modifications de code approuvées dans la branche principale/de sortie.
- [ ] Vérifier que le changement de code fonctionne comme prévu dans l'environnement de production.
- [ ] Célébrer l'achèvement réussi du changement de code !
