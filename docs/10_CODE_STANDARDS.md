# CODE STANDARDS

Version: 1.0

---

# PURPOSE

This document defines the mandatory coding standards for the entire project.

Every source file must comply with these rules.

No exceptions.

---

# GENERAL PRINCIPLES

Code must be:

- Readable
- Predictable
- Maintainable
- Testable
- Reusable
- Self-documenting

Always prefer clarity over cleverness.

---

# SOFTWARE PRINCIPLES

The project must follow:

- SOLID
- DRY
- KISS
- YAGNI
- Clean Architecture
- Feature First
- Separation of Concerns
- Composition over Inheritance

---

# LANGUAGE

All source code must use:

TypeScript

Strict Mode enabled.

JavaScript files are prohibited.

---

# TYPESCRIPT

Strict mode required.

Avoid:

any

unknown (unless justified)

non-null assertions (!)

type assertions (as) unless unavoidable.

Prefer explicit types.

Use interfaces for contracts.

Use type aliases for unions.

---

# FILE STRUCTURE

One primary responsibility per file.

Maximum file size:

300 lines (recommended)

500 lines (absolute maximum)

Large modules must be split.

---

# FUNCTION RULES

Functions should:

Do one thing.

Have descriptive names.

Avoid side effects.

Prefer pure functions.

Maximum recommended length:

50 lines.

---

# CLASS RULES

Classes must:

Have one responsibility.

Use constructor injection.

Avoid static mutable state.

Prefer services over utility classes when business logic exists.

---

# NAMING CONVENTIONS

Variables

camelCase

Functions

camelCase

Classes

PascalCase

Interfaces

PascalCase

Enums

PascalCase

Constants

UPPER_SNAKE_CASE

Files

kebab-case

Folders

kebab-case

---

# IMPORTS

Use absolute imports where configured.

Avoid circular dependencies.

Group imports:

Node

Third-party

Shared

Internal

Relative

Unused imports prohibited.

---

# COMMENTS

Comments explain:

Why

Never:

What

Obvious comments are prohibited.

TODO prohibited.

FIXME prohibited.

HACK prohibited.

---

# ERROR HANDLING

Never ignore errors.

Use explicit exceptions.

Catch only when handling.

Never swallow exceptions.

---

# LOGGING

Structured logging only.

No console.log in production.

Allowed levels:

Debug

Info

Warn

Error

---

# ASYNC CODE

Prefer:

async/await

Avoid nested promises.

Avoid callback patterns.

Always handle rejected promises.

---

# VALIDATION

Frontend

Zod

Backend

DTO

class-validator

No manual validation duplication.

---

# API DESIGN

REST conventions.

Plural resource names.

Correct HTTP verbs.

Consistent response format.

Consistent error format.

---

# DATABASE

Access only through Prisma.

Repositories encapsulate persistence.

Business logic never accesses Prisma directly.

---

# FRONTEND

Component-driven architecture.

Prefer composition.

Reusable components first.

Avoid duplicated UI.

Use controlled forms.

Separate presentation from business logic.

---

# REACT RULES

Functional Components only.

Hooks only.

No class components.

No prop drilling beyond reasonable depth.

Use custom hooks for reusable logic.

---

# STATE MANAGEMENT

Server State

TanStack Query

Client State

Zustand

Forms

React Hook Form

No duplicated state.

---

# CSS

TailwindCSS only.

No inline styles except dynamic values.

No duplicated utility groups.

Reusable UI abstractions encouraged.

---

# ANIMATIONS

Framer Motion.

No CSS animation duplication.

Animation values centralized.

---

# TESTING

Every critical feature requires tests.

Business logic coverage prioritized.

Do not mock business logic unnecessarily.

---

# PERFORMANCE

Lazy loading.

Memoization only when beneficial.

Avoid unnecessary renders.

Optimize image loading.

Virtualize long lists.

---

# ACCESSIBILITY

Semantic HTML.

Keyboard support.

Visible focus.

Accessible labels.

Minimum touch target:

44x44 px

---

# GIT CONVENTIONS

Branch naming:

feature/

fix/

refactor/

docs/

test/

Conventional Commits required.

Examples

feat:

fix:

refactor:

docs:

test:

---

# LINTING

ESLint required.

No warnings allowed.

Build fails on lint errors.

---

# FORMATTING

Prettier required.

Formatting is automatic.

No manual formatting differences.

---

# DEPENDENCIES

Every dependency must:

Be maintained.

Be actively supported.

Have a clear purpose.

Unused dependencies prohibited.

---

# DOCUMENTATION

Every module requires:

README (where appropriate)

Public API documentation

Meaningful names

Minimal onboarding effort

---

# CODE REVIEW CHECKLIST

Before merging:

✔ Builds successfully

✔ Lint passes

✔ Tests pass

✔ Types pass

✔ No TODO

✔ No FIXME

✔ No dead code

✔ No duplicate logic

✔ No unused imports

✔ No unnecessary dependencies

✔ Documentation updated

---

# DEFINITION OF DONE

Code is considered complete only when:

- It follows every rule in this document.
- It compiles without warnings.
- It passes linting.
- It passes type checking.
- It passes all tests.
- It contains no placeholder logic.
- It contains no prohibited patterns.
- It is production-ready.
