# XDV QHPI Tests

Deterministic tests and fixtures for `xdv-qhpi`.

## Covered Behaviors

- Provider registration and attestation verification.
- Calibration contract validity and expiration handling.
- Q job submission protocol checks and no-clone enforcement.
- Deterministic provider error mapping and escalation action.

## Entrypoints

- `xdv-qhpi/src/qhpi_tests.ds` : core behavior checks.
- `xdv-qhpi/tests/qhpi_e2e.ds` : aggregate test entrypoint.

## Run

```bash
dust check xdv-qhpi/src
dust check xdv-qhpi/tests/qhpi_e2e.ds
```
