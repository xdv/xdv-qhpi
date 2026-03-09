# Provider Registration and Attestation

## Scope

`src/qhpi_provider.ds` implements XDV-060 provider registration and attestation boundary checks.

## Registration

`register_provider` requires:

- valid provider id
- firmware measurement hash
- hardware topology metadata
- logical qubit capacity
- supported gate profile
- decoherence profile
- post-quantum signature
- logical timestamp

Registration deterministically succeeds only when all required fields are present and valid.

## Attestation

- `attestation_token` builds deterministic attestation material from provider identity + nonce + timestamp.
- `verify_attestation` compares presented token against deterministic recomputation.

## Capability Declaration

`provider_capability_token` models stable capability declaration including:

- max logical qubits
- gate profile
- calibration profile id
- max circuit depth
- measurement modes

This supports contract gating before Q job submission.
