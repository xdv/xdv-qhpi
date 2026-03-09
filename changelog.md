# Changelog

## 0.1.1 - XDV-060 QHPI Core Implementation

- Implemented XDV-060 contract constants and validators in `src/qhpi_contracts.ds`.
- Implemented provider registration, capability declaration, and attestation verification in `src/qhpi_provider.ds`.
- Implemented calibration contract tokenization and validity/expiration checks in `src/qhpi_calibration.ds`.
- Implemented job descriptor validation, submission protocol, no-clone boundary, and measurement result tokenization in `src/qhpi_job.ds`.
- Implemented deterministic error mapping, report tokenization, and escalation actions in `src/qhpi_errors.ds`.
- Added behavior tests in `src/qhpi_tests.ds`.
- Added aggregate test entrypoint `tests/qhpi_e2e.ds`.
- Updated README and docs for delivered XDV-060 behavior.

## 0.1.0 - Initial Skeleton

- Created project scaffold for XDV Q Hardware Provider Interface.
- Added State.toml, README.md, and docs/test placeholders.
- Imported LICENSE from xdv-os/LICENSE.
