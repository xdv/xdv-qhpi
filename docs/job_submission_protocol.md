# Job Submission Protocol

## Scope

`src/qhpi_job.ds` models Q job descriptor validation and submission checks.

## Descriptor

`job_descriptor_token` requires non-zero core identifiers and valid measurement specification.

Key fields include:

- job id
- process id
- resource contract id
- calibration contract id
- logical qubit count
- circuit pointer
- measurement spec
- decoherence budget
- capability id
- logical timestamp

## Submission Pipeline

`submit_job` enforces deterministic ordering of checks:

1. provider identity valid
2. provider attestation valid
3. resource contract active
4. calibration active
5. qubit capacity available
6. gate profile supported
7. decoherence budget satisfied
8. measurement spec valid
9. no-clone boundary check

The first failing condition returns stable status/error category.

## Measurement Result

`measurement_result_token` emits deterministic classical result metadata.
