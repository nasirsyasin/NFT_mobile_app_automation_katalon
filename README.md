# NFT Mobile App Automation

[![Katalon](https://img.shields.io/badge/Katalon%20Studio-5.9.0%2B-4B6BFB)](https://katalon.com/)
[![Platform](https://img.shields.io/badge/platform-mobile-2EA44F)](https://github.com/)
[![Security](https://img.shields.io/badge/secrets-sanitized-success)](#security)

A maintainable Katalon Studio project for mobile application quality assurance, functional testing, and regression testing.

> **Repository status:** This repository contains the reusable project foundation and configuration. Test cases and suites can be added under the standard Katalon project structure as the automation scope grows.

## Contents

- [Overview](#overview)
- [Technology](#technology)
- [Project structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Quick start](#quick-start)
- [Configuration](#configuration)
- [Execution](#execution)
- [Development guidelines](#development-guidelines)
- [CI/CD](#cicd)
- [Security](#security)
- [License](#license)

## Overview

The project provides a clean starting point for automating a mobile NFT application with Katalon Studio. It supports local devices, emulators, and remote WebDriver or device-farm execution when the required environment values are supplied at runtime.

The repository is designed to keep source code, project metadata, reusable keywords, and safe configuration templates in version control while keeping credentials and generated execution artifacts local.

## Technology

| Component | Details |
| --- | --- |
| Automation tool | Katalon Studio 5.9.0 or later |
| Language | Groovy for custom keywords and automation logic |
| Project type | Generic Katalon project |
| Mobile execution | Local device, emulator, or remote device provider |
| Remote execution | Selenium Remote WebDriver-compatible endpoint |

## Project structure

| Path | Purpose |
| --- | --- |
| `katalon_NFT_project.prj` | Katalon project metadata and source-folder configuration |
| `Include/config/` | Project logging configuration |
| `Libs/CustomKeywords.groovy` | Reusable custom keywords |
| `Libs/internal/` | Katalon-generated global-variable support |
| `Profiles/` | Katalon execution profiles |
| `settings/external/` | External execution and database settings |
| `settings/internal/` | Katalon execution and integration settings |
| `console.properties.example` | Safe local configuration template |
| `Reports/` | Local Katalon-generated reports; excluded from Git |
| `bin/` | Local compiled output; excluded from Git |

## Prerequisites

- Katalon Studio 5.9.0 or later
- Android or iOS tooling when running against a local device or emulator
- An available application build and test data
- A configured device, emulator, Selenium Grid, or supported device-farm account

## Quick start

1. Clone the repository.
2. Open `katalon_NFT_project.prj` in Katalon Studio.
3. Create a local configuration file from the supplied template:

   ```text
   console.properties.example → console.properties
   ```

4. Configure the target device or remote execution endpoint locally.
5. Select the appropriate execution profile in `Profiles/`.
6. Run the required test case or test suite from Katalon Studio.

## Configuration

Environment-specific values must remain outside the public repository.

The local `console.properties` file supports values such as:

- Remote WebDriver URL and execution type
- Device and emulator identifiers
- Device-farm credentials
- Test management and reporting integration identifiers
- Tunnel or environment settings

Use `console.properties.example` as the starting point. Store credentials in a secure secret manager or protected CI/CD variables. Never commit passwords, access tokens, API keys, private URLs, personal data, or device credentials.

## Execution

### Local execution

1. Start the required emulator or connect the test device.
2. Confirm that Katalon Studio can detect the device.
3. Select the desired profile and test scope.
4. Run the test from Katalon Studio.

### Remote execution

1. Configure the remote WebDriver URL and device capabilities locally.
2. Add provider credentials through protected environment variables or the local properties file.
3. Verify network access to the remote execution service.
4. Run the selected test scope and review results locally or in the protected CI artifact store.

## Development guidelines

- Keep reusable automation logic in `Libs/CustomKeywords.groovy`.
- Add test cases, test suites, and test objects using Katalon Studio conventions.
- Use descriptive names for test cases, profiles, keywords, and test objects.
- Keep environment-specific configuration outside tracked source files.
- Do not commit generated reports, compiled binaries, screenshots, or sensitive execution logs.
- Review staged changes before every push.

## CI/CD

The project can be integrated into a CI/CD pipeline by invoking the supported Katalon execution environment and injecting configuration at runtime. A production pipeline should:

- Retrieve credentials from the CI/CD secret store.
- Avoid printing secrets in commands or logs.
- Execute a defined test suite or test collection.
- Publish test results as protected build artifacts.
- Clean up temporary configuration files after execution.

## Security

This repository is prepared as a sanitized public project template. The `.gitignore` file excludes local credentials, generated reports, compiled output, logs, and IDE metadata.

Before publishing or mirroring the repository:

1. Scan the complete Git history for credentials and private data.
2. Revoke and rotate any credential that may have been exposed.
3. Remove sensitive content from Git history when necessary.
4. Confirm that only sanitized configuration templates are committed.

## License

Add the appropriate license and ownership information before public distribution.
