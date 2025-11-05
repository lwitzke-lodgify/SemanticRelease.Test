# Semantic Versioning Workflow

This project uses semantic versioning with automated releases based on conventional commits.

## Conventional Commit Format

Commits should follow this format:
```
<type>(<scope>): <subject>

<body>

<footer>
```

### Commit Types and Version Bumps

- **BREAKING CHANGE** or `!` after type: **Major** version bump (e.g., 1.0.0 → 2.0.0)
- **feat**: **Minor** version bump (e.g., 1.0.0 → 1.1.0) - New feature
- **fix**: **Patch** version bump (e.g., 1.0.0 → 1.0.1) - Bug fix
- **perf**: **Patch** version bump - Performance improvement
- **docs**: **Patch** version bump - Documentation changes
- **style**: **Patch** version bump - Code style changes (formatting, etc.)
- **refactor**: **Patch** version bump - Code refactoring
- **test**: **Patch** version bump - Adding or updating tests
- **build**: **Patch** version bump - Build system changes
- **ci**: **Patch** version bump - CI configuration changes
- **chore**: **Patch** version bump - Other changes

## Examples

### Minor Version Bump (New Feature)
```
feat: add user authentication

Implemented JWT-based authentication for API endpoints
```

### Patch Version Bump (Bug Fix)
```
fix: resolve null reference exception in user service

Added null check before accessing user properties
```

### Major Version Bump (Breaking Change)
```
feat!: change API response format

BREAKING CHANGE: API now returns data in a new format that is incompatible with previous versions
```

Or:
```
feat: update authentication mechanism

BREAKING CHANGE: Changed from session-based to token-based authentication
```

## How It Works

1. When a PR is merged into `main` or `master`, the workflow triggers
2. Semantic-release analyzes commit messages since the last release
3. Determines the next version number based on commit types
4. Generates a changelog
5. Creates a GitHub release with release notes
6. Updates the CHANGELOG.md file

## Requirements

- Commits must follow conventional commit format
- PRs should be merged (not squashed) to preserve commit history, OR
- When squashing, the PR title/merge commit should follow conventional commit format

## First Release

The first release will be version 1.0.0. Make sure your first commit to trigger the workflow follows the conventional commit format.
