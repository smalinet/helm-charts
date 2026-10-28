# AGENTS.md

Helm chart repository, published via GitHub Pages (`https://smalinet.github.io/helm-charts`) and OCI (`ghcr.io/smalinet/helm-charts`). One chart lives under `charts/<name>/`.

## Tooling

Requires: `helm` with the builtin `helm schema` command (repo verified with helm v4.3.1), `helm-docs`, `git-cliff`, `just`. Task runner is `justfile` — use it instead of raw commands:

- `just helm-lint <chart>` — strict lint (`helm lint --strict`)
- `just helm-docs <chart>` — regenerate chart `README.md`
- `just helm-schema <chart>` — regenerate `values.schema.json`
- `just gen-rel <chart>-<version>` — release prep (see below)

## Generated files — do not hand-edit

- `charts/<chart>/README.md` is generated from `README.md.gotmpl` + `# --` comments in `values.yaml` by helm-docs.
- `charts/<chart>/values.schema.json` is generated from `values.yaml`.

Edit `values.yaml` (with `# --` doc comments) and templates, then run `just helm-docs <chart>` and `just helm-schema <chart>`.

## Commits and releases

- Conventional Commits are required: git-cliff parses them into `CHANGELOG.md` (scopes used: `helm`, `<chart-name>`, e.g. `fix(ocsinventory): ...`).
- `chore(release): prepare for <tag>` commits are excluded from the changelog by `cliff.toml`.
- Release flow (tag `ocsinventory-0.3.2` style, must exactly match `Chart.yaml` `name`-`version`):
  1. Bump `version` (and `appVersion` if needed) in `Chart.yaml`.
  2. `just gen-rel <chart>-<version>` — runs git-cliff in place, then `git commit -a -s -S` (Signed-off-by + signed commit) and creates a signed annotated tag. It commits ALL working-tree changes; commit and tag signing must be configured or it fails.
  3. Push the tag. `.github/workflows/release.yml` runs chart-releaser (publishes GitHub release/Pages index) then pushes the package to `ghcr.io/smalinet/helm-charts`.
- No CI runs on PRs/pushes to branches — run `just helm-lint <chart>` yourself before pushing.

## Notes

- Chart tests: `charts/<chart>/templates/tests/test-connection.yaml` runs via `helm test`.
