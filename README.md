# Enterprise Workflow Playwright Automation Framework

This repository contains a scalable, enterprise-grade UI and workflow automation framework built using Playwright and TypeScript. It is designed to validate complex, multi-step business logic, state transitions, and cross-system data flows.

---

## Key Differentiators & Positioning
* Beyond Basic UI Testing: Focused on end-to-end workflow validation, business rule verification, and structural data integrity rather than simple element clicking.
* Layered Architecture: Implements a strict 3-layer pattern (Pages -> Flows -> Tests) to minimize script maintenance time and maximize code reusability.
* Continuous Integration: Integrated with GitHub Actions to execute automated regression and smoke test suites on every code push as a quality gate.

---

## Technology Stack
* Automation Core: Playwright, Playwright Test Runner
* Language: TypeScript, Node.js
* Design Pattern: Page Object Model (POM), Workflow-Based Architecture
* CI/CD: GitHub Actions
* Reporting: Playwright HTML Reporter, Trace Viewer, Automated Screenshots/Videos on Failure

---

## Framework Architecture

The framework follows a clean, decoupled layered design:

```text
Tests (Smoke, Regression, Features)
  ↓
Flows (Business Workflow Orchestration)
  ↓
Pages (UI Interactions & Locators)
  ↓
Playwright Engine

Directory Structure

enterprise-workflow-playwright-framework/
├── .github/
│   └── workflows/
│       └── playwright.yml         # CI/CD Pipeline configuration
├── constants/
│   └── appConstants.ts            # Application-wide constants and configurations
├── flows/
│   ├── manageOrder/               # Multi-step business workflow actions
│   │   ├── batchDuplication.flow.ts
│   │   ├── executionSet.flow.ts
│   │   └── orderManagement.flow.ts
│   └── sync/
│       └── dataSynchronization.flow.ts
├── pages/
│   ├── manageOrder/               # Page Object Model locators and low-level actions
│   │   ├── BatchDuplicationPage.ts
│   │   ├── ExecutionSetPage.ts
│   │   └── OrderManagementPage.ts
│   ├── LoginPage.ts
│   └── DataSyncPage.ts
├── tests/
│   ├── Features/                  # Feature-specific test cases
│   ├── Regression/                # End-to-end regression suites
│   ├── Smoke/                     # Critical path health checks
│   └── setup/                     # Global setup and authentication states
├── utils/
│   └── testData.ts                # Data management and helper functions
├── playwright.config.ts           # Global Playwright configuration
├── package.json                   # Project dependencies and npm scripts
├── tsconfig.json                  # TypeScript compiler options
└── README.md
