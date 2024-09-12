# Static and Dynamic Analysis in Code Reviews

* pre-commit should be installed and configured on the project. All user should enforce pre-commit (`pre-commit install`).
* Every PR/MR should pass the ruff linter for python before submission.
* Use Prettier to auto-format other type of files to reduce formatting inconsistencies.
* The CI pipeline includes:
  * Pytest: Unit tests run automatically on each push.
  * SonarQube: Static analysis tools like for security and code quality checks.
  * Check code coverage reports generated in SonarQube to ensure at least 75% test coverage.
* Automated tools should raise issues on trivial matters so reviewers can focus on the logic and structure. (thank you ruff)
