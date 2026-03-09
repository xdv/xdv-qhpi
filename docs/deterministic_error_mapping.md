# Deterministic Error Mapping

## Scope

`src/qhpi_errors.ds` provides stable failure-to-error-code mapping and escalation behavior.

## Stable Error Codes

Implemented code space:

- `Q_ERR_DECOHERENCE_EXCEEDED`
- `Q_ERR_CALIBRATION_INVALID`
- `Q_ERR_RESOURCE_UNAVAILABLE`
- `Q_ERR_HARDWARE_FAILURE`
- `Q_ERR_GATE_UNSUPPORTED`
- `Q_ERR_MEASUREMENT_FAILURE`
- `Q_ERR_NO_CLONE_VIOLATION`

## Mapping Rules

`map_provider_failure` deterministically resolves provider state inputs into a single error code with strict precedence.

## Error Reports

`error_report_token` produces deterministic signed report metadata:

- job id
- provider id
- error code
- metadata
- logical timestamp
- signature

## Escalation

`escalation_action` maps error code + rollback context to deterministic action:

- none
- retry
- rollback
- deregister provider

## Test Coverage

`src/qhpi_tests.ds` validates stable mappings and deterministic digest behavior.
