# Na'atik Japanese Language Repository

Curated Na’atik packages and approved resources for Japanese language support.

Status: repository skeleton only; zero published packages. No remote or public
repository is configured.

## Planned scope — not implemented

Planned categories: OCR, dictionaries, kanji data, language analysis, grammar,
speech, writing and translation. No working Japanese engine, provider, dictionary,
model or translation package is supplied by this skeleton.

Research/planning candidates only:

- Tesseract Japanese horizontal data: `jpn`.
- Tesseract Japanese vertical data: `jpn_vert`.
- JMdict candidate dictionary source.
- KANJIDIC candidate kanji source.

Nothing above has been downloaded, bundled, installed or approved for
redistribution. Canonical sources, precise versions, checksums, licenses,
attribution and redistribution terms must be separately audited before use.

## Repository format

This is an empty Na'atik schema-1 repository, following the existing
`internal/repositoryindex` and `internal/repository` implementation and fixtures.
It is not a new manifest format. No packages are currently published or installed.

```text
LICENSE
README.md
RESOURCE_PROVENANCE.md
THIRD_PARTY_NOTICES.md
repository.toml
packages/
  index.txt
```

`repository.toml` requires `schema = 1`, `[repository].id` and
`[repository].display_name`. It also supports repository `description` and
optional `[metadata].maintainer` / `homepage`. No hosting URL is assigned here.

`packages/index.txt` is intentionally zero bytes. The HTTP reader accepts blank
lines/comments and one repository-root-relative release metadata path per entry.
The local published reader recursively discovers `.toml` files under `packages/`;
it does not use index.txt. Both readers therefore return zero releases here.

When a real release is approved, the existing layout uses
`packages/<package-id>/<version>.toml` plus its real `.npkg` artifact under
`packages/<package-id>/`. Release metadata supports `schema`, `[id]` name/version,
`[package]` type, `[compatibility]` core, `[source]` package/sha256/size and
`[metadata]` display_name/description. Source `package` names the artifact; there
is no arbitrary artifact-URL field. The remote reader derives the URL from
`packages/<id.name>/<source.package>`. SHA-256 must be 64 hexadecimal characters;
size must be positive. An artifact's internal `naatik.toml` is a separate package
manifest. Do not invent a release entry, size, checksum or artifact in this skeleton.

Publication is not configured. The current Na'atik remote constructor strips a
trailing slash and uses standard relative URL resolution. A base URL containing
a path prefix consequently resolves these relative requests at its parent path.
Do not assume a future GitHub source repository URL or path-prefixed static site
is directly consumable. Qualify hosting/base-URL behavior separately before
registering the repository; do not work around it by inventing metadata fields.

## License and provenance

Original metadata/documentation/code: **PolyForm Noncommercial License 1.0.0**,
SPDX `PolyForm-Noncommercial-1.0.0`; source-available for noncommercial use.
Required Notice: Copyright (c) 2026 Alx Hndz

See [LICENSE](LICENSE), [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) and
[RESOURCE_PROVENANCE.md](RESOURCE_PROVENANCE.md). Third-party resources retain
their own terms; no legal or redistribution approval is implied.
