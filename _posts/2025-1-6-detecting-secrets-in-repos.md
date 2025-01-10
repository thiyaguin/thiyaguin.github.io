---
title: "Detecting secrets in Source Code"
tags:
  - Git
  - GitLeaks
  - Security
  - Repository
  - Secrets
  - CI/CD
  - Cloud Operations
  - Keys
---
Maintaining the security of our code is paramount, and a critical aspect of that security is the proper management and protection of secrets like API keys, keyfiles, passwords, and tokens. Accidentally committing these secrets to your code repository can have serious consequences.

## Why Secret Scanning is Essential

* Prevents Data Leaks: Secrets embedded in code can be easily exposed if not managed properly, leading to unauthorized access and potential data breaches.
* Ensures Compliance: Many organizations have compliance requirements that mandate the protection of sensitive data. Secret scanning helps ensure adherence to these regulations.
* Early Detection: Integrating secret scanning into your CI/CD pipeline allows for early detection of leaks, preventing them from reaching production environments.
* Faster Releases: Automated secret scanning streamlines the security process, eliminating manual checks that can slow down deployments.

## Gitleaks: An Open-Source Secret Scanning Tool

Gitleaks is a free, open-source tool that inspects Git repositories for potential leaks of sensitive information. It scans code for patterns that might indicate the presence of secrets like passwords, API keys, and keyfiles. When Gitleaks finds a match, it triggers an alert, allowing you to take action to remove the sensitive information from your repository.

## Using Gitleaks 

There are two primary ways to leverage Gitleaks for secret scanning:

* Pre-commit Hooks: Git hooks are scripts that run before or after specific Git events, such as commits, pushes, or merges. Pre-commit hooks specifically run before a commit is finalized and can be used for various tasks, including secret scanning with Gitleaks. You can find instructions for setting up Gitleaks as a pre-commit hook in the official documentation: [Gitleaks as pre-commit hook](https://github.com/gitleaks/gitleaks?tab=readme-ov-file#pre-commit):

![Pre Commit Hook](/assets/precommit.png)

* CI/CD Pipeline Integration: Integrating Gitleaks with your CI/CD pipeline allows for automated scanning of your repositories as part of the development process. This ensures that secret leaks are caught early and addressed before they become a security risk.
The specific steps for integrating Gitleaks with your CI/CD pipeline will vary depending on the platform you are using. Here are some examples:

GitLab pipeline: 

![GitLab](/assets/gitlab-gitleaks.png)

GitHub pipeline: 

GitHub scans repositories for known types of secrets, to prevent fraudulent use of secrets that were committed accidentally. Secret scanning is available for the following repositories:

* Public repositories (for free)
* Private and internal repositories in organizations using GitHub Enterprise Cloud with GitHub Advanced Security enabled

Gitleak can be used as Github Action to scan the repositories

![GitHub](/assets/github-gitleaks.png)

By implementing secret scanning with Gitleaks, you can significantly improve the security of your code repositories and prevent accidental leaks of sensitive information.
