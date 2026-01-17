# Release Guide

This project publishes to PyPI from a GitHub tag. The tag value is used as the
package version.

## One-time setup
1. Create a PyPI API token with scope for this project.
2. Add the token to the GitHub repository secrets:
   - Name: `PYPI_API_TOKEN`
   - Value: your PyPI token

## Tag format
- Use semantic version tags: `vMAJOR.MINOR.PATCH`
- Example: `v0.1.0`

## Release steps
1. Update code and docs.
2. Create and push a tag:
   - `git tag v0.1.0`
   - `git push origin v0.1.0`
3. GitHub Actions builds and publishes the package.

## Notes
- The workflow only runs on tags that match `v*.*.*`.
- The workflow overwrites `version` in `pyproject.toml` during the build.
