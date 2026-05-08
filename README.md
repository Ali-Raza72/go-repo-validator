[README.md](https://github.com/user-attachments/files/27508301/README.md)
# 🔍 Go Repository Validator

A CLI tool written in Go that validates GitHub repositories for quality — checking Git hygiene, Docker setup, and test coverage. Outputs a scored report with actionable issues.

## Features

- ✅ Git analysis (branch, commit count, contributors, README, .gitignore)
- 🐳 Docker validation (Dockerfile, multi-stage builds, Docker Compose)
- 🧪 Test coverage detection (Go `_test.go` files)
- 📊 Quality score out of 100
- 📄 JSON report export

## Usage

```bash
# Validate current directory
go run main.go

# Validate a specific repo path
go run main.go /path/to/your/repo
```

## Example Output

```
🔍 Validating repository: /home/user/my-project

=== GIT INFO ===
  Branch       : main
  Commits      : 42
  Last Commit  : 2024-01-15 fix: resolve race condition in worker pool
  README       : true
  .gitignore   : true

=== DOCKER INFO ===
  Dockerfile        : true
  Multi-stage build : true
  Docker Compose    : true

=== TEST COVERAGE ===
  Has Tests   : true
  Test Files  : 3
    - handlers/user_test.go
    - services/auth_test.go
    - utils/parser_test.go

=== SCORE: 100/100 ===
✅ No issues found!

📄 Full report saved to repo-report.json
```

## Build

```bash
go build -o repo-validator main.go
./repo-validator /path/to/repo
```

## Why This Exists

Built as part of exploring LLM evaluation tooling — specifically how to automate quality checks on public GitHub repositories for use in training dataset validation pipelines.
