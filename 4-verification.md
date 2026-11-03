# 4 Verification

## 4.1 Methods

| Method | Name          | Meaning                                                                                                      |
|--------|---------------|--------------------------------------------------------------------------------------------------------------|
| T      | Test          | Automated test of the built node: unit test, or node run against Bitcoin Core peers on `regtest` or `signet`. |
| C      | Comparison    | Test against Bitcoin Core's behaviour or test vectors for the same input.                                    |
| I      | Inspection    | Review of the source code, build configuration or configuration files.                                       |
| A      | Analysis      | Reasoning over the specification and the code, where a test cannot produce the condition.                    |

## 4.2 Assignment

Every requirement is verified by Test (T) unless listed in Table 4-1.

Table 4-1. Requirements not verified by Test alone

| Requirements                              | Method | Note                                                                      |
|-------------------------------------------|--------|---------------------------------------------------------------------------|
| CHN-04, CHN-05, CHN-07, CHN-08, CHN-09, CHN-20, CHN-23 | C | Validation results, flags and reject reasons compared with Bitcoin Core. |
| CHN-21, CHN-22                            | C      | Chain work compared with Bitcoin Core's `GetBlockProof` and chain selection. |
| BSY-14                                    | C      | Locator heights compared with Bitcoin Core's `GetLocator`.                |
| STO-02, STO-03, STO-04, STO-05            | I, A   | Store layout reviewed against the data that changes together.             |
| STO-06 to STO-10                          | I      | Store and table definitions reviewed in code.                             |
| STO-11 to STO-14, STO-16                  | I, T   | Write order reviewed in code; result tested by stopping the node between steps. |
| DES-01 to DES-05                          | I      | Module boundaries reviewed in code.                                       |
| DES-06                                    | I, T   | Bound reviewed in code; full queue tested.                                |
| DES-07 to DES-12                          | I      | Engine, profiles, sync mode and components reviewed in code.              |
| ATT-02                                    | T      | Tested with an invalid block on `regtest`.                                |
| ATT-03                                    | T      | Tested by stopping the node during reorg mode on `regtest`.               |
| BSY-30, BSY-32                            | T      | Tested with a peer that does not answer, and one that answers `notfound`. |
| ATT-05                                    | I, A   | Follows from STO-01 and STO-05.                                           |
| EXT-07, EXT-08, NET-20, CHN-19, BSY-29    | T, I   | Configuration parsing tested; defaults reviewed.                          |
