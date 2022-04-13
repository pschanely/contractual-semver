# Contractual SemVer

Libraries that follow
[Semantic Versioning (SemVer)](https://semver.org/)
increment major version numbers when backwards-incompatible changes are
introduced.
It does not say, however, how we are to interpret "backwards compatibility."

**Contractual** SemVer uses the idea of
[Software contracts](https://en.wikipedia.org/wiki/Design_by_contract)
to let authors rigorously define "backwards compatibility" for their
libraries.


# Details

Contracts are expressed in various ways, depending on the language and contract
system.
Wikipedia's
[design-by-contract page](https://en.wikipedia.org/wiki/Design_by_contract#Language_support)
contains contract systems for many popular programming languages.

Contractual SemVer libraries use machine-understandable contracts when possible,
but may fall back to natural language contracts as needed.

Libraries may increment **minor** and **patch** versions when the contracts
are not changed, or are **weakened**. Some examples:

* A precondition is changed to newly allow a null argument.
* A postcondition is added, declaring that a negative number will never be returned.

A **major** version increment is needed when contracts are **strengthened**.




## Benefits for library authors

* Minimize discussion about whether a major version increment is required.
* Reduce the probability that clients become dependent on implementation details.
* Communicate your commitment to responsible behavioral evolution.

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

Additionally, some of these tools may be useful for **contractual** SemVer:

* [CrossHair (Python)](https://github.com/pschanely/CrossHair).
  Library authors can use CrossHair's symbolic execution engine to verify their contracts.
  Library consumers can use CrossHair to automatically detect when they are dependent on implementation details.
  See these [CrossHair docs](https://crosshair.readthedocs.io/en/latest/case_studies.html#contractual-semver) for more information.
* (Make a pull request to add more ...)
