# PRAXO-CORE for Delphi / Free Pascal

Dedicated repository for the Delphi / Free Pascal implementation of
PRAXO-CORE: an embeddable, MIT-licensed agent execution kernel with policy
controls, human-in-the-loop approval, checkpoints, events, and tool calling.

- Package: `PRAXO-CORE` (OPM assets)
- Documentation: https://axisvela.github.io/praxo-core/languages/delphi/
- Canonical source: https://github.com/axisvela/praxo-core/tree/main/language/delphi
- Release index: https://axisvela.github.io/praxo-core/languages/registry-status/

This repository is a discovery mirror of the canonical Delphi source. The
monorepo remains the source of truth and the release workflow source. Shared
conformance vectors are included under `spec/`.

Free Pascal 3.2.2 is the verified compiler. Commercial Delphi is unverified.
OPM maintainer submission is pending.

## Build

Build with Free Pascal using `praxo.pas`, or use the published OPM assets.

## Verify

Build and test instructions are in `language/delphi/README.md`. The monorepo CI
runs the Free Pascal conformance and native tests.

PRAXO-CORE is not a hosted model, workflow engine, identity provider, or safety
controller. Do not infer exactly-once execution, complete sandbox isolation,
production security certification, live-provider behavior, or physical safety
from this package.

MIT licensed.
