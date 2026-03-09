# FLW Application Performance Testing

This repository contains **performance testing scripts** for the FLW application created using **Apache JMeter**.
The project is organized using **separate branches for different types of performance tests** such as Load Testing and Spike Testing.
The goal of this repository is to evaluate the **performance, scalability, and reliability** of the FLW application under different traffic conditions.



# Performance Test Types
Currently the repository includes the following performance testing types:

| Test Type     | Description                                                          | Branch       |
| ------------- | -------------------------------------------------------------------- | ------------ |
| Load Testing  | Tests system performance under gradually increasing concurrent users | `load-test`  |
| Spike Testing | Tests system behavior when sudden spikes in traffic occur            | `spike-test` |

If you want to run a specific type of test, switch to the corresponding branch.
Example:
```
git checkout load-test
```

# Overview
The performance tests simulate **multiple users interacting with FLW application APIs** to evaluate system behavior under concurrent usage.
These tests help analyze how the system performs when handling large numbers of requests simultaneously.


# Key Points
* Performance testing is implemented using **Apache JMeter**
* Test data is provided using **CSV Data Set Config**
* The CSV file contains **multiple user credentials used during execution**
* The test suite includes several application APIs and workflows

Example APIs covered in testing include:

* Login
* Get User
* Get Profile
* Beneficiary Data
* Registration APIs
* Incentive Management APIs
* Other application workflows

# Testing Objectives
The main goal of these tests is to measure:
* **Response Time** – How quickly the system responds to requests
* **Throughput** – Number of requests processed per second
* **Error Rate** – Percentage of failed requests
* **System Stability** – How the system behaves under concurrent user load


# Repository Structure
Each testing type is maintained in a **separate branch** to keep scripts organized.

| Branch       | Contents                                  |
| ------------ | ----------------------------------------- |
| `load-test`  | Load testing JMeter scripts and datasets  |
| `spike-test` | Spike testing JMeter scripts and datasets |

Each branch typically contains:

* JMeter Test Plan (`.jmx`)
* CSV dataset containing user credentials
* Supporting configuration files


# Prerequisites
Before running the tests locally, ensure the following tools are installed:

* **Apache JMeter (version 5.x or later)**
* **Java (JDK 8 or above)**
* **Git**

You can verify the installations using:
```
java -version
jmeter -v
git --version
```

# How to Clone the Repository
Clone the repository using:
```
git clone <repository-url>
``

Navigate into the project directory:
```
cd <repository-name>
```
# How to Run Load Tests
If you want to execute **Load Testing**, switch to the `load-test` branch:

```
git checkout load-test
```

# Running the Test Locally
## Step 1 — Open JMeter
Launch **Apache JMeter** on your system.



## Step 2 — Open the Test Plan
Open the JMeter test plan file:
```
File → Open → Select the .jmx file
```

## Step 3 — Verify CSV Dataset
Ensure the **CSV Data Set Config** correctly references the dataset file containing the user credentials.


## Step 4 — Run the Test
Click the **Start (▶) button** in JMeter to begin executing the test.


## Step 5 — View Results
You can monitor the test results using the following JMeter listeners:
* **View Results Tree**
* **Summary Report**
* **Aggregate Report**

These reports provide insights into response time, throughput, and error percentages during the test execution.
