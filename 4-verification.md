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
| CHN-04, CHN-05, CHN-07, CHN-08, CHN-09    | C      | Validation results and reject reasons compared with Bitcoin Core.         |
| BSY-14                                    | C      | Locator heights compared with Bitcoin Core's `GetLocator`.                |
| STO-02, STO-03, STO-04, STO-05            | I, A   | Store layout reviewed against the data that changes together.             |
| STO-06 to STO-10                          | I      | Store and table definitions reviewed in code.                             |
| STO-11 to STO-14                          | I, T   | Write order reviewed in code; result tested by stopping the node between steps. |
| DES-01 to DES-05                          | I      | Module boundaries reviewed in code.                                       |
| DES-06                                    | I, T   | Bound reviewed in code; full queue tested.                                |
| DES-07 to DES-12                          | I      | Engine, profiles, sync mode and components reviewed in code.              |
| ATT-02                                    | T      | Tested with an invalid block on `regtest`.                                |
| ATT-03                                    | T      | Tested by stopping the node during a reorg on `regtest`.                  |
| ATT-05                                    | I, A   | Follows from STO-01 and STO-05.                                           |
| EXT-07, EXT-08, NET-20, CHN-19, BSY-29    | T, I   | Configuration parsing tested; defaults reviewed.                          |
