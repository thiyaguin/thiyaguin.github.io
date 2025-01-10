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
Maintaining the security of our code is as crucial as ensuring its functionality. One of the key aspects of security is managing and safeguarding our secrets, such as API keys, keyfiles, passwords, and tokens. Accidentally committing these secrets to your repository can lead to severe security breaches

Why secret scanning is important:

1. Prevent Data Leaks: Secrets embedded in the code can be easily exposed if not managed properly, leading to unauthorized access.
2. Compliance: Many organizations have compliance requirements that mandate the protection of sensitive data.
3. Early Detection: Scanning for secrets early in the CI pipeline helps catch issues before they make it to production.
4. Faster Time to Market through Accelerated Releases: Automated secret scanning ensures that security checks do not become bottlenecks in the release process, allowing for faster and more frequent releases.

Gitleaks is an open-source tool - inspects Git repositories for potential leaks of sensitive information. It scans the code repository for files that match a set of predefined patterns. These patterns are designed to match various types of sensitive information, such as passwords, secrets, key files, etc. Once GitLeaks finds a match, it alerts, and we can take action to remove the sensitive information.

## Using Gitleaks 

In pre-commit hooks:

Git hooks are scripts that Git runs before or after certain events like committing, pushing, or merging code.

Pre-commit hooks are scripts that run automatically before a commit is finalized within a Git repository, which are versatile and can be customized to perform various tasks, such as code linting, running tests, or checking for specific patterns in committed code.

[Gitleaks as pre-commit hook](https://github.com/gitleaks/gitleaks?tab=readme-ov-file#pre-commit):

![Pre Commit Hook](/assets/precommit.png)

In CI/CD pipeline: 

Integration of Gitleaks with CI/CD systems allows for streamlined scanning of repositories and reporting of findings.

GitLab pipeline: 

![GitLab](/assets/gitlab-gitleaks.png)

GitHub pipeline: 

GitHub scans repositories for known types of secrets, to prevent fraudulent use of secrets that were committed accidentally. Secret scanning is available for the following repositories:

* Public repositories (for free)
* Private and internal repositories in organizations using GitHub Enterprise Cloud with GitHub Advanced Security enabled

Gitleak can be used as Github Action to scan the repositories

![GitHub](/assets/github-gitleaks.png)
