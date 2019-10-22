# Axiom

## Axiom Foundation Release and Issuance

- Permitted Transactions: ChangeValidation, ReleaseFromEndowment, RecordEndowmentNAV, Transfer, TransferAndLock, Issue
- Validation Keys: 3 Axiom Foundation keys and 9 BPC keys
- Validation Rules:

    - ChangeValidation: 2 Axiom signatures and 3 BPC signatures, or 6 BPC signatures
    - RecordEndowmentNAV: 1 Axiom signature
    - ReleaseFromEndowment, Transfer, TransferAndLock, Issue:
        - <= 30,000 ndau: 1 Axiom signature
        - More than 30,000 ndau: 2 Axiom signatures
