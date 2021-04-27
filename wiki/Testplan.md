---
layout: page
title: Test Plan
permalink: /wiki/testing
notInNav: true
---

{% include wiki-nav.html %}


## Table of Contents

- [Test Plan - FileFighter](#test-plan---filefighter)
  * [Table of Contents](#table-of-contents)
  * [Revision History](#revision-history)
  * [1. Introduction](#1-introduction)
    + [1.1 Purpose](#11-purpose)
    + [1.2 Scope](#12-scope)
    + [1.3 Intended Audience](#13-intended-audience)
    + [1.3 Definitions, Acronyms and Abbreviations](#13-definitions--acronyms-and-abbreviations)
    + [1.4 References](#14-references)
    + [1.6 Document Structure](#16-document-structure)
  * [2. Evaluation Mission and Test Motivation](#2-evaluation-mission-and-test-motivation)
    + [2.1 Background](#21-background)
    + [2.2 Evaluation Mission](#22-evaluation-mission)
    + [2.3 Test Motivators](#23-test-motivators)
  * [3. Target Test Items](#3-target-test-items)
  * [4. Outline of Planned Tests](#4-outline-of-planned-tests)
    + [4.1 Outline of Test Inclusions](#41-outline-of-test-inclusions)
    + [4.2 Outline of Other Candidates for Potential Inclusion](#42-outline-of-other-candidates-for-potential-inclusion)
    + [4.3 Outline of Test Exclusions](#43-outline-of-test-exclusions)
  * [5. Test Approach](#5-test-approach)
    + [5.1 Initial Test-Idea Catalogs and Other Reference Sources](#51-initial-test-idea-catalogs-and-other-reference-sources)
    + [5.2 Testing Techniques and Types](#52-testing-techniques-and-types)
      - [5.2.1 Data and Database Integrity Testing](#521-data-and-database-integrity-testing)
      - [5.2.2 Function Testing](#522-function-testing)
      - [5.2.3 Business Cycle Testing](#523-business-cycle-testing)
      - [5.2.4 User Interface Testing](#524-user-interface-testing)
        * [automated End-to-End-test run in the browser](#automated-end-to-end-test-run-in-the-browser)
        * [automated snapshot test](#automated-snapshot-test)
      - [5.2.5 Performance Profiling](#525-performance-profiling)
      - [5.2.6 Load Testing](#526-load-testing)
      - [5.2.7 Stress Testing](#527-stress-testing)
      - [5.2.8 Volume Testing](#528-volume-testing)
      - [5.2.9 Security and Access Control Testing](#529-security-and-access-control-testing)
      - [5.2.10 Failover and Recovery Testing](#5210-failover-and-recovery-testing)
      - [5.2.11 Configuration Testing](#5211-configuration-testing)
      - [5.2.12 Installation Testing](#5212-installation-testing)
  * [6. Entry and Exit Criteria](#6-entry-and-exit-criteria)
    + [6.1 Test Plan](#61-test-plan)
      - [6.1.1 Test Plan Entry Criteria](#611-test-plan-entry-criteria)
      - [6.1.2 Test Plan Exit Criteria](#612-test-plan-exit-criteria)
      - [6.1.3 Suspension and Resumption Criteria](#613-suspension-and-resumption-criteria)
    + [6.2 Test Cycles](#62-test-cycles)
      - [6.2.1 Test Cycle Entry Criteria](#621-test-cycle-entry-criteria)
      - [6.2.2 Test Cycle Exit Criteria](#622-test-cycle-exit-criteria)
      - [6.2.3 Test Cycle Abnormal Termination](#623-test-cycle-abnormal-termination)
  * [7.Deliverables](#7deliverables)
    + [7.1 Test Evaluation Summaries](#71-test-evaluation-summaries)
    + [7.2 Reporting on Test Coverage](#72-reporting-on-test-coverage)
    + [7.3 Perceived Quality Reports](#73-perceived-quality-reports)
    + [7.4 Incident Logs and Change Requests](#74-incident-logs-and-change-requests)
    + [7.5 Smoke Test Suite and Supporting Test Scripts](#75-smoke-test-suite-and-supporting-test-scripts)
    + [7.6 Additional Work Products](#76-additional-work-products)
      - [7.6.1 Detailed Test Results](#761-detailed-test-results)
      - [7.6.2 Additional Automated Functional Test Scripts](#762-additional-automated-functional-test-scripts)
        * [Rest Backend](#rest-backend)
        * [Webapp](#webapp)
      - [7.6.3 Test Guidelines](#763-test-guidelines)
      - [7.6.4 Traceability Matrices](#764-traceability-matrices)
  * [8.Testing Workflow](#8testing-workflow)
  * [9. Environmental Needs](#9-environmental-needs)
    + [9.1 Base System Hardware](#91-base-system-hardware)
    + [9.2 Base Software Elements in the Test Environment](#92-base-software-elements-in-the-test-environment)
    + [9.3 Productivity and Support Tools](#93-productivity-and-support-tools)
    + [9.4 Test Environment Configurations](#94-test-environment-configurations)
  * [10. Responsibilities, Staffing, and Training Needs](#10-responsibilities--staffing--and-training-needs)
    + [10.1 People and Roles](#101-people-and-roles)
    + [10.2 Staffing and Training Needs](#102-staffing-and-training-needs)
- [11. Iteration Milestones](#11-iteration-milestones)
- [12. Risks, Dependencies, Assumptions, and Constraints](#12-risks--dependencies--assumptions--and-constraints)
  * [13. Management Process and Procedures](#13-management-process-and-procedures)
    + [13.1 Measuring and Assessing the Extent of Testing](#131-measuring-and-assessing-the-extent-of-testing)
    + [13.2 Assessing the Deliverables of this Test Plan](#132-assessing-the-deliverables-of-this-test-plan)
    + [13.3 Problem Reporting, Escalation, and Issue Resolution](#133-problem-reporting--escalation--and-issue-resolution)
    + [13.4 Managing Test Cycles](#134-managing-test-cycles)
    + [13.5 Traceability Strategies](#135-traceability-strategies)
    + [13.6 Approval and Signoff](#136-approval-and-signoff)

<small><i><a href='http://ecotrust-canada.github.io/markdown-toc/'>Table of contents generated with markdown-toc</a></i></small>

## Revision History

Version 1.0

| **Date** | **Version** | **Description** | **Author** |
| --- | --- | --- | --- |
| 27.05.2020 | 1.0 | Initial Version | qvalentin, open-schnick, Gimleux |

## 1. Introduction

### 1.1 Purpose

The purpose of the Iteration Test Plan is to gather all the information necessary to plan and control the test effort for a given iteration. It describes the approach to testing the
software, and is the top-level plan generated and used by managers to direct the test effort.

This Test plan for FileFighter supports the following objectives:

- Identifying the items that should be targeted by the tests.
- Identifying the motivation for and ideas behind the test areas to be covered.
- Outlining the testing approach that will be used.
- Identifying the required resources and providing an estimation for the test efforts.

### 1.2 Scope

FileFighter is tested using different methods of tests to ensure that the implementation is working correctly throughout the development.

### 1.3 Intended Audience

This document is written mainly for internal usage by the project team and contains technically detailed information about testing the application. The basic description of the application
itself is not part of it. Therefore, this document is for the developers and for readers with the necessary background knowledge. However, everyone interested is invited to read this
document.

### 1.3 Definitions, Acronyms and Abbreviations

{% include abbreviations.md %}

### 1.4 References

{% include references.md %}

### 1.6 Document Structure

See [Table of Contents](#-table-of-contents)

## 2. Evaluation Mission and Test Motivation

### 2.1 Background

The test coverage for our project leads to a better control of new implementations, and the changes made to existing code. It gives us a better possibility to make sure that future changes
won't influence the functionality negatively. The integration of testing into the deployment process ensures that just stable versions which meet our quality requirements are being deployed.

### 2.2 Evaluation Mission

The main reason for implementing tests is to ensure that occurring problems are identified as early as possible. This leads to stable and working versions of our project. Continuous testing
provides us the opportunity to automatically verify the functionality of our project. With Test Driven Development (TDD) the tests are written before the functionality itself gets
implemented. This helps to prevent problems before they occur.

### 2.3 Test Motivators

The motivation to use testing in our project was to reduce functional risks and keep the quality as high as possible. It helps to fulfill the needed requirements and is good for implementing
the Use Cases by checking the correct working results.

## 3. Target Test Items

The following list identifies the tested parts of our application. Tests will cover the main backend functionality as well as the logical implementations.

* Frontend (JavaScript)
* Backend (Java)
* Backend (Haskell)
* Setup scripts for the client (bash)

## 4. Outline of Planned Tests

### 4.1 Outline of Test Inclusions

* Backend functionality will be tested with unit tests and integration tests using cucumber
* Logical functionality will be tested with cucumber integration tests.
* User interface will be tested with snapshot test and automated UI test
* API will be tested using integration tests

### 4.2 Outline of Other Candidates for Potential Inclusion

There are possible additional options for testing, but these are not in scope of our testing yet.

- testing the performance of the application
- stress testing the server
- testing of the client scripts

### 4.3 Outline of Test Exclusions

Currently, the only real exclusion from tests is the testing of the database integration, because we test the logic that uses the database separately.

## 5. Test Approach

### 5.1 Initial Test-Idea Catalogs and Other Reference Sources

The concept of unit testing is to structure the code into pieces that are as small as possible. These units are going to be tested individually to check the functionality on the lowest
possible level. Due to this partitioning of the implementation, bugs and problems can be found rather easily. If the granular functionalities have been approved, the units can be put
together to modules, which then will be tested on this higher level. Unit Testing has proven to be a good way to find bugs and problems in software early and reliable.

The concept of behaviour driven development is to write tests that define how the application should behave before writing the actual code. To do this you can describe test cases in a humane
readable format (.feature files) that can be used by non developers. This way the developer gets a guideline for how to implement something and can easily tell if his implementation is
correct.

### 5.2 Testing Techniques and Types

#### 5.2.1 Data and Database Integrity Testing

n/a

#### 5.2.2 Function Testing

|||
| --- | --- |
| Technique Objective: | Assert correct behavior of each functionality of the project |
| Technique: | Creation of unit tests for each functionality that is part of model or controller. Creating integration tests for each important backend endpoint to ensure that the functions are also working correctly from a users perspective. |
| Oracles: |  Successful execution of unit tests using the JUnit Test Runner - Successful execution of unit tests on build |
| Required Tools: | JUnit, Mockito, Cucumber, Hspec |
| Success Criteria: | (This only applies to the rest-backend) All tests pass. That means that each class has a coverage of over 95% tested lines and the overall coverage is over 90%. Also the release workflow on github passes. |
| Special Considerations: | -|

#### 5.2.3 Business Cycle Testing

n/a

#### 5.2.4 User Interface Testing

#### automated End-to-End-test run in the browser

|| |
|---|---|
|Technique Objective    | automatically exercise the most common scenarios of the interface to test for the correct behavior |
|Technique |  Execute each use-case scenario’s individual use-case flows or functions and features, using valid and invalid data |
|Oracles |  automated took enters valid data, for example a valid username and a valid password   |
|Required Tools | [Cypress](https://cypress.io)     |
|Success Criteria |    All tests pass         |
|Special Considerations    | Test are recorded as shown below |

<video style="width:100%"  controls>
  <source src="https://assets.filefighter.de/cypress-register.mp4" type="video/mp4"> 
Your browser does not support the video tag.
</video>

#### automated snapshot test

|| |
|---|---|
|Technique Objective    | automatically detect changes to the user  interface |
|Technique |  check the generated html code and compare it with the previous version |
|Oracles |  -  |
|Required Tools | [jest](https://jestjs.io/), [storybook](https://storybook.js.org)|
|Success Criteria |    All tests pass         |
|Special Considerations    |     test that fail because the design was changed must be updated          |

#### 5.2.5 Performance Profiling

n/a

#### 5.2.6 Load Testing

n/a

#### 5.2.7 Stress Testing

n/a

#### 5.2.8 Volume Testing

n/a

#### 5.2.9 Security and Access Control Testing

n/a

#### 5.2.10 Failover and Recovery Testing

n/a

#### 5.2.11 Configuration Testing

n/a

#### 5.2.12 Installation Testing

n/a

## 6. Entry and Exit Criteria

### 6.1 Test Plan

#### 6.1.1 Test Plan Entry Criteria

The test plan is active for over 6 months, since we are writing tests first and then implementing the actual logic.

#### 6.1.2 Test Plan Exit Criteria

The execution of the Test Plan is completed when all test run without errors, and the project is finished.

#### 6.1.3 Suspension and Resumption Criteria

The test plan is not supposed to be suspended. Therefore, there are no suspension and resumption criteria.

### 6.2 Test Cycles

#### 6.2.1 Test Cycle Entry Criteria

Every pushed commit on GitHub triggers the tests to be run.

#### 6.2.2 Test Cycle Exit Criteria

The test effort of a cycle is deemed sufficient when a build has been completed without failures and all unit and integration tests are run successfully.

#### 6.2.3 Test Cycle Abnormal Termination

Occurring errors during the build terminate the test cycle. Then an email is sent to the person who made the changes that caused the test to fail.

## 7.Deliverables

### 7.1 Test Evaluation Summaries

| Continuous Integration Service                              | Badges |
|-------------------------------------------------------------|:-----:|
| [GitHub Pipeline (Frontend)](https://github.com/FileFighter/WebApp) | ![Latest Release](https://github.com/FileFighter/WebApp/workflows/Latest%20Release/badge.svg) ![Stable Release](https://github.com/FileFighter/WebApp/workflows/Stable%20Release/badge.svg) ![Docker Release](https://img.shields.io/github/v/release/filefighter/webapp?color=dark-green&label=Stable%20Version&logo=docker&style=for-the-badge) ![Docker Pulls](https://img.shields.io/docker/pulls/filefighter/frontend?logo=docker&style=for-the-badge) [![Code Smells](https://sonar.filefighter.de/api/project_badges/measure?project=de.filefighter.frontend&metric=code_smells)](https://sonar.filefighter.de/dashboard?id=de.filefighter.frontend) [![Lines of Code](https://sonar.filefighter.de/api/project_badges/measure?project=de.filefighter.frontend&metric=ncloc)](https://sonar.filefighter.de/dashboard?id=de.filefighter.frontend) [![Security Rating](https://sonar.filefighter.de/api/project_badges/measure?project=de.filefighter.frontend&metric=security_rating)](https://sonar.filefighter.de/dashboard?id=de.filefighter.frontend) [![Bugs](https://sonar.filefighter.de/api/project_badges/measure?project=de.filefighter.frontend&metric=bugs)](https://sonar.filefighter.de/dashboard?id=de.filefighter.frontend) [![Duplicated Lines Density](https://sonar.filefighter.de/api/project_badges/measure?project=de.filefighter.frontend&metric=duplicated_lines_density)](https://sonar.filefighter.de/dashboard?id=de.filefighter.frontend) ![CodeFactor](https://www.codefactor.io/repository/github/filefighter/webapp/badge) ![End-to-end tests](https://github.com/FileFighter/WebApp/workflows/End-to-end%20tests/badge.svg) |
| [GitHub Pipeline (Rest Backend)](https://github.com/FileFighter/RestApi) | [![Docker Release](https://img.shields.io/github/v/release/filefighter/restapi?color=dark-green&label=Stable%20Version&logo=docker&style=for-the-badge)](https://github.com/FileFighter/RestApi/releases) [![Docker Pulls](https://img.shields.io/docker/pulls/filefighter/rest?logo=docker&style=for-the-badge)](https://hub.docker.com/r/filefighter/rest) [![Quality Gate Status](https://sonar.filefighter.de/api/project_badges/measure?project=de.filefighter%3Arest&metric=alert_status)](https://sonar.filefighter.de/dashboard?id=de.filefighter%3Arest) [![Coverage](https://sonar.filefighter.de/api/project_badges/measure?project=de.filefighter%3Arest&metric=coverage)](https://sonar.filefighter.de/dashboard?id=de.filefighter%3Arest) [![Lines of Code](https://sonar.filefighter.de/api/project_badges/measure?project=de.filefighter%3Arest&metric=ncloc)](https://sonar.filefighter.de/dashboard?id=de.filefighter%3Arest) [![Security Rating](https://sonar.filefighter.de/api/project_badges/measure?project=de.filefighter%3Arest&metric=security_rating)](https://sonar.filefighter.de/dashboard?id=de.filefighter%3Arest) ![Latest Release](https://github.com/FileFighter/RestApi/workflows/Latest%20Release/badge.svg) ![Stable Release](https://github.com/FileFighter/RestApi/workflows/Stable%20Release/badge.svg) ![Tests (Master)](https://github.com/FileFighter/RestApi/workflows/Tests%20(Master)/badge.svg) |
| [GitHub Pipeline (FileHandler Backend)](https://github.com/FileFighter/FileHandler) | n/a |

### 7.2 Reporting on Test Coverage

Test coverage numbers for the rest backend will be generated by the surefire plugin running in a pipeline with maven.

### 7.3 Perceived Quality Reports

The tool which is used for quality reports is SonarQube. It shows the number of bugs, code-smells and code duplication in the code as well as several other metrics. The analysis of the code
is triggered by the test pipeline. Sonar also shows the test coverage calculated by the surefire plugin. That way we can easily track our code quality. Our dashboard can be
found [on our own SonarQube instance.](https://sonar.filefighter.de/projects?sort=-analysis_date)

All our projects are getting regularly pull requests created by a tool called renovate. The pull request updates dependencies of our projects. One example of this can be
seen [here](https://github.com/FileFighter/RestApi/pull/101).

Every repository is checked regularly by a tool called [synk.io](https://snyk.io/). [Synk](https://snyk.io/) is an open-source tool to notify developers about known vulnerabilities in their projects.

Our second tool for creating metrics is [codefactor](https://codefactor.io/).

### 7.4 Incident Logs and Change Requests

We are collecting the logs of a running version of the system. We are not tracking any usage of clients or anything like that because we are not human garbage and respect privacy.

### 7.5 Smoke Test Suite and Supporting Test Scripts

n/a

### 7.6 Additional Work Products

n/a

#### 7.6.1 Detailed Test Results

[Rest Backend](https://github.com/FileFighter/RestApi/actions/workflows/masterTests.yml)  
[Webapp](https://github.com/FileFighter/WebApp/actions/workflows/tests.yml)

#### 7.6.2 Additional Automated Functional Test Scripts

##### Rest Backend

<script src="https://gist-it.appspot.com/https://github.com/FileFighter/RestApi/blob/master/.github/workflows/masterTests.yml"></script>

##### Webapp

<script src="https://gist-it.appspot.com/https://github.com/FileFighter/WebApp/blob/master/.github/workflows/tests.yml"></script>

#### 7.6.3 Test Guidelines

n/a

#### 7.6.4 Traceability Matrices

n/a

## 8.Testing Workflow

When a developer adds new functionality to the project, he also writes an appropriate Unit-Test covering the functionality. All unit tests are then automatically executed on a build. The
developer can also test parts of the new code by running the tests from his IDE.

## 9. Environmental Needs

The test plan also lists the non-human resources.

### 9.1 Base System Hardware

| Resource | Quantity | Name and Type |
|---|---|---|
| Integration Server | 1 | provided by GitHub |
| Development Server    | 1 | Linux VM    |
| Database | 2 | MongoDB provided with docker    |

### 9.2 Base Software Elements in the Test Environment

| Software Element Name | Version             | Type and Other Notes |
|-----------------------|---------------------|----------------------|
| Windows               | 10                  | Operating System     |
| Linux (Arch btw)      | current             | Operating System     |
| Brave                 | current              | Internet Browser     |
| Chrome, Electron      | current              | Internet Browser     |
| Mozilla Firefox       | current              | Internet Browser     |
| MongoDB               | current             | Database             |

### 9.3 Productivity and Support Tools

| Tool Category or Type | Tool Brand Name                                                                                   |
|-----------------------|---------------------------------------------------------------------------------------------------|
| Code Hoster           | [github.com](https://github.com/FileFighter) and [tea.filefighter.de](https://tea.filefighter.de/)|
| CI Service            | [GitHub Actions](https://github.com/features/actions)                                             |
| Blog Hoster           | [github.com](https://github.com/) using [jekyll](https://jekyllrb.com/)                           |
| Communication Platform| [Matrix](https://matrix.org), [Jitsi](https://jitsi.filefighter.de/)                              |

### 9.4 Test Environment Configurations

Docker must be installed to set up the database.

## 10. Responsibilities, Staffing, and Training Needs

### 10.1 People and Roles

This table displays the staffing assumptions for the test effort of our project.

| Role                 | Person       | Specific Responsibilities                                               |
|----------------------|--------------|-------------------------------------------------------------------------| 
|Test Manager Backend  | Open-Schnick |Ensures that testing is complete and conducted for the right motivators| 
|Test Manager Frontend | qvalentin    |Ensures that testing is complete and conducted for the right motivators| 
|Test Analyst Backend | qvalentin |Selects what to test based on the motivators| 
|Test Analyst Frontend | Gimleux |Selects what to test based on the motivators| 
|Tester| everyone |Implements and executes the tests|

### 10.2 Staffing and Training Needs

All necessary roles are staffed by members of the project team.

# 11. Iteration Milestones

| **Milestone** | **Planned Start Date** | **Actual Start Date** | **Planned End Date** | **Actual End Date** |
| --- | --- | --- | --- | --- |
| Iteration Plan agreed | 27.04.2021  | 27.04.2021  |  |  |
| Iteration starts |  27.04.2021 | 27.04.2021 | End of Project |  |
|> = 20% Test Coverage (Backend)| 11.05.2021||
|> = 30% Test Coverage (Backend)| 25.05.2021||
|> = 50% Test Coverage (Backend)| 15.06.2021||
|Tests integrated in CI | 27.04.2021 | 27.04.2021 | End of Project ||

# 12. Risks, Dependencies, Assumptions, and Constraints

The risk for our project are outlined in our <a href="https://www.filefighter.de/wiki/#5-risk-management">Wiki</a>, and our blog post
about <a href="https://www.filefighter.de/pm/2021/04/08/risk-management.html">Risk Management</a>.

## 13. Management Process and Procedures

### 13.1 Measuring and Assessing the Extent of Testing

### 13.2 Assessing the Deliverables of this Test Plan

### 13.3 Problem Reporting, Escalation, and Issue Resolution

Minor Problems will be fixed by the developer of the task. Major Problems will be escalated and handled in an additional YouTrack task.

### 13.4 Managing Test Cycles

n/a

### 13.5 Traceability Strategies

n/a

### 13.6 Approval and Signoff

This test plan has to be approved by the Test Designer and the Testers.
