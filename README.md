# Lago Mobile App Automation - Katalon Project

## Project Overview

This is a **Katalon test automation project** for the Lago mobile application. The project uses Katalon Studio to automate test cases for quality assurance and continuous testing of the Lago mobile app.

**Project Name:** katalon_lago_project  
**Project ID:** f08f49fd-a617-4951-9878-6e807e7b0eb7  
**Katalon Version:** 5.9.0+  
**Project Type:** Generic

---

## Project Structure

### Root Level Files

| File | Purpose |
|------|---------|
| `katalon_lago_project.prj` | Main Katalon project configuration file (XML) |
| `console.properties` | Console configuration and settings |

### Directory Structure

#### 1. **bin/** - Binary and Compiled Files
- `lib/` - Contains compiled libraries and dependencies
  - `internal/` - Internal Katalon libraries

#### 2. **Include/** - Test Source Files
Contains all source code and configuration for tests.

- **config/** - Configuration files
  - `log.properties` - Logging configuration
  
- **scripts/groovy/** - Groovy test scripts (referenced in project configuration)

- **features/** - BDD feature files (if using Behavior-Driven Development)

#### 3. **Libs/** - Custom Libraries and Keywords
- `CustomKeywords.groovy` - Custom keywords defined for the project
  - Reusable custom functions and utilities for test automation
  
- `internal/` - Internal library files
  - `GlobalVariable.groovy` - Global variables used across test cases

#### 4. **Profiles/** - Test Execution Profiles
- `default.glbl` - Default profile with global variables and settings
  - Contains environment-specific configurations
  - Settings for test execution environments (dev, staging, production, etc.)

#### 5. **Reports/** - Test Execution Reports
- `Self-healing/` - Katalon's self-healing mechanism
  - `broken-test-objects.json` - Contains locator information for self-healed objects

#### 6. **settings/** - Project Settings and Configuration
Contains various Katalon and execution settings.

- **external/** - External configuration files
  - `com.kms.katalon.composer.execution.settings.properties` - Test execution settings
  - `com.kms.katalon.core.db.DatabaseSettings.properties` - Database connection settings

- **internal/** - Internal Katalon settings
  - `com.kms.katalon.composer.testcase.properties` - Test case configuration
  - `com.kms.katalon.execution.properties` - Execution environment settings
  - `com.kms.katalon.execution.webui.properties` - Web UI execution settings
  - `com.kms.katalon.integration.analytics.properties` - Analytics integration settings
  - `com.kms.katalon.integration.qtest.properties` - qTest integration settings

#### 7. **.git/** - Version Control
Git repository for version control and change tracking

---

## Key Features

### Custom Keywords
- Defined in `Libs/CustomKeywords.groovy`
- Provides reusable automation logic specific to Lago app
- Can be called from test cases for better maintainability

### Global Variables
- Stored in `Libs/internal/GlobalVariable.groovy`
- Used across multiple test cases
- Includes common data and configuration values

### Self-Healing Mechanism
- Automatically recovers from broken locators
- Stores information in `Reports/Self-healing/broken-test-objects.json`
- Improves test stability and reduces maintenance overhead

### Multiple Execution Profiles
- `Profiles/default.glbl` allows different execution configurations
- Supports environment-specific settings (dev, staging, production)

---

## Configuration Files

### Log Configuration
- **Location:** `Include/config/log.properties`
- **Purpose:** Controls logging behavior during test execution

### Database Settings
- **Location:** `settings/external/com.kms.katalon.core.db.DatabaseSettings.properties`
- **Purpose:** Database connection configuration for data-driven tests

### Analytics & Integration
- **qTest Integration:** `settings/internal/com.kms.katalon.integration.qtest.properties`
- **Analytics:** `settings/internal/com.kms.katalon.integration.analytics.properties`

---

## How to Use

### Running Tests
1. Open the project in Katalon Studio
2. Select a test case or test suite to execute
3. Choose the appropriate execution profile from `Profiles/`
4. Click "Run" to start test execution

### Adding Test Cases
Test cases should be created in appropriate directories within `Include/` and can utilize custom keywords from `Libs/CustomKeywords.groovy`

### Modifying Settings
- Test execution settings: Edit files in `settings/` directory
- Global variables: Edit `Libs/internal/GlobalVariable.groovy`
- Custom keywords: Edit `Libs/CustomKeywords.groovy`

---

## Git Repository
This project is version controlled with Git (`.git/` directory present). Use standard Git commands to manage changes and maintain project history.

---

## Notes
- The project follows Katalon Studio standards and conventions
- Self-healing feature is enabled for improved test maintenance
- Multiple integrations configured (qTest, Analytics)
- Project is configured for generic testing scenarios
