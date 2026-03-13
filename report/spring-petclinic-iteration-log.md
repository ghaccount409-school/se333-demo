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
