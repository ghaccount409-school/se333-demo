# Spring PetClinic Iterative Testing Log

- **Target repository tested:** https://github.com/spring-projects/spring-petclinic
- **Results repository:** https://github.com/ghaccount409-school/se333-demo

## Iteration 2 — 2026-03-12

- **Command:** `mvn test jacoco:report "-Dtest=!PostgresIntegrationTests,!MySqlIntegrationTests"`
- **Outcome:** Build success
- **Tests:** 55 run, 0 failures, 0 errors, 0 skipped
- **Coverage (JaCoCo):**
  - Line: `94.26% (279/296)`
  - Instruction: `90.49% (1018/1125)`
- **Notes:** Excluded environment-bound Postgres/MySQL integration tests for stable iteration signal.

## Iteration 3 — 2026-03-12

- **Command:** `mvn test jacoco:report "-Dtest=!PostgresIntegrationTests"`
- **Outcome:** Build success
- **Tests:** 57 run, 0 failures, 0 errors, 2 skipped
- **Coverage (JaCoCo):**
  - Line: `94.26% (279/296)`
  - Instruction: `90.49% (1018/1125)`
- **Notes:** Narrowed exclusions to only Postgres integration tests; MySQL tests executed and were skipped by environment conditions.

## Iteration 4 — 2026-03-12

- **Command:** `mvn test jacoco:report`
- **Outcome:** Build failure (strict full-suite run)
- **Tests:** 58 run, 0 failures, 1 error, 2 skipped
- **Blocking error:** `PostgresIntegrationTests.available` -> `InvalidPathException: Illegal char <:> at index 13: JAVA_HOME = C:\Program Files\Java\jdk-21.0.10`
- **Notes:** This iteration intentionally verifies strict full-suite behavior and preserves failure evidence in git history.

## Iteration 5 — 2026-03-12

- **Command:** `mvn test jacoco:report` (with temporary `PATH` sanitization removing malformed `JAVA_HOME = ...` token)
- **Outcome:** Build success (strict full-suite run)
- **Tests:** 57 run, 0 failures, 0 errors, 2 skipped
- **Coverage (JaCoCo):**
  - Line: `94.26% (279/296)`
  - Instruction: `90.49% (1018/1125)`
- **Notes:** `PostgresIntegrationTests` no longer throws `InvalidPathException`; with no valid Docker environment, it is skipped instead of erroring.
