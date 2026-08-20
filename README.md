# Python CI/CD with GitHub Actions

A small hands-on project demonstrating how Continuous Integration and Continuous Deployment work using Python, pytest, GitHub Actions, and GitHub Pages.

## What this project demonstrates

This repository shows the complete development flow:

Code → Test → Commit → Push → CI → Deploy

### Continuous Integration

Whenever code is pushed to the `main` branch, GitHub Actions automatically:

1. Creates an Ubuntu runner
2. Checks out the repository
3. Sets up Python
4. Installs pytest
5. Runs the automated tests
6. Reports whether the build passed or failed

### Continuous Deployment

A second GitHub Actions workflow automatically publishes the static website in the `site` directory to GitHub Pages.

## Project Structure

```text
.
├── .github/
│   └── workflows/
│       ├── ci.yml
│       └── deploy.yml
├── site/
│   └── index.html
├── calculator.py
├── test_calculator.py
├── requirements.txt
├── .gitignore
└── README.md

```
## Example Application

The project contains a simple Python calculator:

```python
def add(a, b):
    return a + b


def subtract(a, b):
    return a - b
```

## Automated Tests

The calculator functions are tested using `pytest`.

```python
from calculator import add, subtract


def test_add():
    assert add(2, 3) == 5


def test_subtract():
    assert subtract(10, 4) == 6
```

Run the tests locally with:

```bash
pytest
```

Expected result:

```text
2 passed
```

## CI Pipeline

The Continuous Integration workflow is located at:

```text
.github/workflows/ci.yml
```

Whenever code is pushed to the `main` branch, GitHub Actions automatically:

1. Checks out the repository
2. Sets up Python
3. Installs project dependencies
4. Runs the automated tests
5. Reports whether the tests passed or failed

The flow looks like this:

```text
Developer
    ↓
git push
    ↓
GitHub
    ↓
GitHub Actions
    ↓
Install dependencies
    ↓
Run pytest
    ↓
PASS ✅ / FAIL ❌
```

## CD Pipeline

The Continuous Deployment workflow is located at:

```text
.github/workflows/deploy.yml
```

The workflow automatically deploys the website inside the `site` directory to GitHub Pages.

```text
Code Change
    ↓
git push
    ↓
GitHub Actions
    ↓
Upload Website
    ↓
GitHub Pages
    ↓
Live Website 🌎
```

## Why CI/CD Matters

CI/CD helps development teams:

* Automatically test code
* Catch bugs before deployment
* Reduce manual deployment steps
* Make deployments repeatable
* Release software more safely
* Detect problems quickly

## Technologies Used

* Python
* pytest
* Git
* GitHub
* GitHub Actions
* GitHub Pages
* YAML
* HTML

## Running the Project Locally

Clone the repository:

```bash
git clone https://github.com/mnsharon/cicd-demo.git
```

Enter the project directory:

```bash
cd cicd-demo
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run the tests:

```bash
pytest
```

## CI/CD Workflow Summary

```text
Write Code
    ↓
Test Locally
    ↓
git add
    ↓
git commit
    ↓
git push
    ↓
GitHub Actions
    ↓
CI Tests
    ↓
Deployment
    ↓
GitHub Pages
```

## Key Takeaway

**Git tracks the code.**

**GitHub stores the code.**

**CI tests the code.**

**CD deploys the code.**

This repository provides a simple, practical example of how those pieces work together.
