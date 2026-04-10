# XDV Q Hardware Provider Interface

Version: 0.1.0
Status: active
Language: Dust Programming Language (DPL)

## Specification Alignment

Primary specification: XDV-060 in `xdv-spec`.

Implemented focus for this milestone:

1. Provider registration and attestation flow.
2. Calibration contract and Q job submission protocol.
3. Deterministic error mapping and escalation behavior tests.

## Purpose

Q-domain hardware provider boundary for deterministic, contract-validated execution.

## Modules

- `src/qhpi_contracts.ds`
  Normative status/error constants and validation for providers, calibration windows, measurement spec, and decoherence budget.

- `src/qhpi_provider.ds`
  Provider registration, capability tokenization, attestation token generation, and verification.

- `src/qhpi_calibration.ds`
  Calibration contract tokenization and validity/expiration behavior.

- `src/qhpi_job.ds`
  Q job descriptor model, submission validation pipeline, no-clone boundary enforcement, and measurement result tokenization.

- `src/qhpi_errors.ds`
  Deterministic provider failure mapping, signed error report tokenization, and deterministic escalation action.

- `src/qhpi_tests.ds`
  Behavioral tests for registration/attestation, calibration+job protocol, and deterministic error mapping.

- `src/main.ds`
  Startup validation, smoke flows, and self-test entrypoints.

## Design Notes

- Provider identity and calibration are mandatory gates before job acceptance.
- Job descriptors remain classical metadata and do not expose raw Q-state.
- No-clone boundary is explicitly checked and mapped to stable error code.
- Error mapping and escalation are deterministic for replay equivalence.

## Build

```bash
dust check xdv-qhpi/src
```

## Test

```bash
dust check xdv-qhpi/src/qhpi_tests.ds
dust check xdv-qhpi/tests/qhpi_e2e.ds
```

## Integration Contracts

- Preserve deterministic provider registration and attestation decisions.
- Require valid calibration contract for new Q jobs.
- Keep no-clone enforcement on submission path.
- Emit stable error codes and deterministic escalation actions.
