# Verification commands

Suggest commands for the user to run; do not run them yourself. Always prefer the project's own scripts or task runner (for example `npm run test`, `make test`, or `just check`) over the generic commands below. Only suggest a tool the project actually uses, based on its config files and lockfiles.

For each command, tell the user what success and failure look like, and ask them to paste the output if something fails.

## JavaScript / TypeScript

| Check | Command | Success looks like |
|---|---|---|
| Tests | `npm test`, `pnpm test`, or `yarn test` (match the lockfile) | All tests pass, exit code 0 |
| Single test file | `npx vitest run path/to/file.test.ts` or `npx jest path/to/file.test.ts` | That file's tests pass |
| Type check | `npx tsc --noEmit` | No output |
| Lint | `npx eslint path/to/file.ts` | No errors reported |

Pitfalls to point out: `any` that hides a real type, missing `await` on promises, and mutating React state directly.

## Python

| Check | Command | Success looks like |
|---|---|---|
| Tests | `pytest` (or `uv run pytest` / `poetry run pytest`) | All tests pass |
| Single test | `pytest path/to/test_file.py::test_name -x` | That test passes |
| Type check | `mypy path/` or `pyright` | `Success: no issues found` / `0 errors` |
| Lint | `ruff check path/` | `All checks passed!` |

Pitfalls to point out: mutable default arguments, bare `except:`, and running code outside the project's virtual environment.

## Go

| Check | Command | Success looks like |
|---|---|---|
| Build | `go build ./...` | No output |
| Tests | `go test ./...` | `ok` for every package |
| Vet | `go vet ./...` | No output |

Pitfalls to point out: ignored `err` return values and loop-variable capture in goroutines on older Go versions.

## Rust

| Check | Command | Success looks like |
|---|---|---|
| Compile check | `cargo check` | `Finished` with no errors |
| Tests | `cargo test` | `test result: ok` |
| Lint | `cargo clippy` | No warnings |

Pitfalls to point out: `.unwrap()` in non-test code, and unnecessary `.clone()` to work around the borrow checker. When a borrow error appears, explain what the compiler message is saying.

## PHP

| Check | Command | Success looks like |
|---|---|---|
| Syntax | `php -l path/to/file.php` | `No syntax errors detected` |
| Tests | `vendor/bin/phpunit` or `vendor/bin/pest` (Laravel: `php artisan test`) | All tests pass |
| Static analysis | `vendor/bin/phpstan analyse` | `[OK] No errors` |

## Ruby

| Check | Command | Success looks like |
|---|---|---|
| Tests | `bundle exec rspec` or `bin/rails test` | `0 failures` |
| Lint | `bundle exec rubocop path/` | `no offenses detected` |

## Java / Kotlin

| Check | Command | Success looks like |
|---|---|---|
| Build and tests (Gradle) | `./gradlew test` | `BUILD SUCCESSFUL` |
| Build and tests (Maven) | `mvn test` | `BUILD SUCCESS` |

## When there is no automated check

Give manual steps instead: what to open or run, what to click or call, and what the correct result looks like. For example: "Start the app with `npm run dev`, open http://localhost:3000/settings, toggle dark mode, and check that the page background turns dark and stays dark after a reload."
