# Analyse Statique et Dynamique dans les Revues de Code

* pre-commit doit être installé et configuré sur le projet. Tous les utilisateurs doivent appliquer pre-commit (`pre-commit install`).
* Chaque PR/MR doit passer le linter ruff pour Python avant soumission.
* Utiliser Prettier pour auto-formater les autres types de fichiers afin de réduire les incohérences de formatage.
* La pipeline CI inclut :
  * Pytest : Les tests unitaires sont exécutés automatiquement à chaque push.
  * SonarQube : Outils d'analyse statique pour les contrôles de sécurité et de qualité du code.
  * Vérifier les rapports de couverture de code générés dans SonarQube pour assurer au moins 75% de couverture de tests.
* Les outils automatisés doivent soulever des problèmes mineurs pour que les relecteurs puissent se concentrer sur la logique et la structure. (merci ruff)
