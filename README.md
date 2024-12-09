# CI/CD Pipeline with GitHub Actions

## Table of Contents

- [Project Overview](#project-overview)
- [User Story](#user-story)
- [Acceptance Criteria](#acceptance-criteria)
- [Prerequisites](#prerequisites)
- [Project Setup](#project-setup)
  - [Repository Structure](#repository-structure)
  - [Deployment Configuration](#deployment-configuration)
- [GitHub Actions Workflow](#github-actions-workflow)
  - [Test Workflow](#test-workflow-pull-request-to-develop)
  - [Deployment Workflow](#deployment-workflow-develop-to-main)
- [Workflow Files](#workflow-files)
- [Best Practices](#best-practices)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)

## Project Overview

This project demonstrates the implementation of a Continuous Integration and Continuous Deployment (CI/CD) pipeline using GitHub Actions for a full-stack application. The goal is to automate testing and deployment processes to ensure code quality and streamline development workflows.

## User Story

```
AS A software engineer looking to integrate a CI/CD pipeline in a codebase
I WANT a full-stack application that runs test cases when a Pull Request is made to the develop branch and automatically deploys to Render when the code is merged to main
SO THAT I can ensure that all code integrations are clean and pass the proper requirements and that the application is constantly updated when major releases are made to the main branch
```

## Acceptance Criteria

- When uploading new features, Pull Requests should be made to the `develop` branch first
- Creating a Pull Request to the `develop` branch triggers a GitHub Action to run Cypress component tests
- Passing test results are displayed on GitHub Action, allowing code to be merged
- Pushing code from `develop` to `main` triggers an automatic deployment to Render

## Prerequisites

Before getting started, ensure you have:

- A GitHub account
- A Render account
- MongoDB Atlas account
- Installed Cypress for component testing
- Basic understanding of GitHub Actions and CI/CD concepts

## Project Setup

### Repository Structure

1. Upload the contents of the `Develop` folder to a new GitHub Repository
2. Create two branches:
   - `main`: Production branch
   - `develop`: Development branch for feature integrations

### Deployment Configuration

1. Deploy the application via Render and MongoDB Atlas
2. Navigate to Render Settings and disable Auto-Deploy
3. Copy the Deploy Hook URL for GitHub Actions configuration

## GitHub Actions Workflow

### Test Workflow (Pull Request to `develop`)

The test workflow is configured to:
- Trigger on pull requests to the `develop` branch
- Run Cypress component tests
- Provide test results and status checks

### Deployment Workflow (`develop` to `main`)

The deployment workflow is configured to:
- Trigger when code is merged from `develop` to `main`
- Automatically deploy the application to Render
- Use the Deploy Hook URL for triggering deployment

## Workflow Files

You'll need two YAML configuration files:
- `.github/workflows/test.yml`: Handles testing on pull requests
- `.github/workflows/deploy.yml`: Manages automatic deployment

## Best Practices

- Always create feature branches from `develop`
- Merge feature branches back to `develop`
- Only merge `develop` to `main` when ready for production
- Ensure all tests pass before merging
- Use meaningful commit messages
- Review pull requests thoroughly

## Troubleshooting

- Check GitHub Actions logs for detailed error information
- Verify Render and MongoDB configurations
- Ensure all environment variables are correctly set

## Contributing

1. Fork the repository
2. Create a feature branch from `develop`
3. Make your changes
4. Run tests locally
5. Submit a pull request to `develop`

