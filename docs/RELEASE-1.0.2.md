# MPS 1.0.2 — compiled container distribution

- Application Python modules now ship as compiled native extensions, not readable Python source or bytecode.
- Both Linux AMD64 and ARM64 are supported. First-party source and generated C are excluded from every runtime image layer.
- Web/worker startup, setup protection and persistent configuration/key retention are verified against the compiled runtime.
- Existing licence behaviour and data paths are unchanged. Back up the full app data/state directory before updating; update in place rather than uninstalling.
- The source repository is private. Compilation does not prevent reverse engineering or revoke previously downloaded copies.
- No Windows/Linux installer downloads are included; earlier private installer builds are not source-free.

This release is distributed as a container through the MPS community Umbrel store. Official store acceptance and actual on-device Umbrel upgrade remain separate from container verification.

## Verified distribution

Image: `ghcr.io/matty03072/mps-media-payment-system:v1.0.2@sha256:900a2bfe343291f7534b7fa99f34724794d914a629b48cf8f3036c7e4b6dcbd3`.

Native AMD64 and ARM64 builds, whole-layer source audits, anonymous published pulls, setup protection, application regression suites, web/worker startup, worker heartbeat and restart/key retention all passed. No physical Umbrel installation or update was performed.
