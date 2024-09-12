# Guide de Style de Code

* En python, utiliser 4 espaces pour l'indentation, ailleurs utiliser 2 espaces, **pas de tabulations**.
* Tous les noms de variables et de fonctions doivent être écrits en snake_case.
* Les noms de classes doivent suivre le PascalCase.
* Utiliser des annotations de types.
* Favoriser les fonctions pures.
* Essayer de séparer les fonctions pures des fonctions avec effets de bord.
* Écrire des fonctions testables (penser à la testabilité lors de la conception de la fonction).
* Essayer de maintenir un niveau conceptuel cohérent dans une fonction (pas d'actions bas niveau dans des fonctions haut niveau).
* Utiliser des guillemets doubles pour les chaînes sauf pour les littéraux de template.
* Placer les accolades ouvrantes sur la même ligne que la déclaration.
* La longueur maximale des lignes doit être de 100 caractères (utiliser cette règle de manière intelligente).
* Les docstrings doivent être écrits avec des commentaires en bloc pour les fonctions et des commentaires en ligne pour les explications en ligne.
* Les imports doivent être triés et nettoyés.

En résumé, pour python, utiliser ruff pour formater le code.
