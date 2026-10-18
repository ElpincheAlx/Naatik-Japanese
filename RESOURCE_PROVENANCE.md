# Resource provenance and publication policy

Original repository metadata, documentation and code are source-available for
noncommercial use under PolyForm-Noncommercial-1.0.0. This does not license any
third-party resource. Required Notice: Copyright (c) 2026 Alx Hndz

Before publishing or acquiring any third-party resource, maintain a reviewed
provenance record containing at least:

- Canonical resource name.
- Upstream project/source and upstream URL.
- Exact version, revision or dated snapshot.
- License and applicable terms, including the authoritative license source.
- Attribution and notice requirements.
- SHA-256 of the exact acquired/distributed artifact.
- Redistribution status: not reviewed, permitted with recorded conditions, or prohibited.
- Delivery: hosted by this repository or downloaded from upstream; record the exact origin.
- Supported language/profile, including a specific variety when applicable.
- Supported platforms/architectures when relevant.

These are review requirements for documentation, not an extension of Na'atik's
manifest or repository schema. Never place unsupported provenance keys into
repository.toml or package release metadata. Finalize a machine-readable
provenance representation separately if required; none is invented here.

Unreviewed redistribution remains blocked. A checksum alone is not permission to
redistribute and does not independently authenticate an upstream publisher.
Do not list a candidate as installable until a real validated package/artifact
exists and its license, provenance, compatibility and delivery are reviewed.
Packages must not contain arbitrary installer shell commands or untrusted
post-install scripts. Do not add such commands to manifests. Preserve executable
containment, archive safety, explicit permissions and fail-closed isolation.
No automatic unsandboxed execution or silent provider fallback is permitted.

## PR-0139 Stage 3 — actual first-party adapter artifact

`ocr.tesseract@1.0.0`, Core 1.0.0, Linux amd64, CGO disabled. Publisher:
Na'atik / Alx Hndz. First-party license: PolyForm-Noncommercial-1.0.0.
Artifact `ocr.tesseract-1.0.0-linux-amd64.npkg`; SHA-256 `fcb9dd5997df512d7b4835536090680f50ce1232bfe1969a1608eb5d53963350`;
2435778 bytes. Exact members, binary hash, toolchain, source-file hashes and build
flags are recorded in `packages/ocr.tesseract/PROVENANCE.json` and the artifact's
`payload/BUILD-PROVENANCE.json`. The source is the sibling Na'atik checkout at
base `b7880e3ca26fe1c09075060f09eea2a03c758759` plus the recorded Stage 3 snapshot; the build-time record does not invent
a committed/published revision.

The genuine executable uses the audited internal provider implementation and
is built from the dedicated production command. The public reference example
remains standalone and uses public contracts only.
Only the Na'atik adapter and its required license/provenance material are
packaged. The binary links the Go runtime/standard library and
`golang.org/x/text@v0.28.0` (BSD-3-Clause); complete license/patent notices
are included. No external engine, model or dictionary is acquired or
redistributed. Tesseract, jpn and jpn_vert remain external system requirements;
JMdict and KANJIDIC are not included.

Archive/schema/checksum/size/readers and temporary local Package Manager install
PASS. Subsequent user-supplied external validation also passed real localhost
HTTP discovery, remote download/SHA-256/install/reload and normal isolated
Japanese horizontal/vertical OCR preflight and smoke recognition. Full/race/diff
gates and manual GTK/X11 validation passed without sandbox workarounds. This
qualified catalog was subsequently published and validated in PR-0139 Stage 4B
at `https://raw.githubusercontent.com/ElpincheAlx/Naatik-Japanese/main/`.
This is static catalog publication, not a new GitHub Release. The recorded
artifact and its build-time provenance remain unchanged.
