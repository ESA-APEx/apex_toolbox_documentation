# APEx Documentation Portal

Welcome to the APEx Documentation Portal! This repository contains the source files and setup instructions for building and maintaining the APEx project documentation using Quarto. Whether you're a contributor or a user, you'll find everything you need to get started, preview changes, and ensure high-quality documentation.

## Getting Started

Follow these steps to set up and contribute to the APEx Documentation Portal.

### 1. Install Quarto

Install the [Quarto](https://quarto.org/docs/get-started/) framework. You can verify your installation by running the
following command in your terminal.

```sh
quarto --version
```

### 2. Set Up a Python Virtual Environment

Create and activate a virtual environment to manage Python dependencies:

```sh
python3 -m venv .venv
source .venv/bin/activate  # On Windows use: .venv\Scripts\activate
```

Upgrade pip and install the required libraries. If you add more dependencies, make sure to include them in `requirements.txt`:

```sh
pip install --upgrade pip
pip install -r requirements.txt
```

### 3. Preview the Documentation

To preview the documentation locally, run:

```sh
quarto preview
```

This will start a local server and open the documentation in your browser. Any changes you make will automatically reload.

### 4. Additional Resources

- [Getting Started with Quarto](https://quarto.org/docs/get-started/)
- [Quarto User Guide](https://quarto.org/docs/guide/)
- [Quarto Reference](https://quarto.org/docs/reference/)
- [Python Virtual Environments](https://docs.python.org/3/library/venv.html)

### Branch Protection and Pull Requests

By default, the `main` branch is protected to ensure the stability and quality of the documentation.
All changes must be made through a pull request (PR) from a separate branch.
After submitting a PR, automated quality checks will run via GitHub Actions.
Only PRs that pass these checks and receive approval from a team member can be merged into the `main` branch.
Once merged, the updates are published to the online documentation portal.

## Automated Deployment with GitHub Actions

Each commit to the `main` branch automatically triggers a new deployment using GitHub Actions. During this process, the documentation portal is built and final quality checks are performed to ensure everything is up to standard. You can monitor the deployment progress and review logs on the **Actions** page of your GitHub repository.

## Code Quality

### Pre-commit Hooks

This repository uses [`pre-commit`](https://pre-commit.com/) to manage code quality and consistency at commit time. `pre-commit` is a CLI tool and framework for managing Git pre-commit hooks. It helps with quick quality checks (such as linting and syntax checks), code formatting, and much more.

The pre-commit hooks in this repository perform the following checks before each commit:

- Format files to ensure a consistent style.
- Check documentation for dead links.

You can configure these actions in the `.pre-commit-config.yaml` file.

#### Setup

The `pre-commit` library is installed by default in your Python environment if you followed the steps above.
Alternatively, you can install it globally (using your OS package manager, conda, Homebrew, [pipx](https://pipx.pypa.io)
, etc.) for use across multiple projects.

Install the project-specific Git hooks (as defined in `.pre-commit-config.yaml`) by running the following command from
the project root:

```sh
pre-commit install
```

### Usage

- When you run `git commit`, the pre-commit hooks will execute and block the commit if any issues are detected.
- Fix any reported issues and try committing again.
- Some hooks will automatically fix issues and edit your files in place.
    This may seem intrusive at first, but it helps you maintain code quality without manual effort.

> **TIP**\
> Use Git’s staging feature to stage your changes separately from automatic pre-commit fixes for easier review.
