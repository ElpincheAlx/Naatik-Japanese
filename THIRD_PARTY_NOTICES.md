# Third-party notices

The prepared `ocr.tesseract@1.0.0` artifact contains a Na'atik-owned adapter,
licensed PolyForm-Noncommercial-1.0.0, with required notice:
Copyright (c) 2026 Alx Hndz.

Its executable links:

- Go standard library/runtime, built with `go version go1.26.9-X:nodwarf5 linux/amd64`:
  BSD-3-Clause; full Go LICENSE and PATENTS are included under
  `payload/licenses/Go-LICENSE` and `payload/licenses/Go-PATENTS`.
- `golang.org/x/text@v0.28.0`: BSD-3-Clause; full LICENSE and PATENTS
  are included under `payload/licenses/x-text-LICENSE` and
  `payload/licenses/x-text-PATENTS`.

License texts were read from the installed Fedora Go license directory and the
existing verified Go module checkout, not downloaded for this stage. Those
third-party rights remain distinct from the repository's first-party license.
The artifact also contains `payload/THIRD_PARTY_NOTICES.md` and the complete
Na'atik LICENSE.

**Not bundled:** Tesseract binaries/libraries, `jpn.traineddata`,
`jpn_vert.traineddata`, JMdict, KANJIDIC, other language models, dictionaries or
sample images. System-installed Tesseract/data keep their own upstream and
Fedora terms; Na'atik does not claim ownership or redistribution approval.

See [RESOURCE_PROVENANCE.md](RESOURCE_PROVENANCE.md) and the package's exact
[PROVENANCE.json](packages/ocr.tesseract/PROVENANCE.json). Normal isolated Japanese OCR runtime qualification passed externally, as supplied
by the user. Public publication has not occurred; redistribution boundaries and
third-party notices remain unchanged.
