# DEV TEAM PROCESS

## DEVELOPMENT PROCESS

## Table Of Contents

1. [Objectives](#1-objectives)
2. [Version Control](#2-version-control)
3. [File Management](#3-file-management)
4. [Code](#4-code)

   4\.1. [Linters](#41-linters)

   4\.2. [Coding Rules](#42-coding-rules)

   4\.3. [Comments](#43-comments)

   4\.4. [Documentation](#44-documentation)
5. [Build](#5-build)

   5\.1. [Docker](#51-docker)

   5\.2. [Environment](#52-environment)

   5\.3. [Documentation](#53-documentation)
6. [Test](#6-test)

   6\.1. [Functional Testing](#61-functional-testing)

   6\.2. [End-to-End Testing](#62-endtoend-testing)

   6\.3. [System Testing](#63-system-testing)

   6\.4. [QA Testing](#64-qa-testing)
7. [Bug Report](#7-bug-report)
8. [Code Review](#8-code-review)

   8\.1. [Continous Integration](#81-continous-integration)

   8\.2. [Pull Requests](#82-pull-requests)

   8\.3. [Assignments](#83-assignements)

   8\.4. [Comments](#84-comments)

   8\.5. [Code Modification](#85-code-modification)

## 1. Objectives

This document describes a process specification from a specific side of the software development lifecycle strategy, mainly these three phases: **Code**, **Build** and **Test**.

The key takeaways from this document is to know how to write code, using a uniform specification of code quality, assuring the use of version control for explicit commit history, feature development and releases, the ability to test code using all forms of software testing.

## 2. Version Control

We recommend using **Git** as source code management, here is a few things to consider when choosing git:

* **Commit Message Format:** They must follow these specified [format rules](https://github.com/angular/angular/blob/main/CONTRIBUTING.md#commit-message-header).

  ```
  <type>(<scope>): <short summary>
     │       │             │
     │       │             └─⫸ Summary in present tense. Not capitalized. No period at the end.
     │       │
     │       └─⫸ Commit Scope: animations|bazel|benchpress|common|compiler|compiler-cli|core|
     │                          elements|forms|http|language-service|localize|platform-browser|
     │                          platform-browser-dynamic|platform-server|router|service-worker|
     │                          upgrade|zone.js|packaging|changelog|docs-infra|migrations|
     │                          devtools
     │
     └─⫸ Commit Type: build|ci|docs|feat|fix|perf|refactor|test
  
  [optional body]
  
  [optional footer(s)]
  ```
  Examples:
   * Commit message with description and breaking change footer
      ```
      feat: allow provided config object to extend other configs

      BREAKING CHANGE: `extends` key in config file is now used for extending other config files
      ```
   
   * Commit message with ! to draw attention to breaking change
      ```
      feat!: send an email to the customer when a product is shipped
      ```

  * For more examples see [here](https://www.conventionalcommits.org/en/v1.0.0/#examples).

* **Branches:** The adopted branching strategy is found in [CodeFlowBranches](./CodeFlowBranches.md)

## 3. File Management

## 4. Code

### 4.1. Linters

### 4.2. Coding Rules

### 4.3. Comments

### 4.4. Documentation

## 5. Build

### 5.1. Docker

### 5.2. Environment

### 5.3. Documentation

## 6. Test

### 6.1. Functional Testing

### 6.2. EndtoEnd Testing

### 6.3. System Testing

### 6.4. QA Testing

## 7. Bug Report
Before you submit an issue, please search the issue tracker. An issue for your problem might already exist and the discussion might inform you of workarounds readily available.

## 8. Code Review

### 8.1. Continous Integration

### 8.2. Pull Requests

### 8.3. Assignements

### 8.4. Comments

### 8.5. Code Modification

   If we ask for changes via code reviews then:

   Make the required updates to the code.

   Re-run the project test suites to ensure tests are still passing.

   Create a fixup commit and push to your GitHub repository (this will update your Pull Request):

   ```sh
      git add <files>
      git commit --fixup HEAD
      git push
   ```
   For more info on working with fixup commits see here.

   That's it!

   Updating the commit message
   A reviewer might often suggest changes to a commit message (for example, to add more context for a change or adhere to our commit message guidelines). In order to update the commit message of the last commit on your branch:

   Check out your branch:

   ```sh
      git checkout my-fix-branch
   ```
   Amend the last commit and modify the commit message:

   ```sh
      git commit --amend
   ```
   Push to your GitHub repository:

   ```sh
      git push --force-with-lease
   ```
   #### After your pull request is merged
   After your pull request is merged, you can safely delete your branch and pull the changes from the main (upstream) repository:

   Delete the remote branch on GitHub either through the GitHub web UI or your local shell as follows:

   ```sh
      git push origin --delete my-fix-branch
   ```
   Check out the main branch:

   ```sh
      git checkout main -f
   ```
   Delete the local branch:
   ```sh
      git branch -D my-fix-branch
   ```
   Update your local main with the latest upstream version:

   ```sh
      git pull --ff upstream main
   ```