# 🏰 FormFortress Challenge

![FormFortress Banner](https://img.shields.io/badge/FormFortress-Challenge-blue)
![Docker](https://img.shields.io/badge/Docker-Compose-green)
![Automation](https://img.shields.io/badge/Automation-Testing-yellow)

Welcome to the **FormFortress Challenge**! This challenge is crafted to evaluate your skills in setting up secure web environments and developing robust automated tests for security verification and password setup forms.

---

## 📜 Table of Contents

- [🎯 Objective](#-objective)
- [📁 Project Structure](#-project-structure)
- [⚙️ Environment Setup](#️️️️️️️️️️environment-setup)
  - [Prerequisites](#prerequisites)
  - [Launching the Docker Environment](#launching-the-docker-environment)
  - [Verifying the Setup](#verifying-the-setup)
- [🤖 Automation Testing](#️️️️️️️️️️automation-testing)
  - [Key Areas to Automate](#key-areas-to-automate)
  - [Test Case Examples](#test-case-examples)
- [📝 Documentation](#documentation)
- [🔍 Evaluation Criteria](#evaluation-criteria)
- [🚀 Getting Started](#-getting-started)
- [💡 Additional Tips](#additional-tips)
- [❓ Support](#support)
- [📜 License](#license)

---

## 🎯 **Objective**

The **FormFortress Challenge** aims to assess your ability to:

1. **Set Up** a secure web server environment using Docker Compose and Nginx to serve a security verification and password setup form.
2. **Develop Automated Tests** to validate the form's functionalities, including CAPTCHA verification, password strength validation, form submission, error handling, and security mechanisms.
3. **Document** your process clearly, ensuring that others can replicate your setup and understand your testing approach.

---

## 📁 **Project Structure**

```
FormFortress-Challenge/
├── docker-compose.yml
├── nginx/
│   ├── default.conf
│   └── html/
│       └── index.html
└── README.md
```

- **`docker-compose.yml`**: Docker Compose configuration to set up Nginx.
- **`nginx/default.conf`**: Nginx server configuration.
- **`nginx/html/index.html`**: The security verification and password setup form.
- **`README.md`**: This documentation.

---

## ⚙️ **Environment Setup**

### 🔧 **Prerequisites**

Ensure you have the following installed on your machine:

- **[Docker](https://docs.docker.com/get-docker/)** & **[Docker Compose](https://docs.docker.com/compose/install/)**
- **[Python 3](https://www.python.org/downloads/)** (optional, for automated tests)
- **[Chrome Browser](https://www.google.com/chrome/)** (commonly used by Selenium WebDriver)
- **Optional Testing Tools**:
  - Depending on your chosen framework (e.g., Cypress, Puppeteer, Playwright), ensure you have the necessary tools installed.

### 🚀 **Launching the Docker Environment**

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/Chaos-Camp/FormFortress-Challenge.git
   cd FormFortress-Challenge
   ```

2. **Start Docker Containers**:

   ```bash
   docker-compose up -d
   ```

   - **Explanation**:
     - `-d`: Runs containers in detached mode.
     - Nginx will serve the `index.html` at [http://localhost:8080](http://localhost:8080).

3. **Verify the Setup**:

   - Open your browser and navigate to [http://localhost:8080](http://localhost:8080).
   - You should see the **Security Verification & Password Setup** form.

---

## 🤖 **Automation Testing**

Automate the testing of the form's functionalities to ensure robustness and security. You are free to choose any testing framework that suits your preferences and expertise.

### 🔑 **Key Areas to Automate**

1. **CAPTCHA Verification**
   - **Correct Entry**: Enter the displayed CAPTCHA correctly to proceed.
   - **Incorrect Entry**: Enter an incorrect CAPTCHA and verify error handling.
   - **Lockout Mechanism**: Trigger lockout after maximum failed attempts.

2. **Password Setup**
   - **Password Strength Validation**: Test various password complexities.
   - **Password Visibility Toggle**: Ensure the toggle shows/hides passwords correctly.
   - **Password Confirmation**: Validate that confirmation matches the original password.

3. **Form Submission**
   - **Successful Submission**: Complete the form with valid data and submit.
   - **Invalid Submission**: Attempt submission with invalid or incomplete data.

4. **Security Mechanisms**
   - **Lockout After Failed Attempts**: Verify user lockout after multiple failed CAPTCHA attempts.
   - **Preventing Bypass of Validation**: Test form's resilience against bypass attempts.

5. **Accessibility and Usability**
   - **Keyboard Navigation**: Navigate and interact with the form using the keyboard.
   - **Screen Reader Compatibility**: Ensure form elements are accessible via screen readers.

### 🧪 **Test Case Examples**

| **Test Case ID** | **Description** | **Expected Outcome** |
|-------------------|-----------------|----------------------|
| TC01 | Enter correct CAPTCHA and proceed to password setup | Access to password setup step is granted |
| TC02 | Enter incorrect CAPTCHA and observe error message | Error message displayed, attempt counter incremented |
| TC03 | Enter CAPTCHA incorrectly three times to trigger lockout | User is locked out for 30 seconds with a countdown |
| TC04 | Enter a password with less than 8 characters | Password length criterion fails, submit button disabled |
| TC05 | Enter a password with uppercase, lowercase, numbers, and special characters | All criteria met, submit button enabled |
| TC06 | Toggle password visibility and verify input type changes | Password fields toggle between `password` and `text` types |
| TC07 | Enter mismatched passwords in password and confirmation fields | Passwords do not match, appropriate error message displayed |
| TC08 | Submit the form with all valid inputs | Success message displayed, form resets |
| TC09 | Attempt to submit the form with invalid data via browser dev tools | Form submission is blocked, security mechanisms enforced |
| TC10 | Navigate the form using only the keyboard | All interactive elements are accessible and operable |

---

## 📝 **Documentation**

Provide clear and comprehensive documentation to guide participants through setup and testing.

### 📄 **README.md**

This document serves as your primary guide. Ensure it includes:

- **Introduction**: Overview of the challenge and objectives.
- **Prerequisites**: Tools and software required.
- **Setup Instructions**: Step-by-step guide to launch the environment.
- **Automation Testing**: Detailed areas and test case examples.
- **Running Tests**: Instructions on executing automated tests.
- **Interpreting Results**: Understanding test outputs and handling failures.
- **Troubleshooting**: Common issues and solutions.

---

## 🔍 **Evaluation Criteria**

Submissions will be evaluated based on:

1. **Completeness**: Coverage of all specified test cases.
2. **Accuracy**: Correct implementation and validation of form functionalities.
3. **Efficiency**: Optimization of test scripts for performance and reliability.
4. **Code Quality**: Readability, maintainability, and adherence to best practices.
5. **Documentation**: Clarity and thoroughness of setup and testing instructions.

---

## 🚀 **Getting Started**

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/Chaos-Camp/FormFortress-Challenge.git
   cd FormFortress-Challenge
   ```

2. **Launch Docker Containers**:

   ```bash
   docker-compose up -d
   ```

3. **Access the Form**:

   Open [http://localhost:8080](http://localhost:8080) in your browser.

4. **Develop and Run Automated Tests**:

   - **Choose Your Testing Framework**:
     - Examples: **Selenium**, **Cypress**, **Puppeteer**, **Playwright**, etc.
   
   - **Set Up Your Testing Environment**:
     - Install necessary dependencies based on your chosen framework.
   
   - **Design and Implement Test Cases**:
     - Refer to the **Test Case Examples** section to guide your testing scenarios.
   
   - **Execute Your Tests**:
     - Run your test scripts and ensure all test cases pass.
   
   - **Review and Report**:
     - Analyze test results, fix any issues, and document your findings.

5. **Stop Docker Containers**:

   ```bash
   docker-compose down
   ```

---

## 💡 **Additional Tips**

- **Dynamic CAPTCHA Handling**: Ensure your test scripts can capture and input the dynamically generated CAPTCHA.
- **Synchronization**: Utilize explicit waits to handle dynamic content loading.
- **Error Handling**: Implement robust error handling in your test scripts to manage unexpected behaviors.
- **Modularity**: Structure your test scripts into reusable functions or classes for better maintainability.
- **Reporting**: Generate detailed test reports or logs to facilitate easier analysis of test outcomes.
- **Headless Mode**: Consider running tests in headless mode for efficiency, especially in CI/CD pipelines.
- **Security Considerations**: Test for vulnerabilities like XSS, SQL injection, and input sanitization to ensure form robustness.
- **Accessibility Testing**: Incorporate accessibility testing tools or libraries to validate form compliance with accessibility standards.

---

## ❓ **Support**

If you encounter any issues or have questions regarding the challenge, feel free to reach out:

- **Email**: [support@chaos-camp.com](mailto:support@chaos-camp.com)
- **GitHub Issues**: [Open an Issue](https://github.com/Chaos-Camp/FormFortress-Challenge/issues)

---

## 📜 **License**

Distributed under the [MIT License](LICENSE).

---

# 🌟 **Good Luck!**

Embrace the **FormFortress Challenge**, showcase your automation prowess, and ensure the security verification and password setup form is rock-solid! 🚀
