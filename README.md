# Contractual SemVer

Contractual SemVer libraries distinguish,
in a machine-readable format,
which behaviors are guaranteed and which are implementation details.

Contractual SemVer aims to more rigorously define SemVer's language about 
"backwards compatability".

Background links: [Semantic Versioning (SemVer)](https://semver.org/) and
[Software contracts](https://en.wikipedia.org/wiki/Design_by_contract)


# Details

Libraries may increment **minor** and **patch** versions when the contracts
are not changed, or are **weakened**. Some examples:

* A precondition is changed to newly allow a null argument.
* A postcondition is added, declaring that a negative number will never be returned.

A **major** version increment is needed when contracts are **strengthened**.

The manner in which contracts are expressed may vary by language and contract
library.

Contractual SemVar libraries use machine-understandable contracts when possible,
but may fall back to natural language contracts as needed.


## Benefits for library authors

* Minimize discussion about whether a major version increment is required.
* Reduce the probability that clients become dependent on implementation details.
* Communicate your committment to responsible behavioral evolution.

If you follow Contractual SemVer, let your consumers know by adding a
[![SemVer: Contractual](https://img.shields.io/badge/SemVer-Contractual-301818.svg)](https://github.com/pschanely/contractual-semver)
badge:
```
[![SemVer: Contractual](https://img.shields.io/badge/SemVer-Contractual-301818.svg)](https://github.com/pschanely/contractual-semver)
```


## Benefits for library consumers

* Know which behaviors you can expect over time.
* Use the library's contracts to decide version constraints or bounds.
* Use tools like CrossHair to **automatically** detect whether you're relying on implementation details.



# Contractual SemVer Tools

Find contract libraries for your programming language on wikipedia's
[design-by-contract page](https://en.wikipedia.org/wiki/Design_by_contract#Language_support).

Additionally, some of these tools may be useful for contractual SemVer specifically:

* [CrossHair (Python)](https://github.com/pschanely/CrossHair).
  Library authors can use CrossHair's symbolic execution engine to verify their contracts.
  Library authors can ensure new minor and patch releases don't weaken contracts with the `diff_contracts` command.
  Library consumers can use CrossHair to automatically detect when they are dependent on implementation details.
* (Make a pull request to add more ...)


