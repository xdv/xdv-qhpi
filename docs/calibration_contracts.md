# Calibration Contracts

## Scope

`src/qhpi_calibration.ds` implements calibration contract tokenization and validity semantics.

## Contract Model

`calibration_contract_token` models:

- contract id
- provider id
- calibration profile id
- valid-from and valid-until logical times
- error bounds
- stability metadata
- signature

## Validation

`verify_calibration_contract` performs deterministic recomputation and token equality check.

## Expiration Handling

- `can_accept_new_jobs` requires active calibration window.
- `active_job_completion_allowed` supports bounded tolerance window for in-flight jobs.
- `recalibration_required` deterministically flags expiry state.

These semantics implement XDV-060 calibration gating and expiration behavior.
