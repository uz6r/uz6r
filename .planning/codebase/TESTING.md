# Testing Patterns

**Analysis Date:** 2026-05-25

## Current State

**This repository contains no test files, no test configuration, and no test infrastructure.** It is a personal GitHub profile README repository consisting only of `README.md` and `tracepace/public/preview.png`.

The developer's stated testing tools (from `README.md` stack section) are:
- **Jest** — TypeScript/JavaScript testing
- **Pytest** — Python testing

No test files matching `*.test.*`, `*.spec.*`, `*_test.go`, or `test_*.py` exist anywhere in the repository.

## Test Framework (Expected)

Based on the developer's stated stack and professional experience:

| Framework | Language | Expected Config File |
|-----------|----------|---------------------|
| Jest | TypeScript/JavaScript | `jest.config.ts` or `jest.config.js` |
| Pytest | Python | `pytest.ini`, `pyproject.toml` (pytest config section), or `setup.cfg` |
| Go testing | Go | Standard `testing` package (no external config) |

**No existing config files for any of these frameworks are present.**

## Test Infrastructure

**CI/CD:**
- GitHub Actions is listed in the `README.md` stack (badge for `github_actions`)
- No `.github/workflows/` directory exists
- No CI test pipeline configured

**No testing infrastructure detected:**
- No coverage configuration
- No test helper libraries
- No fixtures or factories
- No mocking setup

## Test Location & Organization

**Convention to establish** (based on standard practices for each part of the developer's stack):

**Next.js / TypeScript projects:**
```
src/
  __tests__/
    components/
      ComponentName.test.tsx
    pages/
      page.test.tsx
    utils/
      utility.test.ts
  components/
    ComponentName.tsx
```

Or co-located pattern (also common):
```
src/
  components/
    ComponentName.tsx
    ComponentName.test.tsx
```

**Python projects:**
```
tests/
  conftest.py
  test_models.py
  test_graphql/
    test_queries.py
    test_mutations.py
  test_services/
```

**Go projects:**
```
internal/
  service/
    service.go
    service_test.go
```

## Testing Patterns (Expected, Based on Stack)

### TypeScript / Jest

**Expected structure:**
```typescript
import { render, screen } from '@testing-library/react';
import { describe, it, expect, vi } from 'vitest';  // or jest globals
import Component from './Component';

describe('Component', () => {
  it('renders the expected content', () => {
    render(<Component />);
    expect(screen.getByText('content')).toBeInTheDocument();
  });

  it('handles error state gracefully', () => {
    // mock and assert
  });
});
```

**Expected mocking approach:**
- `jest.mock()` / `vi.mock()` for module mocking
- `@testing-library/react` for component tests (React Testing Library)
- MSW (Mock Service Worker) for API mocking — common in Next.js/GraphQL stacks
- `faker` or `@faker-js/faker` for test data generation

### Python / Pytest

**Expected structure:**
```python
import pytest
from sqlalchemy import create_engine
from myapp.models import User

@pytest.fixture
def db_session():
    engine = create_engine("sqlite:///:memory:")
    # setup
    yield session
    # teardown

def test_create_user(db_session):
    user = User(name="test")
    db_session.add(user)
    db_session.commit()
    assert user.id is not None
```

**Expected patterns:**
- `conftest.py` for shared fixtures
- `pytest.fixture` for test setup/teardown (matches SQLAlchemy session patterns)
- `pytest.mark.parametrize` for data-driven tests
- `pytest-cov` for coverage reporting (common in professional Python projects)
- `pytest-asyncio` for async GraphQL endpoint testing (matches Strawberry GraphQL stack)

### Go

**Expected structure:**
```go
package service

import "testing"

func TestProcessActivity(t *testing.T) {
    // Arrange
    input := ActivityData{...}
    
    // Act
    result, err := ProcessActivity(input)
    
    // Assert
    if err != nil {
        t.Fatalf("unexpected error: %v", err)
    }
    if result.ID == "" {
        t.Error("expected non-empty ID")
    }
}
```

## Test Data & Fixtures

**No test data files exist in this repository.** Expected locations based on stack:
- `test/fixtures/` or `__fixtures__/` for TypeScript
- `tests/data/` or `tests/fixtures/` for Python
- `testdata/` for Go

For the TracePace project described in `README.md`:
- `.fit` and `.gpx` sample activity files expected in `testdata/` directory
- Sample poster output for visual regression testing
- RDP (Ramer-Douglas-Peucker) algorithm test vectors

## CI/CD Testing Integration

**Expected setup** (GitHub Actions, per `README.md`):

```yaml
# .github/workflows/test.yml
name: Test
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
      - run: npm ci
      - run: npm test
```

Not yet configured — no `.github/workflows/` directory.

## Coverage Requirements

**Not configured.** Recommended targets based on professional standards:
- TypeScript/Next.js: ≥80% line coverage
- Python: ≥80% line coverage
- Go: ≥80% coverage for critical paths (parse, simplify, render)

## Test Types

**None present.** Expected distribution for a full-stack project matching this developer's profile:

| Type | % of Tests | Focus |
|------|-----------|-------|
| Unit | ~70% | Isolated function/component tests |
| Integration | ~20% | API routes, database operations, GraphQL resolvers |
| E2E | ~10% | Critical user flows (Playwright or Cypress) |

## Recommendations

1. **Establish testing as code is added** — this repo currently has zero application code; testing should be introduced alongside the first source files
2. **Create `.github/workflows/test.yml`** when the first application code is committed — enables CI test runs on push/PR
3. **Choose between Jest and Vitest** for TypeScript — Vitest is increasingly standard in the Vite/Next.js ecosystem; the `README.md` lists Vite in the stack
4. **Add `conftest.py`** as the foundation for Python test infrastructure if Python services are added
5. **Add Go `testing` package tests** for the TracePace Go parser binary — `.fit`/`.gpx` parsing is the most critical logic that needs test coverage
6. **Use `testdata/` for Go** with sample `.fit` and `.gpx` files for parser testing
7. **Configure `pytest-cov` or `jest --coverage`** to enforce coverage thresholds from the start
8. **Add a `Makefile` or `package.json` scripts** section with `test`, `test:watch`, `test:coverage` commands
9. **Adopt Golden File testing** for the RDP vector simplification and poster rendering output — compare simplified paths against known-good reference outputs

---

*Testing analysis: 2026-05-25*
