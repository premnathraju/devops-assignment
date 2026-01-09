## Version Control Strategy

This repository follows a GitFlow-inspired branching model to ensure clean history,
safe releases, and enterprise-level collaboration.

### Branching Model

- **`main`**
  - Contains production-ready, stable code
  - Always deployable
  - No direct commits are allowed

- **`develop`**
  - Integration branch for ongoing development
  - All features are merged here first
  - Acts as a staging branch before production

- **`feature/*`**
  - Used for implementing individual features, fixes, or improvements
  - Created from `develop`
  - Example: `feature/version-control-cleanup`

### Development Workflow

1. New work starts from the `develop` branch.
2. A dedicated `feature/*` branch is created for each task.
3. Changes are committed with clear, meaningful messages.
4. A Pull Request (PR) is opened from `feature/*` → `develop`.
5. After review and validation, the PR is merged into `develop`.
6. Once stable, a Pull Request is created from `develop` → `main`.
7. Production releases occur only via PR merges into `main`.

### Commit & Merge Practices

- Commits are small, atomic, and focused on a single change.
- Commit messages follow a descriptive format such as:
  - `feat:` for new features
  - `fix:` for bug fixes
  - `docs:` for documentation updates
- All merges into `develop` and `main` are performed using Pull Requests.
- Build artifacts and dependencies (`node_modules`, `.next`, `venv`, etc.)
  are excluded using `.gitignore`.

### Pull Request Policy

- Pull Requests are mandatory for merging into `develop` and `main`.
- PRs provide:
  - Code review opportunities
  - Audit trail of changes
  - Safer and more reliable releases

This strategy aligns with industry best practices and supports CI/CD automation,
collaborative development, and stable production deployments.
