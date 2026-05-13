playwright-sample-project
Overview:
This is a sample automation project built with Playwright and TypeScript, using the Playwright Test Runner to execute test cases. The framework follows a Data-Driven approach, separating test logic from test data. This allows the same test scripts to run against multiple sets of test data, significantly reducing script duplication compared to a modular framework.

Test data is stored in external Excel sheets, which the scripts read during execution. For demonstration purposes:

UI test cases are implemented on advantageonlineshopping.com.
API test cases are implemented using both SOAP and REST endpoints.
Features
Built-in support for UI, API (SOAP & REST), and Database (MSSQL, DB2, Oracle) automation.

Cross-browser execution (Chrome, Firefox, Edge, WebKit).

Test data and execution control via Excel sheets (choose which tests to run and in which mode).

Data transfer supported between test cases.

Utilities for file downloads and PDF validation (including masking of dynamic content).

Generates multiple reports:

Playwright HTML Report
Allure Report
JUnit Report (XML format)
Allure & Playwright reports include snapshots and video on test failure.

Detailed execution logs stored in log files.

Run tests locally in Playwright’s UI Mode with watch & debug capabilities.

Centralized configuration in playwright.config.ts.

Runtime environment variable management via .env.

Simple integration with CI/CD tools such as Jenkins.

Supported Browsers
Chrome (default)
Firefox
Microsoft Edge
WebKit (Safari engine)
Run Mode Details
Mode	Excel Value	Description
Normal	(blank)	Runs all tests sequentially.
Serial	serial	Runs sequentially; stops execution on first failure.
Parallel	parallel	Runs tests in parallel; ideal for independent test scenarios.
Project Structure
playwright-sample-project/
│
├── src/                         # Source code
│   ├── advantage/               # UI Automation (Advantage Online Shopping)
│   │   ├── constants/           # Constants & test data mappings
│   │   ├── pages/               # Page Object Models
│   │   └── steps/               # Step actions classes
│   │
│   ├── API/                     # API Automation
│   │   ├── REST/                # REST API tests & helpers
│   │   │   ├── constants/       # REST-specific constants
│   │   │   └── steps/           # REST-specific step actions classes
│   │   │
│   │   └── SOAP/                # SOAP API tests & helpers
│   │       ├── constants/       # SOAP-specific constants
│   │       └── steps/           # SOAP-specific step actions classes
│   │
│   ├── database/                # Database interaction utilities
│   │       ├── constants/       # Database-specific constants
│   │       └── steps/           # Database-specific step actions classes
│   ├── framework/               # Core framework utilities
│   └── resources/               # Shared resources
│       ├── API/                 # API payloads
│       ├── data/                # Test data files
│       └── pdf/                 # PDF files for validation
│
├── tests/                       # Test specifications (.spec.ts)
│
├── test-results/                # Output of test executions
│   ├── downloads/               # Downloaded files during tests
│   ├── failure/                 # Failure screenshots & artifacts
│   ├── logs/                    # Execution logs
│   ├── pdf/                     # PDF comparison results
│   ├── report/                  # Allure / HTML reports
│   └── results/                 # Playwright HTML results
│
├── .env                         # Environment variables
├── .eslintignore                # ESLint ignore rules
├── .eslintrc.json               # ESLint configuration
├── .gitignore                   # Git ignore rules
├── package.json                 # Project dependencies & scripts
├── package-lock.json            # Lock file
└── playwright.config.ts         # Playwright configuration
Getting Started
1. Installation
Install Node.js (v22+).


Install dependencies:

npm ci
2. Test Creation
Create a new test file with .spec.ts extension. Example: LoginTest.spec.ts
In the testData Excel file, create a sheet with the same name. Example: LoginTest
Update the execution sheet (e.g., Regression) to include the new test case, setting values for run, mode, etc.
3. Execution
To run test suite use below command.

npm run create:suite SHEET=<SheetName> && npm test
Note: SheetName needs to be updated (Example: Regression).

To run individual test locally use below command.

set TEST_NAME=<TestFileName> && npm run local:test
Note: Using set command we are setting the local TestFileName (Example: LoginTest ).

Run an individual test in UI Mode:

set TEST_NAME=<TestFileName> && npm run local:test:ui
Change environment variables at runtime (example: set browser to Edge):

set BROWSER=edge
Generate Allure report:

npm run report
⚠️ Important Note
All commands shown above are written for Windows Command Prompt.

4. Reports & Logs
Playwright HTML Report:

test-results/results/index.html
Execution logs:

test-results/logs/execution.log
