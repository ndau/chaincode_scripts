# ntrd Target Price sales

- Permitted Transactions: ChangeValidation, ReleaseFromEndowment, Transfer, TransferAndLock
- Validation Keys: 4 ntrd Keys (indices `0`-`3`) plus 3 pre-BPC Keys (`4`-`6`)
- Validation Rules:

    - ChangeValidation: 1 of first 2 ntrd signatures and 1 of second 2 ntrd signatures, or 2 pre-BPC signatures
    - ReleaseFromEndowment:
        - Up to 5,000 ndau: 1 of first 2 ntrd signatures
        - 5,000 - 20,000 ndau: 1 of first 2 ntrd signatures and 1 of second 2 ntrd signatures
        - More than 20,000 ndau: 1 of first 2 ntrd signatures and 1 of second 2 ntrd signatures and 1 of pre-BPC
    - Transfer and TransferAndLock:
        - Up to 20,000 ndau: 1 of first 2 ntrd signatures
        - More than 20,000 ndau: 1 of first 2 ntrd signatures and 1 of second 2 ntrd signatures
