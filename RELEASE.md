# Release Process

This project uses `pyproject.toml` and `setuptools-scm` for automatic version management.

## Configuration

All package configuration has been migrated to `pyproject.toml`. The version number is automatically derived from Git tags using `setuptools-scm`, and written to `src/tweety/_version.py` (which is gitignored).

## Setup PyPI Trusted Publisher

This project uses PyPI Trusted Publishers for secure, token-free authentication.

### First-time setup (before first release)

1. Go to https://pypi.org/manage/account/publishing/
2. Add a new pending publisher with:
   - PyPI Project Name: `tweety-changchiyou`
   - Owner: `changchiyou`
   - Repository name: `tweety`
   - Workflow name: `release.yml`
3. Save the configuration

The first time you push a tag, PyPI will automatically create the project and link it to your GitHub workflow. Subsequent releases will work automatically.

No API tokens needed.

## Release a New Version

No manual version updates needed. Simply tag and push:

```bash
# Commit your changes
git add .
git commit -m "Your changes"

# Create and push a tag
git tag v2.5.0
git push origin v2.5.0
```

GitHub Actions will automatically:
- Extract version from tag (v2.5.0 → 2.5.0)
- Build the package
- Publish to PyPI
- Create a GitHub Release

## Versioning

Follow [Semantic Versioning](https://semver.org/):

- `v2.5.0` - Major version (breaking changes)
- `v2.4.2` - Minor version (new features, backwards compatible)
- `v2.4.1` - Patch version (bug fixes)

## Local Testing

```bash
# Install build dependencies
pip install build setuptools-scm

# Check current version
python -m setuptools_scm

# Build locally
python -m build
```

## Version Derivation

setuptools-scm derives version from Git state:

- On tag: `v2.5.0` → `2.5.0`
- After tag with commits: `v2.5.0` + 3 commits → `2.5.1.dev3+g1234567`
- With uncommitted changes: adds `.dirty` suffix

This ensures every build has a unique version identifier.
