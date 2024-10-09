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
7. [Code Review](#7-code-review)

   7\.1. [Continous Integration](#71-continous-integration)

   7\.2. [Pull Requests](#72-pull-requests)

   7\.3. [Assignments](#73-assignements)

   7\.4. [Comments](#74-comments)

   7\.5. [Code Modification](#75-code-modification)
8. [Bug Report](#8-bug-report)

   8\.1. [Issue Assignment](#81-issue-management)

   8\.2. [Version Control](#82-version-control)

## 1. Objectives

This document describes a process specification from a specific side of the software development lifecycle strategy, mainly these three phases: **Code**, **Build** and **Test**.

The key takeaways from this document is to know how to write code, using a uniform specification of code quality, assuring the use of version control for explicit commit history, feature development and releases, the ability to test code using all forms of software testing.

## 2. Version Control

We recommend using **Git** as source code management, here is a few things to consider when choosing git:

* **Commits:** They must follow these specified [naming rules](https://github.com/angular/angular/blob/main/CONTRIBUTING.md#commit-message-header).

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

## 7. Code Review

### 7.1. Continous Integration

### 7.2. Pull Requests

### 7.3. Assignements

### 7.4. Comments

### 7.5. Code Modification

## 8. Bug Report

### 8.1. Issue Management

### 8.2. Version Control