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
