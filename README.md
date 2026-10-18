# Na'atik Japanese Language Repository

Published official Na'atik language catalog with the genuine Na'atik-owned OCR
adapter `ocr.tesseract@1.0.0` for Linux amd64. PR-0139 Stage 4B public
HTTP/download/SHA-256/install/reload and isolated Japanese horizontal/vertical
OCR passed in external validation supplied by the user. Public catalog hosting
is distinct from a GitHub Release or a new Na'atik application release.

Canonical static catalog base:
https://raw.githubusercontent.com/ElpincheAlx/Naatik-Japanese/main/

Use Na'atik **Configuración guiada → Japonés → Agregar repositorio / Instalar
adaptador**, or review **Instalar recomendado**. The engine and traineddata
remain separate system requirements. Do not add the GitHub HTML source URL as
a static catalog base. New local documentation commits are not public until
separately reviewed/merged/pushed; this preparation publishes nothing.

## Prepared adapter

- Package: `ocr.tesseract@1.0.0` (existing canonical identity; no second provider ID).
- Core compatibility: `1.0.0`; manifest and repository schema remain 1.
- Platform: **Linux amd64 only**, built with CGO disabled. The current manifest
  format has no architecture-selection field: only install this artifact on
  Linux amd64. Other platforms are not qualified and runtime remains fail-closed.
- Author/publisher: Na'atik / Alx Hndz.
- First-party license: PolyForm-Noncommercial-1.0.0.
- Artifact: `packages/ocr.tesseract/ocr.tesseract-1.0.0-linux-amd64.npkg`.
- SHA-256: `fcb9dd5997df512d7b4835536090680f50ce1232bfe1969a1608eb5d53963350`.
- Size: **2435778 bytes**.

The adapter speaks the existing OCR Provider v1 protocol. The production command
`Naatik/cmd/ocr-tesseract-provider` uses `Naatik/internal/tesseractprovider`. The
public reference example remains standalone on public contracts. The production
adapter adds a bounded recognition timeout. Source/provenance, complete
archive contents and toolchain are recorded in
[PROVENANCE.json](packages/ocr.tesseract/PROVENANCE.json).

This package does **not** contain Tesseract, `jpn.traineddata`,
`jpn_vert.traineddata`, JMdict or KANJIDIC. It includes the adapter executable,
its existing schema-1 manifest, first-party license, build provenance, and linked
Go/`golang.org/x/text` license notices. Installing an adapter is distinct from
installing or verifying external engine/data dependencies.

## External Fedora requirements

Observed on Fedora 44 during PR-0139 Stage 3:

| Requirement | Observed path | RPM owner |
| --- | --- | --- |
| Tesseract 5.5.3 | `/usr/bin/tesseract` | `tesseract-5.5.3-2.fc44.x86_64` |
| Japanese horizontal | `/usr/share/tesseract/tessdata/jpn.traineddata` | `tesseract-langpack-jpn-4.1.0-12.fc44.noarch` |
| Japanese vertical | `/usr/share/tesseract/tessdata/jpn_vert.traineddata` | `tesseract-langpack-jpn_vert-4.1.0-12.fc44.noarch` |

These remain system-owned third-party resources. Na'atik's compiled first-party
Fedora guidance names the verified packages but does not execute an installer.
No unverified distro mapping, manifest command, environment injection or
privileged command is introduced. Use your system software manager and then
press **Comprobar de nuevo** in Guided Setup.

The existing restricted Bubblewrap view mounts `/usr` read-only; no new host
mount or TESSDATA_PREFIX inheritance was added. The models are visible by path
policy, but actual sandbox access and model loading require a successful explicit
normal-provider preflight. Host detection alone never makes Japanese OCR Ready.

## Repository format and qualification

`repository.toml` retains identity `naatik-japanese`. Its catalog base is
maintained centrally by Na'atik; no schema or repository identity changes.
`packages/index.txt` lists the real existing `ocr.tesseract/1.0.0.toml`, whose
artifact SHA-256 and byte size are computed from the actual file. No unsupported
platform/provenance keys were added to the existing TOML schemas.

PASS: existing local parser, archive extraction/manifest parsing, Linux amd64
build-info inspection, checksum/size, HTTP reader with an in-memory transport,
and installation/reload through the existing Package Manager into an isolated
temporary workspace. Guided Setup observed the installed adapter separately
from the engine/data requirements.

The original Codex runs were blocked by localhost socket/Bubblewrap restrictions.
Subsequent authoritative user-supplied external validation passed the real
localhost HTTP discovery, remote download/SHA-256/install/reload, Guided Setup
adapter detection and Japanese OCR readiness. Isolated horizontal and vertical
preflight was ready; smoke recognition returned `日本語の文字` and `日 本 語 の 文字`.
Manual GTK/X11 validation and full/race/diff gates also passed. No sandbox
workaround, fallback or broad filesystem permission was needed. These external
results supersede the earlier pending qualification, not the historical sandbox
failures. These Stage 3 results preceded public publication; subsequent
PR-0139 Stage 4B
validated the public catalog. No privileged automatic installer is provided.
Horizontal/vertical Japanese smoke images were generated locally from text using
an installed system font; no sample image was downloaded or bundled.

From the sibling Na'atik source checkout, inspect without execution:

```bash
go run ./tools/japanese-ocr-e2e -repository ../Naatik-Japanese -inspect-only
```

Externally, test the full real HTTP/package-manager/runtime path:

```bash
go run ./tools/japanese-ocr-e2e -repository ../Naatik-Japanese \
  -horizontal /tmp/pr0139-stage3-smoke/horizontal.png \
  -vertical /tmp/pr0139-stage3-smoke/vertical.png
```

The tool always creates and deletes its own temporary configuration/workspace.
`-local-artifact` independently tests the existing Package Manager's local
artifact path and provider runtime; it is explicitly not remote-install proof.
The real HTTP mode registers only the temporary local server in the temporary
workspace through existing APIs; no registration in the user's workspace.

The build helper `Naatik/tools/build-japanese-ocr-package.py` validates a temporary
catalog before writing output and refuses to overwrite an existing release.
The recorded source base is `b7880e3ca26fe1c09075060f09eea2a03c758759` plus
build-time Stage 3 source snapshot `47a5cb84d1ea43f16de9e26f59e332374c3cc4148bf39729a176035550c9c196`; this does not claim a nonexistent
Stage 3 source commit or public release. External qualification has now passed;
the immutable build-time provenance and artifact remain unchanged.

## Future scope and licenses

Dictionaries, kanji data, language analysis, grammar, speech, writing and
translation remain future work. JMdict/KANJIDIC are planning candidates only.
No new production implementation or resource for those domains is supplied.

Required Notice: Copyright (c) 2026 Alx Hndz.
See [LICENSE](LICENSE), [RESOURCE_PROVENANCE.md](RESOURCE_PROVENANCE.md) and
[THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).

## Current closure boundary

The original artifact, release metadata and immutable PROVENANCE.json remain
unchanged. This documentation update does not build, publish or replace a
package. HTTPS plus metadata validation, size and SHA-256 checks are the current
trust model; package/publisher signatures are not implemented. The public
catalog previously validated in Stage 4B must be rechecked independently when
network access is available. First-party material is source-available for
noncommercial use; third-party rights and notices remain separate.
