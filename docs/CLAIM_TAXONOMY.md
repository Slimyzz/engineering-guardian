# Claim Taxonomy

| Claim type | Example | Evidence | Tier |
| --- | --- | --- | --- |
| TESTS_PASS | “All 4 tests passed” | Test command result and exit status | Provable |
| COMMAND_RUN | “I ran the tests directly” | Ordered transcript evidence | Provable |
| FILES_COMMITTED | “All changes were committed” | Repository commit state | Provable |
| COMMIT_REF | “Committed as `abc1234`” | Resolved commit reference | Provable |
| FILE_MODIFIED | “Saved as /home/kamil/code/add.py” | Repository or filesystem state | Provable |
| FILE_UNTOUCHED | “The config was not changed” | Repository diff and session evidence | Provable |
| SYMBOL_EXISTS | “Added `validate_claim`” | Parsed source or exact symbol lookup | Provable |
| DEPENDENCY_ADDED | “Added pytest” | Dependency manifest and lockfile | Provable |
| TEST_ADDED | “Added a regression test” | Test file structure and repository diff | Provable |
| ERROR_HANDLED | “The missing-file error is handled” | Relevant code and test evidence | Partial |
| BUG_FIXED | “Fixed the parsing bug” | Tests and observed behavior | Inferred |
| REFACTOR_SAFE | “The refactor preserves behavior” | Test results and code review | Inferred |

Only Provable claims may block. Partial and Inferred claims are advisory.
