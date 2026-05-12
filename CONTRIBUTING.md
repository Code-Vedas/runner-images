# Contributing to Runner Images

Thank you for contributing to `runner-images`. This repository contains container images used by Code Vedas CI/CD pipelines. Before opening a change, review the repository structure in [README.md](README.md) and keep changes scoped to the relevant image directory under `images/`.

Feel free to contribute through various avenues such as suggestions, comments, bug reports, or pull requests. To do so, please open an issue or a pull request directly in the repository.

## Community Engagement

There are several ways to become an active part of our community:

1. [Create an issue](https://www.github.com/Code-Vedas/runner-images/issues/new/choose) in the repository.
2. Join our mailing list by sending an email to [Join mailing list](mailto:mailing-list@codevedas.com).
3. Participate in our Slack channel by sending an email to [Join slack](mailto:join-slack@codevedas.com).
4. Apply for project membership by sending an email to [Join project](mailto:join-project@codevedas.com). Following an initial screening, an invitation will be extended to you. This membership allows you to create issues, pull requests, and more, directly in the repository without the need to fork it.
5. If you wish to make a financial contribution, please follow GitHub's instructions for donating to the project.

## Code and Documentation

We encourage contributions to both the codebase and documentation.

This repository can contain multiple runner images. Each image should have its own directory, build context, and documentation assumptions.

Current layout:

| Path                 | Purpose                          |
| -------------------- | -------------------------------- |
| `images/cpp-runner/` | C++ CI image with build tooling  |

## Improve Documentation

Contributions to the documentation, including this file, are highly welcomed.

Two ways to contribute to the documentation:

1. Create an issue in the repository with the suggested changes using the appropriate template.
2. Submit a pull request in the repository with the suggested changes, adhering to the specified template.

Both approaches are applicable to this file as well, following the outlined code of conduct.

## Improve Code

Your contributions to the codebase are appreciated. Keep image-specific changes inside that image's directory and update shared automation when the repository structure changes.

Two ways to contribute to the code:

1. Open an issue in the repository with the suggested changes, using the appropriate template.
2. Submit a pull request in the repository with the suggested changes, following the specified template.

### Pull Request

Before creating a pull request, ensure the following:

1. Download and install the code on your local machine.
2. Build the affected image locally and verify that it is functioning as expected.
3. Create a branch for your changes, ensuring they work as intended. The branch name should follow the format `feature/<feature-name>`, `bugfix/<bug-name>`, `hotfix/<hotfix-name>`, etc.
4. Run applicable validation for the changed image or workflow.
5. Ensure the code adheres to coding standards and best practices.
6. Provide thorough documentation for the changes made.
7. When creating a PR, select the correct template and complete all details. If the template is unavailable, create an issue in the repository for template addition. Failure to complete the template may result in the PR being closed without action.

### Issue

Before creating an issue, perform the following:

1. Invest time in finding a solution to the problem (if applicable).
2. When creating an issue, select the correct template and complete all details. If the template is absent, create an issue in the repository to request its addition. Failure to complete the template may lead to the issue being closed without action.

Both approaches are suitable for various changes, including bug fixes and new features, while adhering to the code of conduct.

## Enhance Security

Contributions to the security aspects of the project are highly appreciated. To report a security vulnerability, please follow the instructions outlined in the [SECURITY.md](SECURITY.md) file.
