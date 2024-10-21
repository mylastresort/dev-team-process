# DEV TEAM PROCESS

## Table Of Contents

1. [Objectives](#1-objectives)
2. [Version Control](#2-version-control)
3. [File Management](#3-file-management)
4. [Code](#4-code)

   4\.1. [Tools](#41-tools)

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
9. [Index](#9-index)

## 1. Objectives

This document describes a process specification from a specific side of the software development lifecycle strategy, mainly these three phases: **Code**, **Build** and **Test**.

The key takeaway from this document is to know how to write code, using a uniform specification of code quality, assuring the use of version control for explicit commit history, feature development, releases and the ability to test code using all forms of software testing.

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

* **Branches:** 
   These branches which we expect to be permanently available on the repository follow the flow of code changes starting from development until the production.
   
   * **Master** (*master*)
   
     All new features, their tests and bug fixes should be brought to the main branch.
   
   * **Release** (*release*)
   
     A branch for tagging a specific release version.

   * **Feature** (*feature*) temporary branches

      Any code changes for a new module or use case should be done on a feature branch.

   More information can be found here [BranchingStrategy](./BranchingStrategy.md).

## 3. File Management

When targeting a new project, it can be tedious to impose a general folder structure for all projects, however, you need to consider this main objectif:
* each project must have these main root folders/files:
   ```
         project/
         ├── .github
         │   └── workflows
         │       └── build.yml
         ├── .gitignore
         ├── Makefile
         ├── README.md
         ├── doc
         ├── docker-compose.yml
         ├── pull_request_template.md
         ├── src
         ├── target
         └── test
   ```
   * `README.md`: file describing the content of the repository and how to build and test the project.
   * `[build]`: build files.
   * `doc`: anything related to user guide, project references, etc.
   * `src`: any source code files.
   * `test`: any test code files must be inside test folder.
      The choice of having class test files in the same path as the source files is allowed, but other forms of testing must be outside `src` folder.
   * `Makefile (optional)`: for building the source files.
   * `src/docker-compose.yml`: for building docker images.
   * `.github`: for CI tooling
   * `.gitignore`: file to ignore tracking files in git.
      * It must contain `target` or `**/target` on modular project.

   **NOTICE**: The case where the project has multiple modules, hence a **modular project**, e.g frontend and backend, microservice architecture, etc:
   * You can now move `src`, `target` and `test` folders to new folders per microservice/module, respecting the same previous root structure (`doc` & `docker-compose.yml` can be skiped).

## 4. Code

### 4.1. Tools

#### 4.1.1. Language Choice
You must prefer a typed language, either staticly or dynamically, but staticly is always preffered.

NOTICE: Make sure to have the latest stable version of the language.

#### 4.1.2. Linters
Code is linted using predefined configuration file (eslint, clang-tidy, ...)

References:
* [JS/TS Linter](https://eslint.org/docs/latest/rules/)

### 4.2. Coding Rules

To ensure consistency throughout the source code, keep these rules in mind as you are working:

* All features or bug fixes must be tested by one or more specs (unit-tests).

* We follow our own Coding Convetion specified [here](./coding_rules.md), but wrap all code at 100 characters.

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
#### Creating a Pull Request
When creating a new pull request, consider checking the `pull_request_template.md` document first, given on the root directory of the project.

An example of a such template can be found [here](https://github.com/thingsboard/thingsboard/blob/master/pull_request_template.md).

#### Labelling pull requests
There are five labels that target PRs to versions:

|Label |  Description|
|---|----|
target: major  |  A change that includes a backwards-incompatible behavior or API change.
target: minor | A change that introduces a new, backwards-compatible functionality.
target: patch | A backwards-compatible bug fix.

* Every PR must have exactly one `target: *` label.

* The vast majority of pull requests will target `major`, `minor`, or `patch` based on the contents of the code change.

* Breaking changes, marked with `target: major`, can only be merged when `main`  represents the next major version.

### 8.3. Assignements

### 8.4. Comments

### 8.5. Code Modification
   #### Addressing review feedback
   If we ask for changes via code reviews then:

   1. Make the required updates to the code.

   2. Re-run the project test suites to ensure tests are still passing.

   3. Create a fixup commit and push to your GitHub repository (this will update your Pull Request):

   ```sh
      git add <files>
      git commit --fixup HEAD
      git push
   ```

   That's it!

   #### Updating the commit message
   A reviewer might often suggest changes to a commit message (for example, to add more context for a change or adhere to our commit message guidelines). In order to update the commit message of the last commit on your branch:

   1. Check out your branch:

   ```sh
      git checkout my-fix-branch
   ```
   2. Amend the last commit and modify the commit message:

   ```sh
      git commit --amend
   ```
   3. Push to your GitHub repository:

   ```sh
      git push --force-with-lease
   ```
   #### After your pull request is merged
   After your pull request is merged, you can safely delete your branch and pull the changes from the main (upstream) repository:

   1. Delete the remote branch on GitHub either through the GitHub web UI or your local shell as follows:

   ```sh
      git push origin --delete my-fix-branch
   ```
   2. Check out the main branch:

   ```sh
      git checkout main -f
   ```
   3. Delete the local branch:
   ```sh
      git branch -D my-fix-branch
   ```
   4. Update your local main with the latest upstream version:

   ```sh
      git pull --ff upstream main
   ```

## 9. Index