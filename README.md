# Validation Scripts

This repo contains a number of chaincode validation scripts. In general, two user stories are currently supported:

- Special accounts associated with Ndau get bespoke scripts
- A selection of generic validation scripts is available for use by ndau users

## Validation Context

All validation scripts receive a standardized context on initialization. This context comes in the form of entries present on the stack at initialization.

It is sometimes useful to write out the expected values on the stack to aid in writing chaincode. Conventionally, when writing the stack horizontally, the bottom of the stack is on the left, and the top is on the right. When writing the stack vertically, it is inverted: the first item in the list is the bottom of the stack, and the last item of the list is the top.

Universal context for validation scripts:

- `acct`: a struct representing the "source" account associated with the transaction. For transactions associated with more than one account, this is always the account which pays the transaction fee.

- `tx`: a struct representing the transaction in question.

- `sigs`: a bitmask of signatures for this transaction. The bits of the bitmask are mapped to the validation signatures of the account such that when the public key at index `0` of the validation keys verifies one of the signatures in the signature set, bit `0` of the bitmask is set, and so on for all other keys.

### RFE Context

The `ReleaseFromEndowment` transaction has some special handling. The top of the RFE stack is identical to the standard context, but it has an additional field appended to the bottom::

- `dest`: a struct representing the destination account into which this RFE will release funds.

# Conventions

## Structure
* Chasm files should have the extension .chasm.
* Binary files will be generated with .chbin. (These are ignored by .gitignore)
* Test scripts to be run by crank should have the extension .crank.
* Test scripts should start with a load command, giving the relative path (from the script) to the .chbin file.

## Code style
* Code should be run through chfmt
* Functions should use CamelCase
* Constants should be named, and constant names should be UPPERCASE
* opcodes are in lowercase
* when explicitly failing a validation script, use the fail opcode
* remember that numeric zero is a good return and anything else is a failure
* to return the result of a conditional, use not instead of a conditional
