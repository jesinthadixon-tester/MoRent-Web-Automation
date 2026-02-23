# MoRent Web Automation

A comprehensive Robot Framework test automation suite for the MoRent car rental web application. This project provides end-to-end testing capabilities with Python extensions for enhanced functionality.

## 📋 Table of Contents

- [Project Overview](#project-overview)
- [Project Structure](#project-structure)
- [Tools Used](#tools-used)
- [Project Setup](#project-setup)
- [How to Run Tests](#how-to-run-tests)
- [Test Coverage Summary](#test-coverage-summary)
- [Test Results](#test-results)
- [Contributing](#contributing)

## 🎯 Project Overview

This automation framework is designed to test the MoRent web application, covering critical user journeys including authentication, profile management, search functionality, and booking processes.

## 📁 Project Structure

```
MoRent-Web-Automation/
├── tests/                          # Test suites organized by feature
│   ├── auth/                       # Authentication tests
│   │   ├── header_navigation_tests.robot
│   │   ├── login_tests.robot
│   │   └── registration_navigation_tests.robot
│   ├── booking/                    # Booking functionality tests
│   │   └── booking_tests.robot
│   ├── profile/                    # User profile tests
│   │   └── TC_Verify_Update_Profile_Functionality.robot
│   └── search/                     # Search functionality tests
│       └── search_tests.robot
├── resources/                      # Reusable resources
│   ├── keywords.robot              # Custom keywords
│   ├── locators.robot              # Element locators
│   ├── variables.robot             # Test variables
│   ├── base/                       # Base utilities
│   │   └── common_utility.robot
│   └── pages/                      # Page objects
│       ├── home_page.robot
│       ├── login_page.robot
│       └── profile_page.robot
├── python_lib/                     # Python helper libraries
│   ├── data_generator.py           # Test data generation
│   ├── date_utils.py               # Date/time utilities
│   └── validators.py               # Data validation utilities
├── config/                         # Configuration files
│   └── env_config.py               # Environment configuration
├── results/                        # Test execution results
└── README.md                       # Project documentation
```

## 🛠️ Tools Used

### Core Framework
- **Robot Framework** (v6.0+) - Test automation framework
- **SeleniumLibrary** (v6.0+) - Web testing library for Robot Framework
- **Python** (v3.8+) - Programming language for custom libraries

### Testing Tools
- **Selenium WebDriver** - Browser automation
- **Chrome/Firefox WebDriver** - Browser drivers for test execution

### Development Tools
- **Git** - Version control
- **VS Code** - Recommended IDE with Robot Framework extensions

### Python Libraries
- **Custom Python Libraries**:
  - `data_generator.py` - Generates test data dynamically
  - `date_utils.py` - Handles date/time operations
  - `validators.py` - Validates input data and responses

## 🚀 Project Setup

### Prerequisites

1. **Python Installation** (v3.8 or higher)
   ```bash
   python --version
   ```

2. **pip Installation** (Python package manager)
   ```bash
   pip --version
   ```

### Installation Steps

1. **Clone the Repository**
   ```bash
   git clone https://github.com/jesinthadixon-tester/MoRent-Web-Automation.git
   cd MoRent-Web-Automation
   ```

2. **Install Robot Framework and Dependencies**
   ```bash
   pip install robotframework
   pip install robotframework-seleniumlibrary
   ```

3. **Install WebDriver** (Choose one based on your browser)
   
   **For Chrome:**
   ```bash
   # Download ChromeDriver matching your Chrome version
   # Place it in your system PATH or project directory
   ```
   
   **For Firefox:**
   ```bash
   # Download GeckoDriver
   # Place it in your system PATH or project directory
   ```

4. **Verify Installation**
   ```bash
   robot --version
   ```

5. **Configure Environment** (Optional)
   - Update `config/env_config.py` with your environment-specific settings
   - Set base URL, timeouts, and other configurations

## ▶️ How to Run Tests

### Run All Tests
Execute all test suites in the project:
```bash
robot --outputdir results tests/
```

### Run Specific Test Suite
Execute tests from a specific module:

**Authentication Tests:**
```bash
robot --outputdir results tests/auth/login_tests.robot
robot --outputdir results tests/auth/registration_navigation_tests.robot
robot --outputdir results tests/auth/header_navigation_tests.robot
```

**Profile Tests:**
```bash
robot --outputdir results tests/profile/TC_Verify_Update_Profile_Functionality.robot
```

**Search Tests:**
```bash
robot --outputdir results tests/search/search_tests.robot
```

**Booking Tests:**
```bash
robot --outputdir results tests/booking/booking_tests.robot
```

### Run Tests by Tag
Execute tests with specific tags:
```bash
robot --outputdir results --include smoke tests/
robot --outputdir results --include regression tests/
```

### Run Tests with Custom Browser
```bash
robot --outputdir results --variable BROWSER:firefox tests/
robot --outputdir results --variable BROWSER:chrome tests/
```

### Parallel Execution (Optional)
Install Pabot for parallel execution:
```bash
pip install robotframework-pabot
pabot --processes 4 --outputdir results tests/
```

## 📊 Test Coverage Summary

### Authentication Module
- **Login Tests** (`tests/auth/login_tests.robot`)
  - Valid user login
  - Invalid credentials handling
  - Session management
  - Remember me functionality

- **Registration Navigation Tests** (`tests/auth/registration_navigation_tests.robot`)
  - Sign-up page navigation
  - Registration form validation
  - User account creation flow

- **Header Navigation Tests** (`tests/auth/header_navigation_tests.robot`)
  - Navigation menu functionality
  - User menu interactions
  - Logout functionality

### Profile Management Module
- **Update Profile Tests** (`tests/profile/TC_Verify_Update_Profile_Functionality.robot`)
  - Profile information update
  - First name and last name modification
  - Profile validation
  - Data persistence verification

### Search Module
- **Search Tests** (`tests/search/search_tests.robot`)
  - Vehicle search functionality
  - Filter application
  - Search results validation
  - Sort functionality

### Booking Module
- **Booking Tests** (`tests/booking/booking_tests.robot`)
  - Vehicle booking flow
  - Date selection
  - Booking confirmation
  - Payment integration

### Reusable Resources
- **Keywords** (`resources/keywords.robot`)
  - Launch Application
  - Navigate To Profile Page
  - Validate Update Profile
  - Update Profile Names
  - Verify Updated User Name

- **Locators** (`resources/locators.robot`)
  - Centralized element locators
  - Page-specific selectors

## 📈 Test Results

After test execution, detailed reports are generated in the `results/` directory:

- **`report.html`** - High-level test execution summary with pass/fail statistics
- **`log.html`** - Detailed step-by-step test execution log with screenshots
- **`output.xml`** - Machine-readable test output for CI/CD integration

### Viewing Results
Open the HTML reports in your browser:
```bash
open results/report.html  # macOS
start results/report.html # Windows
xdg-open results/report.html # Linux
```

## 🤝 Contributing

1. Create a feature branch from `main`
2. Follow the existing project structure
3. Add tests for new features
4. Update documentation as needed
5. Submit a pull request for review

## 📝 Best Practices

- Keep test cases independent and atomic
- Use descriptive test case names
- Maintain page object pattern for better maintainability
- Use variables for test data
- Add appropriate tags for test categorization
- Document complex test scenarios

## 📞 Support

For issues or questions, please create an issue in the GitHub repository.

---

**Last Updated:** February 2026  
**Maintained By:** Jesintha Dixon
