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
